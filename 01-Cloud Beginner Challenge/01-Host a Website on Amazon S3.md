<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)

**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate hosting a website on Amazon S3. I'm doing this project to learn Amazon S3

### Tools and concepts

Services I used were Amazon S3 and S3 bucket. Key concepts I learnt include using S3 and host a website

### Time, challenges, and wins

This project took me approximately one hour.

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will open Amazon S3 because I want to create a storage space for my website

### How long it took to create the bucket

Creating an S3 bucket took me about 2 minutes.

### Region selection

The Region I picked for my S3 bucket was Europe (Stockholm) eu-north-1. because it was the closest location for me.

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no other AWS accont in the entier word can use my backet's name.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_ba6d42ad)

## Upload Website Files to S3

### What I did in this step

In this step, I will download files because I want to upload them into my S3 bucket.

### Files I uploaded

I uploaded two files to my S3 bucket - they were in my downloads folder.

### How the files work together

Both files are necessary for this project because index.html is the main file and other forler contains othr dependent files.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_a265af88)

## Static Website Hosting on S3

### What I did in this step

In this step, I will configure my S3 bucket for static website hosting because I want to visit my public website link.

### Understanding website hosting

Website hosting means a sever like a normal computer for a site's files 

### How I enabled website hosting

To enable website hosting with my S3 bucket, I enable it on properties tab.

### Access Control Lists (ACLs)

An ACL is a set of rules that decides who can get access to a resource and yes I enabled it.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_c22c54c0)

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is just like a regular website URL. It lets people visit my S3 bucket's files as a website.

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw an error. The reason for this error was the actual HTML/image files I've uploaded are still private.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_22ce4daf)

## Success!

### What I did in this step

In this step, I will make my website files in S3 publicly accessible because I want to see mt website live on the internet!

### How I resolved the 403 error

To resolve this 403 Forbidden error, I made my files public

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Bucket Policies

### What I did in this extension

In this project extension I'm about to set up a bucket policy. I'm doing this so that stops people from deleting my files.

### Understanding bucket policies

Using bucket policies means I can now control more than just who can see/access an object. With bucket policies, I can manage:
-Who can delete the object
-Who can change the object
-Who can upload new objects to your bucket
And much, much more!
While bucket policies are a bit more advanced since I'm using code, the level of control I get is much higher compared to using ACLs.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_sm2sm2sm)

### What my bucket policy does

My bucket policy stops people from deleting my files, I tested this by trying to delete the index.html file and saw my access has been denied.

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)*
