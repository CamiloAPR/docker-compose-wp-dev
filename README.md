# Docker Compose for WordPress Development
In a personal need to introduce myself to Docker this is my first official attempt to get into it. Hopefully, we'll see an evolution here ;D . Also, I hope this can come up handy to anyone in need of something like this for personal projects.
So, this _docker-compose_ file will mount a virtual environment for you to develop a WordPress site, using the Latest WordPress version available.

## INSTRUCTIONS
Run the following command where the docker-compose file is located: 

`docker-compose up`

After a couple of minutes you should be able to access the WP site at http://172.28.1.1 , and all of WordPress files in the same location where the docker-compose file is... unfortunately, by default such files will only allow `root` to edit 'em, so you'll have to run the following command aswell:

`sudo chmod -R 777 .`

**Note: 777 permissions are a bit too much, so make sure to find the ones that suit you the best**

And that's it!, from now on you're good to go.

## ADD DUMP from Prod

`docker exec -i $(docker ps -qf "name=db") mysql -uwordpress -pwordpress wordpress < ~/path/to/dump.sql`


_**Note:** `$(docker ps -qf "name=db")` will get the ID of the containers named 'db' currently running. So, if you have more than one running maybe just run `docker container ps` and pick your desired ID manually._

## DEPENDENCIES
Well, we just need docker-compose, so [follow this link](https://docs.docker.com/compose/install/#master-builds) and get it running on your machine.

## References
1. https://docs.docker.com/compose/wordpress/#define-the-project
2. https://www.sitepoint.com/how-to-use-the-official-docker-wordpress-image/
