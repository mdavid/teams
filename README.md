# teams

The backend app that powers [team.lessig2016.us](https://team.lessig2016.us)

Report improvements/bugs at https://github.com/inmomentsoftware/teams/issues.


## Design Docs

Based on Mayday's teams project.
Please see https://github.com/MayOneUS/wiki/wiki/My-SuperPAC-design-doc.


## Setup

1. `cp config_NOCOMMIT_README config_NOCOMMIT.py`
2. download and setup [Google App Engine for Python here](https://developers.google.com/appengine/downloads)
3. Run this app with `dev_appserver.py .`
4. If you want to run [inmomentsoftware/lessigpledge](https://github.com/inmomentsoftware/lessigpledge) simultaneously, which you
   will need to for testing submission of forms and other things, run this app on a separate port other than the
   default 8080 to avoid port collisions. This can done by running
   `dev_appserver.py --port SOME_OTHER_FREE_PORT_LIKE_8081 .`.

## Deploy
1. Uncomment the following two lines in config_NOCOMMIT.py
```
## For production.
auth_service = ProdAuthService("https://auth.lessig2016.us")
pledge_service = ProdPledgeService(PLEDGE_SERVICE_URL)
```
2. Run `appcfg.py update .` in the root directory of the repo.