# AWS-S3-Bash-and-AWS-CLI-Lab-project
This project demonstrates the use of AWS S3, Bash scripting, and the AWS CLI to automate file uploads, check S3 bucket configurations, and generate reports. It is designed as a hands-on lab to showcase practical skills with these technologies.


**Preparation**
1. Install and Configure AWS CLI
- Make sure the AWS CLI is installed and configured with your credentials and region.
Command: aws configure
Provide:
- Access Key ID
- Secret Access Key
- Default region (e.g., us-east-1)
- Default output format (e.g., json)
<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/d3ea125b-c962-4267-85c6-c67d4d1bbec7" />

2. Create the S3 Bucket
- Use the AWS CLI to create a new S3 bucket for the lab.
- Command: aws s3 mb s3://the-s3-bucket-project-backup
<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/ee13018f-5216-484b-ba98-b2aa841e5e55" />


**Set Up Local Files**
1. Create a Directory for Backup Files
- Create a directory on your local system and add some sample files:
- Command: mkdir files-to-backup
- Command: echo 'Sample content for File 1' > files-to-backup/file1.txt
- Command: echo 'Sample content for File 2' > files-to-backup/file2.txt
[
](https://media.discordapp.net/attachments/1423522065474130005/1423767555549433976/Screenshot_2025-10-03_at_4.21.09_PM.png?ex=68e22b1d&is=68e0d99d&hm=faf13ebfb215f1910d53e0276ed788df1638b667269cc4559ee8d92520dbff8e&=&format=webp&quality=lossless&width=1760&height=1100)<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/00db5372-8c54-42bb-b894-d090a73df93e" />

2. Download or Write the Bash Script or Write a script using ChatGPT
- Save the script 's3_backup.sh' to your local machine:
- Command: nano s3_backup.sh
- Command: Copy and paste the script, then save the file.
<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/5f7d83d3-95e6-4dbb-940d-d2c05d5a394d" />

3. Make the Script Executable
- Grant execute permissions to the script:
- Command: chmod +x s3_backup.sh
<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/77d3b414-e29e-4f40-96c1-4591ab70f35c" />


**Run the Script**
1. Execute the Script
- Run the script to perform the following tasks:
- Check if the bucket is public or private.
- Upload files from the files-to-backup directory to the S3 bucket.
- Generate a report of uploaded files.
- Verify the files exist in S3.
- Command: ./s3_backup.sh                      

2. Verify the Output
The script will output status messages to the console and save a report (upload_report.txt) in the
current directory.
[
](https://media.discordapp.net/attachments/1423522065474130005/1423783954313515091/Screenshot_2025-10-03_at_5.25.55_PM.png?ex=68e23a63&is=68e0e8e3&hm=7726df3d246f820c665c77b6b1ce9aab105897e9a75fa743018fd22cdb21eed9&=&format=webp&quality=lossless&width=1760&height=1100)<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/34b4d979-7149-4607-9591-05e85b9ec2f3" />


**Validate in AWS**
1. Check Uploaded Files
- Use the AWS CLI to list files in your S3 bucket:
- Command: aws s3 ls s3://the-s3-bucket-project-backup
- Confirm the uploaded files (file1.txt, file2.txt) appear in the bucket.
[
](https://media.discordapp.net/attachments/1423522065474130005/1423800554219638894/Screenshot_2025-10-03_at_6.34.47_PM.png?ex=68e249d9&is=68e0f859&hm=41b9ccc09db6f9bcb916faa3128e8477374bf37a8513fac670794e2f66a9f48c&=&format=webp&quality=lossless&width=1760&height=1100)<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/2b92f1f8-7aaa-4eed-a566-ba229845bbed" />


**After nothing came up in the terminal (per the above photo), I decided to back track my steps and noticed I needed to edit the name of my bucket in the script using the nano command. Once you do that, run the script again and the files should now appear in the bucket.**
<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/546fb5d7-21fd-430b-9044-8eea66608985" />


**Review Bucket ACL and Policy**
- Confirm the script correctly identifies whether the bucket is public or private:
- Command: aws s3api get-bucket-acl --bucket my-s3-bucket-backup
- Command: aws s3api get-bucket-policy --bucket my-s3-bucket-backup
- I did not add a policy to this s3 bucket when I created and configured it so I did not review the policy for obvious reasons.
[
](https://media.discordapp.net/attachments/1423522065474130005/1423837504485986414/Screenshot_2025-10-03_at_8.56.45_PM.png?ex=68e26c42&is=68e11ac2&hm=759fa368226b03848c5bf35ae66223e690df0155b33f4d7843d1a56470045c45&=&format=webp&quality=lossless&width=1760&height=1100)<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/dd86fd4e-908b-4828-a775-e9b935d0374a" />


**Clean Up**
1. Delete Uploaded Files from S3
- Clean up the S3 bucket:
- Command: aws s3 rm s3://my-s3-bucket-backup --recursive

2. Delete the S3 Bucket
- Remove the bucket:
- Command: aws s3 rb s3://my-s3-bucket-backup

3. Remove Local Files
- Delete the local files-to-backup directory and script if no longer needed:
- Command: rm -rf files-to-backup s3_backup.sh upload_report.tx
<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/e11d0230-12d8-47f4-b65c-48460d58bad9" />


**Summary**
- I created and configured an S3 bucket.
- I Used Bash and AWS CLI to automate file uploads and security checks.
- I Verified the results in AWS and cleaned up resources.
