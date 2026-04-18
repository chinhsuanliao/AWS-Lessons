
1. Create an IAM account as aws credential（access key & secret）
Root User作為最大權限者，直接開aws credential 很混亂，因此開了iam-admin來管理未來不同用途的iam user
- 權限：AdministratorAccess
- 用途: AWS CLI 預設使用者
步驟:
a. 以Root User去開設IAM user:
 <img width="754" height="477" alt="image" src="https://github.com/user-attachments/assets/728531a9-2fc4-4c56-b2b6-4b1e07f88885" />
<img width="286" height="316" alt="Screenshot 2026-04-18 215526" src="https://github.com/user-attachments/assets/966ac1d8-103d-4030-9c7c-daf5affb490d" />
b.登入IAM user 帳號(此時Root User被自動登出是預期行為)
IAM → Users → iam-admin → Security credentials
建立 access key（CLI 用）,並存取下載 credentials(Access key ID & Secret access key)
最後再開啟MFA

2. 在PC上設定configuration
terminal下操作指令
</aws configure>
