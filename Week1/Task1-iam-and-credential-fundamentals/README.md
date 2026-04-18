<img width="500" height="276" alt="image" src="https://github.com/user-attachments/assets/243b4e4a-96e4-47ac-a8e4-5e7be69c5401" /># 【問答題】
### 1. root user 跟 iam user 的差別？
### 2. user, group, role, policy 彼此間的關係為何？policy 的格式為何？

# 【實作題】
### 1. 為 root account 創建 MFA 登入。
   <img width="297" height="353" alt="Screenshot 2026-04-19 011546" src="https://github.com/user-attachments/assets/b9d87d4c-1519-4e7f-8178-a21ec1af72eb" />

### 2. 創建 aws credential（access key & secret），並且使用 aws cli 嘗試存取 ec2 列表（可以手動創建一台機器）及 s3 列表。
<img width="499" height="98" alt="image" src="https://github.com/user-attachments/assets/6d0b8fae-ab36-4f20-aee6-d5fd21272305" />
<img width="495" height="410" alt="Screenshot 2026-04-19 023109" src="https://github.com/user-attachments/assets/8a393b33-017e-433c-8905-0a451c1e59d0" />

### 3. 創建一個 user，名為 `s3_readonly`，並且僅給予其 s3 readonly 的權限，為此 user 創建 credential 並且設定在 aws cli 內，使用不同的 profile 可以指定用哪個 credential 跟 aws 溝通，驗證方式為嘗試取得 ec2 及 s3 的列表，其中一個會失敗。
<img width="500" height="276" alt="image" src="https://github.com/user-attachments/assets/7ec93e7f-1623-4b4d-ac3c-b3cdac45933d" />

EC2如預期失敗，因為沒開權限給他
### 4. 嘗試創建 inline policy，使 s3_readonly 這個使用者在某個時間後就無法存取 s3，並且回答 inline policy 可以用在哪些地方。
### 5. 嘗試創建 EC2，並且為其創建一個 S3ReadOnlyRole 的 role，使 ec2 上可以使用 aws cli（或是 sdk） 存取 s3 資源，並且不需要設定 access key。（這題可以用 aws linux，因為他有內建 aws cli）
