# ADS-B Feeder Kubernetes Example
This is an exmaple of the manifests I use to obtain and feed ADS-B data.
## Components
- readsb
    - https://github.com/sdr-enthusiasts/docker-readsb-protobuf
    - This needs to run on the machine where the SDR is connected. There are documented issues trying to get MLAT working inside VMware due to how VM CPU time is scheduled, so this needs to be bare metal. 
- feeder
    - https://github.com/sdr-enthusiasts/docker-adsbexchange
    - This can run inside a VM. It connects to readsb and feeds data to the locations specified. You can run multiple feeders if you'd like to feed multiple destinations.
- tar1090 (Optional)
    - https://github.com/sdr-enthusiasts/docker-tar1090
    - This provides a local ADS-B "radar" view. It connects to readsb. It can run inside a VM as well.