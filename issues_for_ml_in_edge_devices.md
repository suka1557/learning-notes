# What happens when we want to do ML in Edge Devices ?

## Examples of Edge Devices
Mobile Phones, Raspberry PI and Smart Home devices could be classified as Edge Devices.

## Why do we want to do Edge Computing of ML Models ?
Main reason is to get **Low Latency**. In a normal set up, the ML model would be deployed on some cloud servers. 
When user clicks on a button, a request will be sent to the server, some processing will be done and results would be sent back via response.
This includes latency in compute + latency in network (traffic).

If we can do the compute on mobile only, the 2nd component would get removed (at least to a large extent).

There is one more reason: Internet connectivity and access is not a given at least for some users. This could be significant population for some company.
So in those cases, normally users won't be able to consumer ML powered services without edge computing.

## Coral Project
[The Coral Project](https://coral.ai) is one company that sells devices and services to do Edge Computing. Their [USB Accelerator](https://coral.ai/products/accelerator)
is one such example. It's a small USB (pen drive) that has a small TPU built inside it. You can run models which needs access to TPU by connecting this device to your system.
It comes with a Type-C port, so it should be connectable with Mobile also. And it'll definitely work with Raspberry Pi.



