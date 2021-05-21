# Low latency low bandwidth with bidirectional transmission general purpouse video encoder-decoder quality measurement tool

This kind of codec can be used effectively everywhere where having non latent image is an important factor, for example:
* remote controlled vehicles (drones, cars, planes...)
* wireless displays
* distant/remote screens
* remote gaming services
* remote monitoring devices

## Constraints:

### General
* Every frame is divided into 4 windows vertically
* Decoding execution also takes place at encoder side, decoded windows are stored in decoded windows cache.
* The feedback of received encoded window is sent from decoder to encoder by through feedback channel
* Feedback received at encoder activates decoding and caching decoded window in a buffer if confirmed encoded window is still available in cache of encoded windows
* Transmission channel is compressed with zlib and transmission budget is for compressed data

### Encoding window
* Encoding window execution takes place at every window one by one from top to bottom 
* Encoding window code size budget:                         ????? bytes
* Encoding window ram memory budget:                        ????? bytes
* Encoding window execution virtual machine cycles budget:  ????? cycles
* Encoding window transmission budget:                      ????? bytes
* Encoding window encoded windows cache size:               ?? 64 ?? windows (16 previous encoded frames)

### Decoding window
* Decoding window execution virtual machine cycles budget:  ????? cycles
* Decoding window code size budget:                         ????? bytes
* Decoding window ram memory budget:                        ????? bytes
* Decoding window decoded windows cache size:               ?? 32 ?? windows (8 previous frames)

### Other
* Image quality control algorithm:                          ??? PSNR ???

## Schematics
