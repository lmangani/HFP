# HFP
#### HEP Fidelity Proxy

Reliable way of relaying all your [HEP](http://hep.sipcapture.org) to any HEP remote server that is behind unreliable networks.

It is buffered TCP proxy with option of storing HEP locally in cases of backend HEP server unavailability and replaying of that HEP after HEP server becomes reachable again. It can be beneficial in highly distributed voice networks to reliably deliver your HEP to its destination without additional infrastructure.
It can be deployed locally to every HEP generating node within one premesis/DC/location acting as addon (1:1) approach or HEP generating nodes can connect to one HFP that will   reliably proxy HEP generated within one premesis/DC/location (N:1)


### Usage
```
./HFP -l :9060 -r (HEP TCP server we want to reliably proxy HEP)
```

### Build
##### Manual
Building HFP requires go 1.15+
```
make
```
###### Docker
```
docker build -t sipcapture/HFP .
docker run -ti --rm sipcapture/HFP -l :9062 -r 1.2.3.4:9062
```

### Flow Diagrams


<img width="794" alt="image" src="https://user-images.githubusercontent.com/37185376/127317842-3e65c362-8cc3-4666-9cd2-6495a5122a62.png">
