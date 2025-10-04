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

2. Download or Write the Bash Script
- Save the script 's3_backup.sh' to your local machine:
Command: nano s3_backup.sh
Command: Copy and paste the script, then save the file.
<img width="1760" height="1100" alt="image" src="https://github.com/user-attachments/assets/5f7d83d3-95e6-4dbb-940d-d2c05d5a394d" />


