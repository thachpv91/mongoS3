# mongodump
Simply dump a mongodb, then stream everything to AWS S3, promise flavoured

## Usage

```es6
const mongodump = require('mongodump');

mongodump({
  URI: process.env.MONGO_URI,
  S3: {
      accessKeyId: process.env.AWS_ACCESS_KEY_ID,
      secretAccessKey: process.env.AWS_SECRET_ACCESS_KEY,
      Bucket: process.env.AWS_S3_DUMP_BUCKET,
      Key: process.env.AWS_S3_DUMP_KEY
  }
}).then(function (result) { console.log('EVERYTHING SHOULD BE OK') })
  .catch(function (err) { console.error('Snap something went wrong :(') });
```