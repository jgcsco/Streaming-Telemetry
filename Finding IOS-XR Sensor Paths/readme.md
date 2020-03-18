# Cisco has a list of tools to help identify and explore ios-xr sensor paths.

### 1. Github
  Go here: [Github] (https://github.com/YangModels/yang/tree/master/vendor/cisco/xr) and browse models for specific release. 
  Note: Telemetry only cares about operational *-oper.yang models, not *–cfg.yang, not *–act.yang.
  
### 2. pyang
  Download the interested yang model to a linux server. 
  Use pyang to see the content of the model. 
  Compare names in the command you want to capture and the output of the YANG model
  
  ```console
  pyang -f tree Cisco-IOS-XR-infra-statsd-oper.yang --tree-path infra-statistics/interfaces/interface/latest/generic-counters
 
module: Cisco-IOS-XR-infra-statsd-oper
   +--ro infra-statistics
      +--ro interfaces
         +--ro interface* [interface-name]
            +--ro latest
               +--ro generic-counters
                  +--ro packets-received?                    uint64
                  +--ro bytes-received?                      uint64
                  +--ro packets-sent?                        uint64
                  +--ro bytes-sent?                          uint64
                  +--ro multicast-packets-received?          uint64
                  +--ro broadcast-packets-received?          uint64
<output snipped for brevity>
```

