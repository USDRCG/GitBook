# Globus Tutorials

{% hint style="danger" %}
This page is under construction, and may have missing or incomplete information.  Hardhats are not required.
{% endhint %}

## Logging in

To log into Globus, go to [https://www.globus.org/](https://www.globus.org/) and click the Log in button.

![](../.gitbook/assets/image%20%2860%29.png)

Log into Globus using your USD credentials.

![](../.gitbook/assets/image%20%288%29.png)

It should open your Globus account.

![](../.gitbook/assets/image%20%2838%29.png)

## 

## Sharing with Other Users

Select the desired endpoint.

![](../.gitbook/assets/image%20%2856%29.png)

Click on the '**Sharing**' tab.

![](../.gitbook/assets/image%20%2826%29.png)

Click on the '**Add Permissions - Share With**' button.

![](../.gitbook/assets/image%20%2821%29.png)

Fill in the **path to the directory** \(Note: `/` starts at the endpoint's location, so the path `/globus` in permissions for an endpoint that connects to the home directory `lawrence/home/usd.local/user.name` will connect to `lawrence/home/usd.local/user.name/globus` overall\).  Ensure **'user' is selected**, and **enter the email address** of the user who is to be given permissions.  Make sure this email address is connected to the user's Globus account.  Then click '**Add**'.

{% hint style="info" %}
Note: Keep in mind that all the directories/files within the shared directory will be accessible to the people it is shared with \(be cautious of sharing the path as is, that is, leaving it at root: `/` .  

We recommend making a directory called '**globus**', within the home/lab directory \(this must be done on Lawrence\) and organizing files/directories to share within this directory, rather than sharing the entire directory.
{% endhint %}

![](../.gitbook/assets/image%20%2833%29.png)

Write a message if desired, choose whether to give the recipient write access, and click '**Add Permission**'.

![](../.gitbook/assets/image%20%2818%29.png)

This should now show up under the '**Sharing**' tab.

![](../.gitbook/assets/image%20%2832%29.png)

{% hint style="info" %}
Note: If another Globus user with whom you have shared access to your endpoint adds or makes a change to a file, **that action will be considered as if it was done by you**.  

Example: Person A shares an endpoint with person B and person B makes a new file on the shared endpoint: Lawrence will consider the file to be owned by person A.
{% endhint %}

