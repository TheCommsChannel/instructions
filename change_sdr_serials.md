## Changing SDR Serials on adsbexchange.com raspberry pi image

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/B0B1OZ22Z)

When using two of the similar model SDRs, such as the 1090 and 978 SDRs made by Airnav Radarbox, they may have the same serial number.
This makes it difficult to assign each SDR to the 1090 and 978 services. Follow the steps below to change the serial numbers of the SDRs.

### Stop Services
First, stop the services that are potentially using the SDRs

```
sudo service readsb stop &&  sudo service dump978-fa stop
```

### Change the 1090 SDR Serial
First, make sure only one SDR is plugged in and it's the one that will be used for 1090 ES (In the case of the Radar Box SDRs, this is the green one). With that plugged in, run the following command:
```
rtl_eeprom -d 0 -p 1090ES -s 00000001
```

Now unplug the SDR and plug it back in. Run the following command to verify the change:
```
rtl_test
```
You should see the following output at the top
> Found 1 device(s):
  0:  Realtek, 1090ES, SN: 00000001

If all went well, unplug the SDR that was just configured.


### Change the 978 SDR Serial
Now, plug in the SDR that will be used for 978 UAT (In the case of the Radar Box SDRs, this is the red one). This should be the only SDR plugged into at this point. With that plugged in, run the following command:
```
rtl_eeprom -d 0 -p 978UAT -s 00000002
```

Now unplug the SDR and plug it back in. Run the following command to verify the change:
```
rtl_test
```
You should see the following output at the top
> Found 1 device(s):
  0:  Realtek, 978UAT, SN: 00000002

If all went well, you can plug the other SDR back in so that both are now plugged into the device. The process is now complete and the services can be started back up.

### Starting services
```
sudo service readsb start &&  sudo service dump978-fa start
```
