# Ambev-DevOps_Challenges not 
Hello I'm Diego Machado and I created this Repository to answer all Ambev DevOps_Challeges! 
<p>We're here for tech and beer<span>&#127866;</span></p>

# Propose:

This repo was created only with the propose to answer the test challege for the job opopportunity <b>DevOps Engineer</b>
<br>Upon the opportunity I decided to create a Architecture Drawing for each one of all the challenges</br>
 
# The Original Challenge Repo:
•	[AMBEV-DevOps_Challenges](https://github.com/cervejaria-ambev/DevOps_Challenges/)

# The Challenges:
<br>•	[DevOps Engineer](https://github.com/cervejaria-ambev/DevOps_Challenges/blob/master/devops.md)</br>
•	[DBA](https://github.com/cervejaria-ambev/DevOps_Challenges/blob/master/dbre.md)
<br>•	[SRE](https://github.com/cervejaria-ambev/DevOps_Challenges/blob/master/sre.md)</br>
•	[DevSecOps Engineer](https://github.com/cervejaria-ambev/DevOps_Challenges/blob/master/devsecops.md)</br>



# 1º Architecture Design Drawing - DevOps Engineer

<span>&#10042;</span>  Architecture Drawing :

Design Drawing Over the Challege to DevOps Engineer is linked over this Images bellow just click to check the architecture!

Explanation of the sSructure Presented :

• Use cloud-init to create an app to scale 
"#cloud-config
package_upgrade: true
packages:
  - nginx
  - nodejs
  - npm
write_files:
  - owner: www-data:www-data
  - path: /etc/nginx/sites-available/default
    content: |
      server {
        listen 80;
        location / {
          proxy_pass http://localhost:3000;
          proxy_http_version 1.1;
          proxy_set_header Upgrade $http_upgrade;
          proxy_set_header Connection keep-alive;
          proxy_set_header Host $host;
          proxy_cache_bypass $http_upgrade;
        }
      }
  - owner: azureuser:azureuser
  - path: /home/azureuser/myapp/index.js
    content: |
      var express = require('express')
      var app = express()
      var os = require('os');
      app.get('/', function (req, res) {
        res.send('Hello World from host ' + os.hostname() + '!')
      })
      app.listen(3000, function () {
        console.log('Hello world app listening on port 3000!')
      })
runcmd:
  - service nginx restart
  - cd "/home/azureuser/myapp"
  - npm init
  - npm install express -y
  - nodejs index.js"
• Create a virtual machine scale set
• Increase or decrease the number of instances in a scale set
• Create autoscale rules
• View connection info for scale set instances
• Use data disks in a scale set

# Explanation

This list above would one of solution that will use for this challege, first Scale Set can support up to 1,000 VMs when you use an Azure platform image or VM customization requirements, you may wish. You can create up to 300 VMs in a scale set when using a custom image. This solution will helps at peak times, when the disc is widely used degrading the performance  issues mention in the Challenge, I definitely inclued as well scale set with data disks, reates a scale set with 50Gb data disks attached to each instance, instead only 30 gb as was mention in the test, also only to give more performance.


[![CloudSkew](https://cloudskewprod.azureedge.net/assets/misc/landing-page-hero-2.jpg)](https://app.cloudskew.com/viewer/705e048b-18d5-42df-a439-909b0a033501)


Please click in DevOps Solution to check answer for DevOps Engineer Challege:
[DevOps Solution](https://github.com/dimachDevNetOps/Ambev-Test/blob/master/devops.md)

# 2º Architecture Design Drawing - DBA (Not Started)

<span>&#10042;</span>  Architecture Drawing :

[![CloudSkew](https://cloudskewprod.azureedge.net/assets/misc/landing-page-hero-2.jpg)](https://www.cloudskew.com/)

Please click in DBA Solution to check answer for DBA Challege:
[DBA Solution](https://github.com/dimachDevNetOps/Ambev-Test/blob/master/dbre.md)

# 3º Architecture Design Drawing - SRE (Not Started)

<span>&#10042;</span>  Architecture Drawing :

[![CloudSkew](https://cloudskewprod.azureedge.net/assets/misc/landing-page-hero-2.jpg)](https://www.cloudskew.com/)

Please click in SRE Solution to check answer for SRE Challege:
[SRE Solution](https://github.com/dimachDevNetOps/Ambev-Test/blob/master/sre.md)

# 4º Architecture Design Drawing - DevSecOps Engineer (Not Started)

<span>&#10042;</span>  Architecture Drawing :

[![CloudSkew](https://cloudskewprod.azureedge.net/assets/misc/landing-page-hero-2.jpg)](https://www.cloudskew.com/)

Please click in DevSecOps Solution to check answer for DevSecOps Challege:
[DevSecOps Solution](https://github.com/dimachDevNetOps/Ambev-Test/blob/master/devsecops.md)
	
_______________________________________________________________________________________________________________________________	
	
[Professional Profile of the Contribution for this Challenge](https://www.linkedin.com/in/%E2%98%81-diego-machado-%E2%88%9E-06355969/)	
