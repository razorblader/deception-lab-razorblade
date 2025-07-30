# OpenCanary — Testing

This section demonstrates how to simulate common attacks against OpenCanary's emulated services and verify that logs are properly generated.

---

#  Nmap Scan (Port Discovery)

Use `nmap` from Kali Linux to scan for open ports and services exposed by OpenCanary:

```bash
nmap -sV <OPENCANARY-IP>
```
With that you should be able to see all open ports listed. 
To see the logs related to that activity you can run:
```bash
cat /var/tmp/opencanary.log
```
Now you can see the data related to the interaction, including the source IP.
# SSH

Now we will test the SSH simulated service from our Kali distro:
```bash
ssh -p 2222 user@<YOUR_VM_IP>
```
Try to log in, now let's see the logs.
```bash
cat /var/tmp/opencanary.log
```
Now you should see the source IP related to the interaction as well as the usernames and passwords used.

# FTP

Now let's do the same with the FTP emulated service
```bash
 ftp <YOUR_VM_IP> 
```
Try to log in and the we'll see what the logs got:

```bash
cat /var/tmp/opencanary.log
```
You should see the source IP and users and passwords used!

And that's it, you can play around and try to test other services, thank you
To contunue go to [CanaryTokens](../CanaryTokens/setup.md)
