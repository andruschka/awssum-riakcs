# awssum-riakcs / based on awssum-amazon-s3 #
## How to use with RiakCS ##
Everything works in the same way like awssum-amazon-s3, except the amazonS3 init function.  
You can now state a second parameter with your riakCS Url, if you won't it will operate like awssum-amazon-s3!  
This is an ```AwsSum``` plugin!

You'll need to add [awssum-amazon-s3](https://github.com/awssum/awssum-amazon-s3/) to your package.json
dependencies. Both [awssum](https://github.com/awssum/awssum/) and
[awssum-amazon](https://github.com/awssum/awssum-amazon/) are pulled in as peer dependencies.

## Example  with riakCS ##

Init riakCS and list all your buckets:

```
var RiakCS = require('awssum-riakcs');

var riakCS = new RiakCS.S3({
    'accessKeyId'     : process.env.ACCESS_KEY_ID,
    'secretAccessKey' : process.env.SECRET_ACCESS_KEY,
    'region'          : RiakCS.US_EAST_1
}, 'your-riakcs-url.com');

riakCS.ListBuckets(function(err, data) {
    if (err) {
      console.log(err);
    } else {
      console.log(data);
    }
});
```
## Example  with amazon s3 ##

Init s3 and list all your buckets:

```
var amazonS3 = require('awssum-riakcs');

var s3 = new amazonS3.S3({
    'accessKeyId'     : process.env.ACCESS_KEY_ID,
    'secretAccessKey' : process.env.SECRET_ACCESS_KEY,
    'region'          : amazonS3.US_EAST_1
});

s3.ListBuckets(function(err, data) {
  if (err) {
    console.log(err);
  } else {
    console.log(data);
  }
});
```
