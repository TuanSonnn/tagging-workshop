---
title : "Triển khai"

weight : 1
chapter : false
pre : " <b> 2. </b> "
---
### Cấu trúc Tài khoản AWS

AWS Organizations: 1 tài khoản quản lý (Management Account), nhiều tài khoản con (Member Accounts)

### Yêu cầu

IAM Roles:

OrganizationAccountAccessRole

TagAutomationLambdaRole

SCPs: Chặn tạo tài nguyên không gắn tag

### Công cụ:

AWS CLI đã cấu hình --profile cho từng account

AWS Console, AWS CDK (Python/TypeScript), Terraform (nếu sử dụng)