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
- Enable "**static website hosting**" option and choose "**Host a static website**" at Hosting type.
- Define index.html at Index document and Error document
