# NHK - September 2020 Online Plugfest

We provide an emulator of Hybrid TV (Hybridcast). 

## TD Discovery

### [Direct](https://w3c.github.io/wot-discovery/#introduction-direct)

- written URL: http://android.local:8887/td/nhktv.jsonld

### [DNS-Based Service Discovery](https://w3c.github.io/wot-discovery/#introduction-dns-sd)

1. browse `_wot._tcp` service on plugfest VPN.  for example:
```

% avahi-browse -r _wot._tcp
+  ens33 IPv4 Antwapp4hc                                    _wot._tcp            local
=  ens33 IPv4 Antwapp4hc                                    _wot._tcp            local
   hostname = [Android.local]
   address = [192.168.30.132]
   port = [8887]
   txt = ["type=Thing" "td=/td/nhktv.jsonld"]

```
2. retrieve TD using above information
```
% curl http://192.168.30.132:8887/td/nhktv.jsonld
```

## API
Please see [flows for Node-RED](https://github.com/endouhhc/wot-testing/new/master/events/2020.09.Online/TDs/NHK/flows_nhk_plugfest202009.json)

## Hybrid TV Emulator Android App 
- https://github.com/nhkrd/antwapp4hc
- dns-sd is not supported in current version.

## Related Works

### hyconet.js
- Javascript inplementation of standardized Hybridcast-Connect API 
- https://github.com/nhkrd/hyconet.js

### node-red-contrib-hyconet
- Node-RED extra node plugin for hyconet.js (Hybridcast-Connect Javascript SDK)
- https://github.com/nhkrd/node-red-contrib-hyconet
