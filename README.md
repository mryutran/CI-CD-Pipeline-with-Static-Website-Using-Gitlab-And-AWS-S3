# CI/CD Pipeline with Static Website Using Gitlab & AWS S3

## Note
AWS S3 works with:
- Simple static HTML-only websites;
- HTML + Javascript;
- Modern web application using Angular, React.js, Vue;

Can't use S3 with:
- Server side using PHP, ASPX;
- Have a database like MySQL, MariaDB, Postgre, SQL Server,...

### Setting up AWS S3
- First create a bucket name "MyWebsite" to store static website files: index.html
- Enable "**static website hosting**" option and choose "**Host a static website**" at Hosting type at Properties TAB.
- Define index.html at Index document and Error document

![GitHub Logo](https://github.com/mryutran/CI-CD-Pipeline-with-Static-Website-Using-Gitlab-And-AWS-S3/blob/main/S3.png)

- Scroll down to the bottom of the page, will get the website endpoint, for exmaple:  http://xxx.s3-website.ap-east-1.amazonaws.com
- Set Block Public Access to OFF

![GitHub Logo](https://github.com/mryutran/CI-CD-Pipeline-with-Static-Website-Using-Gitlab-And-AWS-S3/blob/main/S3-PublicAccess.png)

- Add bucket policy 

![GitHub Logo](https://github.com/mryutran/CI-CD-Pipeline-with-Static-Website-Using-Gitlab-And-AWS-S3/blob/main/Policy-S3.png)


