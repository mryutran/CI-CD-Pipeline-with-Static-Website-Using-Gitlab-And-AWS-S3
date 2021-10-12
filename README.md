# CI/CD Pipeline with Static Website Using Gitlab & AWS S3


## Note
AWS S3 works with:
- Simple static HTML-only websites;
- HTML + Javascript;
- Modern web application using Angular, React.js, Vue;

Can't use S3 with:
- Server side using PHP, ASPX;
- Have a database like MySQL, MariaDB, Postgre, SQL Server,...

### Diagram

![GitHub Logo](https://github.com/mryutran/CI-CD-Pipeline-with-Static-Website-Using-Gitlab-And-AWS-S3/blob/main/Diagram.jpeg)

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

### Setting CloudFront point to S3 bucket

- Create Distribution, at Origin domain, choose S3 bucket created: xxx.s3.amazonaws.com

### CI/CD Pipeline with Gitlab CI & S3 

- Upload file to S3 from Gitlab CI, using AWS CLI.
- Create new IAM with programmatic access, attached AmazonS3FullAccess.
- Set-up Variable inside your Gitlab project. Go to Settings -> CI/CD -> Variables block.

![image](https://user-images.githubusercontent.com/77818932/136993079-549c932e-a545-46ac-9dd0-691ed36cb88b.png)

- Define the variable: (using IAM access key ID and Secret access key created before)

AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION - set the region which you have created S3 bucket
S3_BUCKET - set to the name of your S3 bucket.

![image](https://user-images.githubusercontent.com/77818932/136993560-e5fbd175-f045-4da4-b411-cba32432fd4a.png)

### Create Gitlab CI Pipeline file (.gitlab-ci.yml)



