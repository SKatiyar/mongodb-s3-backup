# Mongodb to Amazon s3 Backup Script

(Note: If connected to a cluster will use slave to take backup)

## Requirements

* Running mongod process
* mongodump
* mongo
* openssl
* tar
* rm
* curl

## Usage

```
bash /path/to/backup.sh -i MONGODB_HOST -k AWS_ACCESS_KEY -s AWS_SECRET_KEY -r S3_REGION -b S3_BUCKET
```
OR
```
bash /path/to/backup.sh -i MONGODB_HOST -l /path/to/local/bucket/mount
```

Where `S3_REGION` is in the format `ap-southeast-1`

## Cron

### Daily

Add the following line to `/etc/cron.d/db-backup` to run the script every day at midnight (UTC time)

```
0 0 * * * root /bin/bash /path/to/backup.sh -i MONGODB_HOST -k AWS_ACCESS_KEY -s AWS_SECRET_KEY -b S3_BUCKET -r S3_REGION
```

# License

(The MIT License)

Copyright (c) 2014 RGBboy &lt;l-_-l@rgbboy.com&gt;

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
'Software'), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
