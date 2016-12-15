# github webhook

> fork from https://github.com/razius/github-webhook-handler

## deploy webhook on server

    $ git clone https://github.com/Muxi-Studio/github_webhook.git
    $ cd github_webhook
    $ docker-compose build && docker-compose up -d

## config webhook

    $ cp repos.json.example repos.json
    $ vim repos.json (example configuration)

	 {
	    "Muxi-Studio/ccnubox_management_static": {
	        "path": "/root/www/ccnubox_management/ccnubox_management_static/",
	        "key": "ccnubox management",
	        "action": [
	 		["git", "pull", "origin", "master"],
	 		["cp", "index.html", "../deploy/app/templates/"],
	 		["cp", "static/css/*", "../deploy/app/static/css/"],
	 		["cp", "static/js/*", "../deploy/app/static/js/"],
	 		["cp", "static/img/*", "../deploy/app/static/img/"],
			["sh", "deploy.sh"]
	        ]
	    },
	 }
	 
## create a github webhook

![](https://cloud.githubusercontent.com/assets/10671733/21210302/d275a5b2-c2b4-11e6-994f-9cf6b5718c68.png) <br/>

note, the **Payload URL** is your server webhook url.
