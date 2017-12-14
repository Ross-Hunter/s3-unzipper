Forked from https://bitbucket.org/copperhill/s3-unzip

# S3 Unzipper #

A simple library to unzip an archive file in a S3 bucket to its root folder.

This fork unzips into memory rather than using the filesystem. This works much better for use with AWS Lambda, since you only have access to 512mb of disk, but you have up to 3008mb of memory.

### Install ###

`npm install s3-unzipper`

`const s3Unzipper = require("s3-unzipper");`

#### Options ####

~~~~
new s3Unzipper({
  bucket: "test-bucket-in-s3",
  file: "Companies.zip",
  deleteOnSuccess: true,
  verbose: false
}, function(err, success){
  if (err) console.error(err);
  else console.log(success);
});
~~~~

