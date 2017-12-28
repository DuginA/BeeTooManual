# Изменить имя BeeToo.Controller

## NGrok

Connect to the btc with ssh client \([PuTTY](http://www.putty.org/) for example\)

`ssh pi@btc.local`

Open up the file for edit

`sudo -u beetoo nano /home/beetoo/beetoo-ngrok-pm2/app.js`

and change the name

`const NAME = '171228_change_me';`

## PM2

`sudo -u pm2 set pm2-slack:username 171228_change_me`

## Keymetricks

`sudo -u beetoo pm2 link 58id1ow56geal8v x7yeqee5t8pdlcl [171228_change_me]`

`sudo -u beetoo pm2 save`

