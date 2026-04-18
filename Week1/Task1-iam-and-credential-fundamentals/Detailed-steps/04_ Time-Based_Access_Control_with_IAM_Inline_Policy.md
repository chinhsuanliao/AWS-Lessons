<img width="350" height="389" alt="image" src="https://github.com/user-attachments/assets/3ed1d083-cda8-4bcd-9a8f-224ee0fac459" />注意: AWS policy用UTC時間（不是台灣時間，所以直接設定成現在時間+10分鐘)
AWS Console → IAM → Users → s3_readonly
<img width="361" height="219" alt="image" src="https://github.com/user-attachments/assets/044d3502-1050-4586-9019-c387fba77dda" />

### 1. 設定Inline Policy 
<img width="350" height="389" alt="image" src="https://github.com/user-attachments/assets/59a3acaa-8d36-48a3-8a8d-de23c6b625fe" />

'''bash
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "DenyS3AfterSpecificTime",
			"Effect": "Deny",
			"Action": "s3:*",
			"Resource": "*",
			"Condition": {
				"DateGreaterThan": {
					"aws:CurrentTime": "2026-04-19T19:10:00Z"
				}
			}
		}
	]
}
'''
<img width="364" height="313" alt="image" src="https://github.com/user-attachments/assets/595d70a4-59e3-4939-965b-fb8b0fbde146" />


### Verify S3 Access Before Expiration (Expected: Success)

```bash
aws s3 ls --profile s3_readonly
```



