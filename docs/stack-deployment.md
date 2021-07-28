# Deployment

**Deployment is to copy the pre-installed ELK package online to your Cloud Server**. For example, after the user subscribes ELK on the Cloud Platform, the Platform will automatically copy the ELK to the corresponding Cloud Server.

- If ELK has been deployed, go to [Initial Installation](/stack-installation.md) to complete the operation.
- If not, you need to deploy ELK to your cloud server first.

We offer two schemes for ELK deployment and results are the same.

## Deploy by Image

**To deploy by Image** means to start instance based on ELK images. **ELK Image** provide OS and software environment needed for ELK.

For users with experience with cloud servers, to deploy by Image means "one-click deployment".

Websoft9 publishes [ELK image](https://apps.websoft9.com/elk) on Cloud Platforms and there are three methods to deploy it.

* When **Create New Instance**, you can select the ELK image as the system boot template.
* When you **Subscribe ELK** at Marketplace, the system will ask you to create a new instance for this image in the meantime.
* When **Re-install OS** for you instance, you can replace the existing image with a ELK image.

## Deploy by Script

**To Deploy by Script** means to run a script on your cloud instance to pull the pre-installed package online to your instance and configure it at the same time.

Websoft9 provides the [ELK ansible automation script](https://github.com/Websoft9/ansible-elk) on Github. If you are familiar with Ansible, you can deploy the ELK to the instance automatically.

## Comparison

No matter you **deploy by image** or **deploy by script**, the results are the same. So, what's the difference between the two deployment methods?

Suggest to read the document [Deploy by Image vs Deploy by Script](https://support.websoft9.com/docs/faq/bz-product.html#deployment-comparison).
