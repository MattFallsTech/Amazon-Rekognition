<h1>Amazon Rekognition Label Generator</h1>


<h2>Description</h2>
In this project, I will be building an image labels generator, using Amazon Rekognition. It will be able to recognise images that are given and add labels to the image.
<br />


<h2>Services used</h2>

- <b>Amazon S3
- <b>Amazon Rekognition
- <b>Amazon CLI

<h2>Architectural Diagram</h2>

<img src="https://imgur.com/p1SSj3U.png" height="80%" width="80%"/>

<h2>Project walk-through:</h2>

<p align="center">
I Logged in to my AWS Management Console and navigated to Amazon S3 <br/>
<img src="https://imgur.com/01gPFuX.png" height="80%" width="80%"/>
<br />
<br />
Clicked on "Create Bucket" and gave it a unique name, leaving the rest of the options as default and clicked "Create Bucket". I will be using this bucket to store images to be used to generate labels.  <br/>
<img src="https://imgur.com/FmHoMey.png" height="80%" width="80%"/>
<br />
<br />
Now that the bucket is created I am going to click on "Upload" and then click on "Add files" to add some images.  <br/>
<img src="https://imgur.com/Yfzsi0r.png" height="80%" width="80%"/>
<img src="https://imgur.com/Yfzsi0r.png" height="80%" width="80%"/>
<br />
<br />
Clicked on upload and the images I have uploaded are shown  <br/>
<img src="https://imgur.com/YsaAXXZ.png" height="80%" width="80%"/>
<br />
<br />
Now I will be installing the AWS CLI with PowerShell using this prompt "msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi" <br/>
<img src="https://imgur.com/bbOVWNn.png" height="80%" width="80%"/>
<br />
<br />
Next I need to setup an access key by setting up an IAM user. I went to the IAM page and navigated to the User tab and entered a user name. <br/>
<img src="https://imgur.com/jHmZjYE.png" height="80%" width="80%"/>
<br />
<br />
In the set permissions I clicked on the "Attach policies directly" and added AdministratorAccess, then I created the user. <br/>
<img src="https://imgur.com/LPKYRsa.png" height="80%" width="80%"/>
<br />
<br />
I then created an access key from the user that I just created and selected CLI as the option. <br/>
<img src="https://imgur.com/inkyytR.png" width="80%"/>
<br />
<br />
Now I have my access key I navigated back to the terminal and entered "aws configure" and entered the keys and the region name (Note: I fixed region name to "ap-southeast-2" as what is shown in the image is wrong and had errors) <br/>
<img src="https://imgur.com/rxkp46t.png" width="80%"/>
<br />
<br />
Now I started to get ready for importing libraries. First I installed two libraries into the terminal "pip install boto3" and "pip install matplotlib" <br/>
<img src="https://imgur.com/xr8F2Or.png" width="80%"/>
<br />
<br />
Then I used Visual Studio to import the libraries in a .py file <br/>
<img src="https://imgur.com/2VqOoRf.png" width="80%"/>
<br />
<br />
Then I created a function called detect_labels this function will take an image and bucket name as input parameters. <br/>
- Within the function I created a Rekognition client using boto3. <br/>
- I usde the detect_labels method of the Rekognition client to detect labels in the image. <br/>
- I printed the detected lables along with the confidence levels. <br/>
- I loaded the image from the S3 bucket using boto3 and PIL.<br/>
- I used matplotlib to display the image and draw boxes around the detected objects.
<br/>
<img src="https://imgur.com/xOnlrYQ.png" width="80%"/>
<br />
<br />
Now I have created a main function to test the detect_labels function.
<br/>
<img src="https://imgur.com/IW39mPT.png" width="80%"/>
<br />
<br />
Running into an issue and looking into how to fix this.
<br/>
<img src="https://imgur.com/2Xowy04.png" width="80%"/>
<br />
<br />
 
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
