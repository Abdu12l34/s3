<<<<<<< HEAD



![image](https://github.com/user-attachments/assets/664d2dc9-506b-441c-bf24-a77fa55d6c92)

# Deploy static website to S3 using Github action
## There are some steps are follow for this application.
# Step 1: Create an S3 Bucket
1. Sign in to AWS Management Console and open the S3 service.

2. Create a new S3 bucket:

3. Click on "Create bucket".
 - Enter a unique bucket name (e.g., my-static-website).
 - Choose the region closest to your audience.
 - Uncheck "Block all public access" to allow public access to the bucket.
 - Acknowledge the warning and proceed.

4. Configure Bucket for Static Website Hosting:
 - After creating the bucket, go to the Properties tab.
 - Scroll down to the "Static website hosting" section.
 - Enable static website hosting and specify the index document (e.g., index.html).

5. Set Bucket Policy to Make Content Public:

 - Go to the Permissions tab, then scroll to the "Bucket policy" section.
 - edit a bucket policy to allow public read access to the contents. "Replace your-bucket-name" with your "actual bucket name:"
   
# Copy code
![image](https://github.com/user-attachments/assets/5d862170-5e3d-404c-8989-296c088ad02b)
 - Save the policy.
   
# Step 2: Push Your Static Website to GitHub
1. Initialize a Git Repository:

In your local project directory, run these command.
 - git init
 - git add .
 - git commit -m "type commit message"

2. Create a GitHub Repository:

Go to GitHub and create a new repository (e.g., my-static-website).
Push your local repository to GitHub, using these command,
  - git remote add origin https://github.com/Abdu12l34/my-static-website.git
  - git branch -M main
  - git push -u origin main

# Step 3: Automate Deployment with GitHub Actions
  1. Create a GitHub Actions Workflow:

     - In your project, create a directory named .github/workflows.

     - Inside it, create a file named deploy.yml with the following content:
       
name: Deploy to S3
on:
  push:
    branches:
      - main
jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout code
      uses: actions/checkout@v2

    - name: Sync S3 bucket
      uses: jakejarvis/s3-sync-action@v1
      with:
        args: --delete --acl public-read
      env:
        AWS_S3_BUCKET: ${{ secrets.AWS_S3_BUCKET }}
        AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
        AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        AWS_REGION: 'us-east-1'
        SOURCE_DIR: 'website'
- this code paste in deploy.yml file       
         



# Responsive Watches Website ⌚
## [Watch it on youtube](https://youtu.be/QPxYdbbCjhQ)
### Responsive Watches Website ⌚

- Responsive Watches Website Using HTML CSS & JavaScript
- Smooth scrolling in each section.
- Includes a dark and light mode.
- Developed first with the Mobile First methodology, then for desktop.
- Compatible with all mobile devices and with a beautiful and pleasant user interface.

Join the channel to see more videos like this. [Bedimcode](https://www.youtube.com/c/Bedimcode)

![preview img](/preview.png)
=======
# s3
>>>>>>> 23980f8996538be257abc6aeeb5a10bdbd446c20
