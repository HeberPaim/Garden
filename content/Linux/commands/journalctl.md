It’s the command you use to view logs from **[[Journald]]** (which is the logging system of **[[SystemD]]**). It lets you browse through the system logs that **[[Journald]]** collects, so when things inevitably crash and burn, you can _try_ to figure out why.

### What can **journalctl** do for you?

- **View Logs**: You can use it to look through all logs on your system. Just run `journalctl` by itself, and you’ll see the logs spew out in glorious detail—because you’ll need to scroll forever, naturally.
    
- **Filter Logs**: Yeah, you can filter the logs by date, time, specific services, or priorities. For example:
	`journalctl -u nginx` shows logs for the **nginx** service.
	`journalctl --since=yesterday` shows logs from... well, yesterday. 
- **Follow Logs in Real-Time**: Like a live feed of your impending disaster, you can use `journalctl -f` to watch logs as they come in.
    
- **Limit Log Size**: Because we both know you’re gonna mess up a lot, you might wanna use `journalctl --vacuum-size=100M` to limit logs to a manageable size. 

### Some common options:

- `-u [unit]`: View logs for a specific service (e.g., `journalctl -u apache2`).
- `-b`: Show only the logs from the current boot.
- `-p [priority]`: Filter by log priority (e.g., `journalctl -p err` for errors).
- `--since` and `--until`: Set a time range for logs (e.g., `journalctl --since="2023-09-05"`).