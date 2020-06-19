# .scripts

To index all the scripts to your $PATH variable run:
```
git clone https://github.com/rnsavinelli/.scripts ~/.scripts
```
Then edit your `.bash_profile` file and add:
```
export PATH=$PATH:$HOME/.scripts/
```

## mount-andriod

This script's target was Linux computers so it uses the Linux version of `simple-mtpfs`.

This script will mount your device to the `~/.mnt/` folder which, if it does not exist, will
be created.

For the script to run simply:
```
./mount_android-sh
```

Once you've transferred all your files, or done what you had to do, to unmount your device run:
```
umount ~/.mnt/
```

## battery-notification

For the battery notification script to work in the background a cronjob or an ACPI event could be configured.

An entry template would be:
 ```
*/15 * * * * eval "export DBUS_SESSION_BUS_ADDRESS=unix:path=$PATH-TO-THE-BUS/bus"; $PATH-TO-THE-SCRIPT/battery_notification
 ```

Mine looks like this:
 ```
*/15 * * * * eval "export DBUS_SESSION_BUS_ADDRESS=unix:path=/run/user/1000/bus"; ~/.scripts/battery_notification
 ```

## License

All scripts are provided under an MIT License.

MIT License: <https://mit-license.org/> or see the [`LICENSE`](https://github.com/rnsavinelli/aed/blob/master/LICENSE) file.
