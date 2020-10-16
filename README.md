# gcp-bugpoc-ilb

Sets up ILB sandwich with 2 multi-nic gateways as backend service to test ILB distribution

To run the test run iperf with multiple concurrent connections (not too many, it's a small vm) against the server VM for a longer time and monitor network traffic on gw1 and gw2 instances, e.g.:

`iperf -c 172.16.1.3 -P 20 -t 240`
