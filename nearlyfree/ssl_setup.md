# SSL setup

Following [these instructions](https://members.nearlyfreespeech.net/forums/viewtopic.php?t=8567&highlight=ssl) 

```shell
ssh username@ssh.phx.nearlyfreespeech.net
cd /home/private
git clone https://github.com/nfsn/lets-nfsn.sh.git 
cd lets-nfsn.sh 
./nsfn-setup.sh
```

Then follow instructions to add a scheduled task:
```shell
/home/private/lets-nfsn.sh/nfsn-cron.sh
```
