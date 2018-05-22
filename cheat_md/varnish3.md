varnish3
========
Created Tuesday 10 October 2017

varnishlog -n prod -b -i TxURL :  url demandé au backend

varnishlog -n prod -c -m RxHeader:"X-Real-IP: 194.213.124.6"

varnishlog -n prod -m "RxStatus:200"  (cache ou backenkend)

varnishlog -n prod -b -m "RxStatus:500" (backenkend)

varnishlog -n prod -b -m "TxStatus:500" (backenkend)


# Display request cookies.
varnishtop -i RxHeader -I Cookie

# Display varnish hash data ('searchtext' is text to filter within hash).
varnishtop -i "Hash" -I searchtext

# Display 404s.
varnishlog -b -m "RxStatus:404"

# Display all Hashes.
varnishlog -c -i Hash

# Display User-Agent strings.
varnishlog -c -i RxHeader -I User-Agent
