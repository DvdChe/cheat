# Gitlab cheat sheet

## Service account tokens : 


### Create service account :

```bash
curl -XPOST \
   --header "PRIVATE-TOKEN: $GITLAB_TOKEN" \
   --data "name=<name>" \
   "https://<gitlab-url>/api/v4/service_accounts" | jq
```

### Create service account token :

Scopes are available here: https://docs.gitlab.com/ee/user/profile/personal_access_tokens.html#personal-access-token-scopes

```bash
curl -XPOST \
   --header "PRIVATE-TOKEN: $GITLAB_TOKEN" \
   --data "name=<token name>" \
   --data "scopes[]=<coma-separated,scopres>" \
   "https://<gitlab-url>/api/v4/users/<ID>/personal_access_tokens" | jq
```

### List tokens information of a specific user 
```bash
curl -XGET \
    --header "PRIVATE-TOKEN: $GITLAB_TOKEN" \
   "https://<gitlab-url>/api/v4/personal_access_tokens?user_id=<ID>"
```

### Get info from specific token 
```bash
 curl -XGET -H "PRIVATE-TOKEN: <token>" https://<gitlab-url>/api/v4/user | jq
```

### Renew service account 

```bash
curl --request POST \
  --header "PRIVATE-TOKEN: $GITLAB_TOKEN" \
  --url "https://<gitlab-url>/api/v4/personal_access_tokens/<personal_access_token_id>/rotate"
```
