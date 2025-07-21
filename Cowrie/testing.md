#  Cowrie — Testing

This section walks through how to simulate attacks against Cowrie's fake SSH service and observe how it captures attacker behavior.

---

## Simulated SSH Access

From the same VM used for seting up:
Let’s delete any other previous ssh known_hosts connections to the honeypot first to avoid erros:
```bash
rm .ssh/known_hosts
```
Now in a new terminal, in the same VM we can start to test it.
```bash
ssh root@localhost -p 2222
```
then we log in with any made up credentials.
After that, let's try some commands:
```bash
id

whoami

pwd
```
After that, you can see all interaction captured in logs! 
And that is it, as quick as this you can start testing how a Cowrie honeypot works!
To continue to the next honeypot please go to [OpenCanary](../OpenCanary/setup.md)

