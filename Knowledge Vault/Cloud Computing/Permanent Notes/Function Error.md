Common Function error:
- [[Function Based Error]] Lambda function throws an exception or return an error object
- [[Runtime Based Error]] Function had been terminated due to timeout or fail to encoding the response object into JSON
- Function Error doesn't return a 400-series or 500-series error code, Lambda will include a header named X-Amz-Function-Error and a JSON response with other detail message.

Backlink: [[Lambda Error]]