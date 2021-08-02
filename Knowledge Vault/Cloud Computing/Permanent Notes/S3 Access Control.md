# User based
- [[IAM User]]: who has permission to call API
- [[IAM Role]]: which service, cross account has permission to call API

# Resource based
- [[S3 Bucket Policy]]: bucket wide rules from S3 console - allow cross accounts => **Most common**
- Object Access Control List (Less Common)
- Bucket Access Control List (Less Common)

# User and Resource based integration
- [[IAM Principal]] can access [[S3 Object]] if [[IAM User]] has permission OR[[S3 Bucket Policy]] allow it AND no explicit DENY