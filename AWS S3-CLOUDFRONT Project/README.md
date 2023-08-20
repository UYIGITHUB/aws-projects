note: create a like for admin/www/text/production/developer/staff/engineer.ontech.click...in doing this design try to create an A record first without creating them at cloudfront distribution and S3 bucket.

This note demonstrates the hosting of a static website use Route 53 as the DNS service, cloudfront for caching content, certificate manager to SSL of packet request, and S3 bucket for storage. The image below shows the architectural work process of the design.


![[Pasted image 20230709003748.png]]



Step 1

On the AWS management console search ROUTE 53
click registered domains 
click register domains

![[Pasted image 20230709005906.png]]

Step 2

select a unique name as your domain name, this name as to be unique.
click select to choose the available name and make payment


![[Pasted image 20230709010157.png]]

![[Pasted image 20230709010511.png]]

![[Pasted image 20230709010632.png]]

Uncheck the Auto-renew box
click next

![[Pasted image 20230709010835.png]]

fill-in all personal information

![[Pasted image 20230709011128.png]]


click  next
![[Pasted image 20230709011232.png]]

![[Pasted image 20230709011427.png]]

Step 2

Request AWS Certificate Manager
Search for certificate manager on the AWS search bar

![[Pasted image 20230709012104.png]]

click request a public certificate
click next
![[Pasted image 20230709012150.png]]

Enter the domain name that was registered
click DNS validation

![[Pasted image 20230709012448.png]]

click request

![[Pasted image 20230709012629.png]]

click view certificate
![[Pasted image 20230709013244.png]]

click create records in Route53

![[Pasted image 20230709013358.png]]

![[Pasted image 20230709013532.png]]

![[Pasted image 20230709013721.png]]

Go to Route 53 on your AWS management console 

![[Pasted image 20230709013921.png]]

![[Pasted image 20230709014005.png]]

![[Pasted image 20230709014045.png]]

step 3

create S3 bucket
search for S3 on the search bar
click create bucket
![[Pasted image 20230709014214.png]]


The bucket name most be same as the domain name for it to work
![[Pasted image 20230709014345.png]]

![[Pasted image 20230709014433.png]]

![[Pasted image 20230709015201.png]]

![[Pasted image 20230709015541.png]]

![[Pasted image 20230709015653.png]]

![[Pasted image 20230709020042.png]]

![[Pasted image 20230709020157.png]]

![[Pasted image 20230709020233.png]]

![[Pasted image 20230709020333.png]]

![[Pasted image 20230709020506.png]]

![[Pasted image 20230709020546.png]]

![[Pasted image 20230709020910.png]]

![[Pasted image 20230709021410.png]]


step 4

lunch cloudfront 


![[Pasted image 20230709021632.png]]

![[Pasted image 20230709022137.png]]

![[Pasted image 20230709022311.png]]

![[Pasted image 20230709022434.png]]

![[Pasted image 20230709022727.png]]

create A record

![[Pasted image 20230709025833.png]]

![[Pasted image 20230709025907.png]]

![[Pasted image 20230709025944.png]]


![[Pasted image 20230709030123.png]]



![[Pasted image 20230709030211.png]]

![[Pasted image 20230709030247.png]]


![[Pasted image 20230709030407.png]]

![[Pasted image 20230709030505.png]]

![[Pasted image 20230709032743.png]]