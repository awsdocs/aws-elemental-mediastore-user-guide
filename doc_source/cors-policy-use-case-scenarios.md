# CORS Use\-case Scenarios<a name="cors-policy-use-case-scenarios"></a>

The following are example scenarios for using CORS:

+ Scenario 1: Suppose you host a website in an AWS Elemental MediaStore container named *website*\. Your users load the website endpoint `http://website.mediastore.ap-southeast-2.amazonaws.com`\. You want to use JavaScript on the webpages that are stored in this container to be able to make authenticated GET and PUT requests for the same container by using the AWS Elemental MediaStore API endpoint for the container, `website.mediastore.amazonaws.com`\. A browser would normally block JavaScript from allowing those requests, but with CORS you can configure your container to explicitly enable cross\-origin requests from `website.mediastore.ap-southeast-2.amazonaws.com`\.

+ Scenario 2: Suppose you want to host a web font from your AWS Elemental MediaStore container\. Browsers require a CORS check \(also referred as a preflight check\) for loading web fonts, so you would configure the container that is hosting the web font to allow any origin to make these requests\.