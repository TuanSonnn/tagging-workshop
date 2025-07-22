---
title : "Phát hiện tài nguyên mới"

weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---
Truy cập EventBridge

Vào AWS Console: https://console.aws.amazon.com/eventbridge

Chọn "Rules" → Click Create Rule

Bước 2.1.2 – Cấu hình Rule

Name: TagEnforcementRule

Event Bus: Default

Rule Type: Rule with an event pattern

Bước 2.1.3 – Thiết lập mẫu sự kiện (Event pattern)

Chọn AWS events or EventBridge partner events

Dán mẫu JSON sau:

{
  "source": ["aws.ec2", "aws.s3", "aws.rds"],
  "detail-type": ["AWS API Call via CloudTrail"],
  "detail": {
    "eventName": ["CreateVolume", "RunInstances", "CreateBucket"]
  }
}

Click Next

Bước 2.1.4 – Thêm đích (Target)

Target type: AWS service

Select target: Lambda function

Function: AutoTagNewResource

Enable Retry & Dead-letter queue nếu muốn

Bước 2.1.5 – Kích hoạt Rule

Review lại cấu hình và click Create Rule

✅ Gợi ý: Đảm bảo CloudTrail đã được bật và ghi nhận các API tương ứng để sự kiện được gửi đến EventBridge đúng cách.
{
  "source": ["aws.ec2", "aws.s3", "aws.rds"],
  "detail-type": ["AWS API Call via CloudTrail"],
  "detail": {
    "eventName": ["CreateVolume", "RunInstances", "CreateBucket"]
  }
}