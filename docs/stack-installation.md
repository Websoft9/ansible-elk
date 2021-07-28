# Initial Installation

If you have completed the ELK deployment, follow the steps below to start a quick use.

## Preparation

1. Get the **Server's Internet IP** of Server on your Cloud Platform.
2. Check your **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the **TCP:8161** is allowed.
3. Make a domain resolution on your Cloud Console if you want to use domain for ELK.

## ELK Installation Wizard

1. Use local Chrome or Firefox to access the URL *http://DNS:15672* or *http://Server's Internet IP:15672*. You will enter installation wizard of ELK.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-login-websoft9.png)

2. Log in ELK web console. ([Don't have password?](/stack-accounts.md#elk)) 
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-bk-websoft9.png)

3. Set you new password from: 【Users】>【Admin】>【Permissions】>【Update this user】
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/elk/elk-pw-websoft9.png)

> More guide about ELK, please refer to [ELK Documentation](https://www.elk.com/documentation.html).

## ELK Setup wizard

## Q&A

#### Can't visit the start page of ELK?

Your TCP:15672 of Security Group Rules is not allowed, so there is no response from Chrome or Firefox.

#### ELK service can't start? 
Reason:  
Solution:  
