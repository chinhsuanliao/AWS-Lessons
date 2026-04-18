
## 1. Create an IAM account as aws credential（access key & secret）
Root User作為最大權限者，直接開aws credential 很混亂，因此開了iam-admin來管理未來不同用途的iam user
### 權限：AdministratorAccess
### 用途: AWS CLI 預設使用者
### 步驟:
#### a. 以Root User去開設IAM user:
 <img width="754" height="477" alt="image" src="https://github.com/user-attachments/assets/728531a9-2fc4-4c56-b2b6-4b1e07f88885" />
<img width="286" height="316" alt="Screenshot 2026-04-18 215526" src="https://github.com/user-attachments/assets/966ac1d8-103d-4030-9c7c-daf5affb490d" />

#### b.登入IAM user 帳號(此時Root User被自動登出是預期行為)
IAM → Users → iam-admin → Security credentials

建立 access key（CLI 用）,並存取下載 credentials(Access key ID & Secret access key)
最後再開啟MFA
###### Note: access key 是「iam-admin 的身分憑證」, 不是「Root 替他創立的共用鑰匙」,所以root看不到

## 2. 在PC上設定configuration
terminal下操作指令
```bash
aws configure
aws configure set default.region ap-northeast-1
```
AWS Access Key ID:     <iam-admin access key>
AWS Secret Access Key: <iam-admin secret>
Default region name:  us-east-1 (可以隨便換)
Default output format: json

## 3.用Console建立EC2（用 iam-admin）
Launch instance  → Ubuntu/Amazon Linux  → security group 開 SSH


## 4. 用Console建立S3 bucket
AWS Console → Services → S3 → Create bucket

## 5. 用 AWS CLI 驗證

```bash
aws sts get-caller-identity --no-verify-ssl
```


<img width="503" height="164" alt="Screenshot 2026-04-19 015719" src="https://github.com/user-attachments/assets/6e0942eb-0d14-4fc0-8026-aadc0e355430" />


```bash
aws ec2 describe-instances
aws s3 ls
```

###### 以下代表有成功讀取 但尚未建立任何指定服務
<img width="491" height="110" alt="image" src="https://github.com/user-attachments/assets/518c4346-5477-4748-8f75-5b6edbc1947a" />



