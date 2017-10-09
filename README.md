# inventory-kiosk

Tool lending kiosk, to be deployed on Raspberry Pis using [resin.io][resin-link]
Needs [inventory-server](https://github.com/ESAAAlab/inventory-server) running on a server.

#### resin.io deployment

To get this project up and running, you will need to signup for a resin.io account [here][signup-page] and set up a device, have a look at our [Getting Started tutorial][gettingStarted-link]. Once you are set up with resin.io, you will need to clone this repo locally:

```
$ git clone git@github.com:ESAAAlab/inventory-kiosk.git
```
Then add your resin.io application's remote repository to your local repository:
```
$ git remote add resin username@git.resin.io:username/myapp.git
```
By default, the docker image uses a US keyboard layout. This dockerfile.template changes it to french with :
```
RUN L='fr' && sudo sed -i 's/XKBLAYOUT=\"\w*"/XKBLAYOUT=\"'$L'\"/g' /etc/default/keyboard
```
Either comment or change this line to suit your needs.
Then push the code to the newly added remote :
```
$ git push resin master
```
It should take a few minutes for the code to push.
Don't forget to set the environment variables in your application dashboard.

#### Environnement variables to set

``` bash
# address for inventory-server webapp
DEFAULT_URL : 'http://192.168.x.x:3050'
```

---

Based on [resin-hosted-kiosk](https://github.com/drewsimon/resin-hosted-kiosk)

[resin-link]:https://resin.io/
