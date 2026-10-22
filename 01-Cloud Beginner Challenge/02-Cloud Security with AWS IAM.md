
# Cloud Security with AWS IAM


**Author:** Mojtaba Zarifi  
**Email:** mojtabazarifi86@gmail.com

---

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1c864649)

## Introducing Today's Project!

### Project overview

In this project, I will be using the AWS Identity and Access Management (IAM) service to control who is authenticated (signed in) and authorized (has permissions) in my AWS account. I'll launch an EC2 instance, then control who has access to it by creating some IAM policies and user groups.

### Tools and concepts

Services I used were Amazon EC2 and AWS AIM, Key concepts I learnt include IAM users, policies, user groups and account aliases. And also I learned how to use policy simulator, how JSON policies work, how to launch an instance and how to tag an instance.

### Project reflection

This project took me approximately one and a half hours today.

## Tags

### What I did in this step

In this step, I will launch two Amazon EC2 instances because need to increase our computing power!

### Understanding tags

Tags are like labels you can attach to AWS resources for organization.
This tagging helps us with identifying all resources with the same tag at once (they are useful filters when you're searching for something), cost allocation, and applying policies based on environment types.

### My tag configuration

The tag I’ve used on my EC2 instances is called "Env" the value I’ve assigned for my instances are development and production.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_2e0e5a5d)

## IAM Policies

### What I did in this step

In this step, I will create an IAM policy that gives access to the development instance (Not production).

### Understanding IAM policies

An IAM policy is a rule for who can do what with your AWS resources. It's all about giving permissions to IAM users, groups, or roles, saying what they can or can't do on certain resources, and when those rules kick in.

### The policy I set up

For this project, I’ve set up a policy using JSON.

### Policy effect

I’ve created a policy that allows some actions (like starting, stopping, and describing EC2 instances) for instances tagged with "Env = development" while denying the ability to create or delete tags for all instances.

### Understanding Effect, Action, and Resource

Effect:
‍This can have two values - either Allow or Deny - to indicate whether the policy allows or denies a certain action.
‍Action:
‍A list of the actions that the policy allows or denies.
‍Resource:
‍Which resources does this policy apply to? Specifying "*" means all resources within the defined scope.

## My JSON Policy

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1c864649)

## Account Alias

### What I did in this step

In this step, I will create an AWS account alias to simplify user login to our AWS account

### Understanding account aliases

An Account Alias is a friendly name for my AWS account that I can use instead of my account ID to sign in to the AWS Management Console.

### Setting up my account alias

Creating an account alias took me 10 sec Now, my new AWS console sign-in URL uses the alias insted of my account ID.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_0eb4439b)

## IAM Users and User Groups

### What I did in this step

In this step, I will set up tow resources, IAM users and IAM groups. because IAM users are like logins for people thet want access to our AWS accont, while user groups are like foldes to manage users that have the same level access.

### Understanding user groups

An IAM user group is a collection/folder of IAM users. It allows us to manage permissions for all the users in our group at the same time by attaching policies to the group rather than individual users.

### Attaching policies to user groups

I attached the policy I created to this user group, which means every user in this group will have the same permissions.

### Understanding IAM users

IAM users are the people that will get access to our resources/AWS account.

## Logging in as an IAM User

### Sharing sign-in details

The first way is to email sign in instructions to the user while the seconf way is to download a .csv file with the sign in details inside.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed that our user already denied access to items or panels on the main AWS console dashboard. This was because we only set up permissions to EC2 to our development EC2 instance(nothing else).

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_6f2ab446)

## Testing IAM Policies

### What I did in this step

In this step, I will test our new user's login and permissions to make sure that they have the right access to our development instance (and not the production instance).

### Testing policy actions

I tested my JSON IAM policy by attempting to stop both the development and the production instances. 

### Stopping the production instance

When I tried to stop the production instance I was met with an error. This was because of our group policy.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance I saw that it succesfully stopped. This was because we had the permission to do this.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_1811801c)

## IAM Policy Simulator

To extend my project, I'm going to test my permission policies in a safer and more controlled way, a tool called the AIM policy simulator.

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is atool that let's us simulate actions and test permission settings. It's useful for saving time when testing permission settings.

### How I used the simulator

I set up a simulation for whether our development our dev user group has permission to stop instences or delet tags. The results were denied for both. I had to adjust the scope of the EC2 instences to ones that are tagged with development. once be applied that tag permission was allowed.

![Image](https://nextwork.ai/lively_brown_mysterious_lion/uploads/51a5fd24-7458-58a6-8653-9b90119a0e4a_069d8a621)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/51a5fd24-7458-58a6-8653-9b90119a0e4a)*
