## What is Amazon S3?
 - Amazon Simple Storage Service (Amazon S3) is storage for the Internet. Amazon S3 has a simple web services interface that you can use to store and retrieve any amount of data, at any time, from anywhere on the web. It gives any developer access to the same highly scalable, reliable, fast, and inexpensive data storage infrastructure that Amazon uses to run its own global network of web sites.

- Advantages of using Amazon S3
1. Creating buckets – Buckets are the fundamental containers in Amazon S3 for data storage.
2. Storing data – Store an infinite amount of data in a bucket. Upload as many objects as you like into an Amazon S3 bucket.
3. Downloading data – Download your data or enable others to do so. Download your data anytime you like, or allow others to do the same.
4. Permissions – Grant or deny access to others who want to upload or download data into your Amazon S3 bucket.
5. Standard interfaces – Use standards-based REST and SOAP interfaces designed to work with any internet-development toolkit.

## Buckets
- A bucket is a container for objects stored in Amazon S3. Every object is contained in a bucket. For example, if the object named photos/puppy.jpg is stored in the awsexamplebucket1 bucket in the US West (Oregon) Region, then it is addressable using the URL https://awsexamplebucket1.s3.us-west-2.amazonaws.com/photos/puppy.jpg.

- Buckets serve several purposes:
1. They organize the Amazon S3 namespace at the highest level.
2. They identify the account responsible for storage and data transfer charges.
3. They play a role in access control.
4. They serve as the unit of aggregation for usage reporting.

## Objects
- Objects are the fundamental entities stored in Amazon S3. Objects consist of object data and metadata. The data portion is opaque to Amazon S3. The metadata is a set of name-value pairs that describe the object. These include some default metadata, such as the date last modified, and standard HTTP metadata, such as Content-Type. You can also specify custom metadata at the time the object is stored.

## Keys
- A key is the unique identifier for an object within a bucket. Every object in a bucket has exactly one key. The combination of a bucket, key, and version ID uniquely identify each object. So you can think of Amazon S3 as a basic data map between "bucket + key + version" and the object itself. Every object in Amazon S3 can be uniquely addressed through the combination of the web service endpoint, bucket name, key, and optionally, a version. For example, in the URL https://doc.s3.amazonaws.com/2006-03-01/AmazonS3.wsdl, "doc" is the name of the bucket and "2006-03-01/AmazonS3.wsdl" is the key.

### Advantages of using Amazon S3
- Amazon S3 is intentionally built with a minimal feature set that focuses on simplicity and robustness. Following are some of the advantages of using Amazon S3:

1. Creating buckets – Create and name a bucket that stores data. Buckets are the fundamental containers in Amazon S3 for data storage.
2. Storing data – Store an infinite amount of data in a bucket. Upload as many objects as you like into an Amazon S3 bucket. Each object can contain up to 5 TB of data. Each object is stored and retrieved using a unique developer-assigned key.
3. Downloading data – Download your data or enable others to do so. Download your data anytime you like, or allow others to do the same.
4. Permissions – Grant or deny access to others who want to upload or download data into your Amazon S3 bucket. Grant upload and download permissions to three types of users. Authentication mechanisms can help keep data secure from unauthorized access.
5. Standard interfaces – Use standards-based REST and SOAP interfaces designed to work with any internet-development toolkit.