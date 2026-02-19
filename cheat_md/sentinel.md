# Redis Sentinel Incident Response Cheatsheet

## Identify Master Name

**Don't know the name of the monitored cluster?**

```
redis-cli -p 26379 SENTINEL masters

```

_Look for the `name` field in the output (e.g., `mymaster`)._

## Locate the Master

**Who is the current leader?**

```
# Replace 'mymaster' with your cluster name
redis-cli -p 26379 SENTINEL get-master-addr-by-name mymaster

```

_Returns: `[IP] [Port]`_

## Health & Quorum Check

**Is the Sentinel cluster healthy?**

```
redis-cli -p 26379 INFO sentinel

```

_Check: `status=ok`, `address`, `slaves`, `sentinels` count._

**Is there enough quorum to failover?**

```
redis-cli -p 26379 SENTINEL ckquorum mymaster

```

_Check: "OK 3 [sentinels] vote for failover"_

## Detailed Node Status

**Full Master Details:**

```
redis-cli -p 26379 SENTINEL master mymaster

```

_Look for: `flags` (should be `master`, not `s_down` or `o_down`)._

**Check Replicas (Slaves):**

```
redis-cli -p 26379 SENTINEL replicas mymaster

```

_Look for: `master-link-status: up`, `lag: 0` or `1`._

**Check Other Sentinels:**

```
redis-cli -p 26379 SENTINEL sentinels mymaster

```

## Emergency Actions

**Force a Failover (Manual switch):**

```
redis-cli -p 26379 SENTINEL failover mymaster

```

**Clear Stale Config (Reset all state):**

```
redis-cli -p 26379 SENTINEL reset *

```

## Troubleshooting Traps (The "Pitfalls")

**Issue**

**Verification**

**Wrong Port**

Are you on `26379` (Sentinel) or `6379` (Redis)?

**S_DOWN**

Subjective Down. Only _this_ Sentinel thinks the node is dead. Check network.

**O_DOWN**

Objective Down. The _Quorum_ agreed the node is dead. Failover should trigger.

**Quorum < Min**

If Sentinels can't see each other, no failover will EVER happen.

**Config Rewrite**

Ensure `sentinel.conf` is **writable**. Sentinel updates it live.

**Protected Mode**

If `protected-mode yes`, ensure `bind` and `requirepass` are set correctly.

**Replica Priority**

If `replica-priority 0`, Sentinel will **never** promote that node to Master.

## Real-time Monitoring

**Watch events as they happen:**

```
redis-cli -p 26379
> MONITOR

```

_Useful to see `+sdown`, `+odown`, `+switch-master` events._
