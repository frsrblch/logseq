- `systemd-analyze`
- Jan 3 2024 AM:
	- Startup finished in 23.132s (firmware) + 15.468s (loader) + 53.588s (kernel) + 1min 18.135s (userspace) = 2min 50.325s 
	  graphical.target reached after 1min 18.131s in userspace
	- Changed loader, disabled some services
- Jan 3 2024 PM:
	- Startup finished in 40.063s (firmware) + 2.143s (loader) + 6.963s (kernel) + 41.564s (userspace) = 1min 30.735s 
	  graphical.target reached after 41.514s in userspace
- Jan 4 2024 AM:
	- Startup finished in 22.157s (firmware) + 2.143s (loader) + 6.549s (kernel) + 1min 587ms (userspace) = 1min 31.438s 
	  graphical.target reached after 1min 560ms in userspace
	- mask systemd-udev-settle.service
- Jan 4 2024 PM:
	- Startup finished in 28.754s (firmware) + 6.392s (loader) + 6.505s (kernel) + 6.461s (userspace) = 48.112s 
	  graphical.target reached after 6.457s in userspace
	- switch to quick boot, disable zfs
	- Startup finished in 10.690s (firmware) + 1.321s (loader) + 11.835s (kernel) + 4.360s (userspace) = 28.207s 
	  graphical.target reached after 4.356s in userspace
- Jan 11 2024 AM
	- Startup finished in 10.932s (firmware) + 1.185s (loader) + 11.868s (kernel) + 3.369s (userspace) = 27.356s 
	  graphical.target reached after 3.365s in userspace
- Jan 21 2024 AM
	- Startup finished in 10.924s (firmware) + 1.177s (loader) + 11.828s (kernel) + 3.778s (userspace) = 27.709s 
	  graphical.target reached after 3.774s in userspace