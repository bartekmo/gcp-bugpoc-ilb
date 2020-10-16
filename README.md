# gcp-bugpoc-ilb

Sets up ILB sandwich with 2 multi-nic gateways as backend service to test ILB distribution

Client starts a 10-minutes load test with 20 parallel connections immediately after deployment, so no additional steps are required to start the test. Just monitor it.

To run the test manually:
1. connect to client
2. run iperf with multiple concurrent connections (not too many, it's a small vm) against the server VM for a longer time. e.g.:
`iperf -c 172.16.1.3 -P 20 -t 240`

**NOTE**: health probe is running http requests against a dummy apache website on port 80, so you can easily affect health of a gateway instance by simply stopping the apache.

## References
- https://cloud.google.com/load-balancing/docs/internal/setting-up-ilb-next-hop#gcloud_2
- https://cloud.google.com/load-balancing/docs/internal/ilb-next-hop-overview#ilb-nh-multi-nic
