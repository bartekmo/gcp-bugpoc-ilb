# gcp-bugpoc-ilb

Sets up ILB sandwich with 2 multi-nic gateways as backend service to test ILB distribution

To run the test:
1. connect to client
2. run iperf with multiple concurrent connections (not too many, it's a small vm) against the server VM for a longer time. e.g.:
`iperf -c 172.16.1.3 -P 20 -t 240`
3. monitor network traffic on gw1 and gw2 instances (gcp web console should be fine)

## References
- https://cloud.google.com/load-balancing/docs/internal/setting-up-ilb-next-hop#gcloud_2
- https://cloud.google.com/load-balancing/docs/internal/ilb-next-hop-overview#ilb-nh-multi-nic
