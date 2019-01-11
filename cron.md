# Cron

## Format

Each entry in a crontab file has 6 fields,

Min  Hour  Day  Mon  Weekday
*    *     *    *    *        <command>

-    -     -    -    -
|    |     |    |    |__ Weekday (0=Sun .. 6=Sat)
|    |     |    |_______ Month (1 .. 12)
|    |     |____________ Day (1 .. 31)
|    |__________________ Hour (0 .. 23)
|_______________________ Minute (0 .. 59)

# Special Characters

Asterix
The asterix is a wild card character.

```bash
* * * * * /home/admin/scripts/delete.sh
```

Comma
The comma is used when creating a list when declaring 2 or more execution times

```bash
0,15,25 * * * * /home/admin/scripts/delete.sh
```

Hyphen
The hyphen is used to specify the range of time in which scripts can run.

```bash
0-59 0-23 * * * /home/admin/scripts/delete.sh
```

Forward slash
The forward slash is used to create specified intervals of time within a range

```bash
*/10 * * * * /home/admin/scripts/delete.sh
```

## Examples

0 * * * *       every hour

*/15 * * * *    every 15 mins

0 */2 * * *     every 2 hours

0 0 " " )       every Sunday midnight

@reboot         every reboot

## Crontab

```bash
# 
echo "@reboot echo hi" | crontab
```

```bash
# Edit your crontab file
crontab -e
```

```bash
# Display your crontab file
crontab -l 
```

```bash
# Diplay the last time you edited your crontab file
crontab -v
```

## Limiting access

