COSBench - Cloud Object Storage Benchmark
=========================================


Add new feature: head object
-----------
e.g. :
	```xml
	<storage type="s3v2" config="endpoint=xxx" />
	<operation type="head" ratio="100" config="cprefix=fullstack0..." />
	```

New Storage: s3v2
-----------
same to s3 except sdk version: s3v2 is aws-sdk-java-v2.  
e.g. : 
	```xml
	<storage type="s3v2" config="endpoint=xxx" />
	```

Add new feature: GiB, MiB, KiB
-----------
Now GB is 10^n, GiB is 2^n.  
e.g. :
	```xml
	<operation type="write" ratio="100" config="cprefix=fullstack0;containers=c(1);sizes=c(1)GiB" />
	<operation type="write" ratio="100" config="cprefix=fullstack0;containers=c(1);sizes=c(1)MiB" />
	<operation type="write" ratio="100" config="cprefix=fullstack0;containers=c(1);sizes=c(1)KiB" />
	```

Multipart upload Usage
-----------
Add Multipart upload method and part_size parameter: You can set it now. Default is 5MiB.  
e.g. : 
	```xml
	<operation type="mwrite" ...>
	<storage type="s3" config="part_size=5242880;...path_style_access=true;timeout=100000"/>
	```

Restore Usage
-----------
Add Restore method and restore_days parameter: restore_days. You can set it now. Default is 1.  
e.g. : 
	```xml
	<operation type="restore" ...>
	<storage type="s3" config="restore_days=1;...path_style_access=true;timeout=100000"/>
	```

HTTPS Usage
-----------
If https, please set no_verify_ssl to true.  
e.g. :
	```xml
	<storage type="s3" config="accesskey=accesskey;secretkey=secretkey;endpoint=https://ip:port;no_verify_ssl=true;path_style_access=true"/>
	```

= END =
========================================= 