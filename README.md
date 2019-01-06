# Docker Compose for WordPress Development
In a personal need to introduce myself to Docker this is my first official attempt to get into it. Hopefully, we'll see an evolution here ;D . Also, I hope this can come up handy to anyone in need of something like this for personal projects.
*So, this _docker-compose_ file will mount a virtual environment for you to develop a WordPress site, using the Latest WordPress version available*.

# INSTRUCTIONS
Run the following command where the docker-compose file is located: 

`docker-compose up`

After a couple of minutes you should be able to access the WP site at http://172.28.1.1 , and all of WordPress files in the same location where the docker-compose file is located... unfortunately, by default such files will only allow `root` to edit 'em, so you'll have to run the following command aswell:

`sudo chmod -R 755 .`

And that's it!, from now on you're good to go.



# References
1. https://docs.docker.com/compose/wordpress/#define-the-project
2. https://www.sitepoint.com/how-to-use-the-official-docker-wordpress-image/
