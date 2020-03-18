---
description: >-
  This page contains information on logging into Globus and linking a Lawrence
  home directory and a lab directory to Globus as endpoints, as well as sharing
  an endpoint with another Globus user.
---

# Globus

{% hint style="warning" %}
Connecting to SDDS Globus \(data on Lawrence\) through Globus is **only available to** **USD users** at this time.

If you are **not from USD** but working **with someone who is**, and wish to share data via Globus, please contact **rcg@usd.edu**, and ask them to create a Globus collection with the data to be shared and then share that new collection with your Globus user.

If you are **from USD**, and would like to **share files with a non-USD** **user**, please see the section _Sharing with Other Users_ under the _Adding Lawrence \(Home and Lab Directories\)_ section.
{% endhint %}

## Logging in

To log into Globus, go to [https://www.globus.org/](https://www.globus.org/) and click the Log in button.

![](../.gitbook/assets/image%20%2860%29.png)

Log into Globus using your USD credentials.

![](../.gitbook/assets/image%20%288%29.png)

It should open your Globus account.

![](../.gitbook/assets/image%20%2838%29.png)

## Making Lawrence \(Home and Lab Directory\) Endpoints

Select '**Endpoints'** from the side menu, then the '**Shared with You'** tab.

![](../.gitbook/assets/image%20%2857%29.png)

Click on '**Search all endpoints**'.

![](../.gitbook/assets/image%20%2851%29.png)

Type in "**sdds**" then click on the '**SDDS - South Dakota Data Store'** option.

![](../.gitbook/assets/image%20%2823%29.png)

Click on the '**Collections**' tab.

![](../.gitbook/assets/image%20%2876%29.png)

Click on '**Add a Collection**'

![](../.gitbook/assets/image%20%2863%29.png)

Click on '**SDDS - South Dakota Data Store \(POSIX\)**'

![](../.gitbook/assets/image%20%2875%29.png)

For the next step, you will need the path to your home directory: from within Lawrence, use the **cd** command to return to your home directory, and use **pwd** to print your working directory.

```text
user.name@usd.local@login ~]$ cd
user.name@usd.local@login ~]$ pwd
/home/usd.local/user.name
```

Fill 'Path' with **lawrence/the\_path\_to/your\_home\_directory\_on\_Lawrence** \(previous step: usually something like lawrence/home/usd.local/user.name\). Choose a display name, fill in other details as desired, and click '**Create Collection**'.  

![](../.gitbook/assets/image%20%2874%29.png)

After submitting, a confirmation window will appear.  To make a lab directory as well, click on the '**Create another collection from SDDS - South Dakota Data Store**' button.

![](../.gitbook/assets/image%20%2845%29.png)

Fill in the information for your lab directory with **lawrence/the\_path\_to/your\_lab\_directory**.  \(Usually something like `lawrence/home/your_lab` . To get the path to your lab directory, log into Lawrence, navigate to the lab directory, type pwd, and copy the output.\)  Add a name for the collection, then fill in other information as desired and click the '**Create Collection**' button.

![](../.gitbook/assets/image%20%2827%29.png)

Click on '**Transfer data to or from this new collection**' to return to Globus.

![](../.gitbook/assets/image%20%281%29.png)

### Sharing with Other Users

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
Note: If another Globus user with whom you have shared access to your endpoint adds or makes a change to a file, that action will be considered to have been done by you.  

Example: Person A shares an endpoint with person B and person B makes a new file on the shared endpoint: Lawrence will consider the file to be owned by person A.
{% endhint %}

## Making a Personal Endpoint

A personal endpoint connects Globus to a personal computer.  Making a personal endpoint allows the user to transfer data from a personal computer to Lawrence, and vice versa, through Globus.

To make a personal endpoint, click on the '**Endpoints**' tab, then '**Create a personal endpoint'.**

![](../.gitbook/assets/image%20%284%29.png)

Choose a name for the endpoint.  Also note the "high assurance endpoint" option. Then click on '**Generate Setup Key'.**

{% hint style="warning" %}
If a high assurance endpoint is needed, other aspects of the data storage \(such as storage on Lawrence\) may not be equipped with the necessary security measures.  Please contact RCG at rcg@usd.edu for assistance.
{% endhint %}

![](../.gitbook/assets/image%20%2816%29.png)

Copy the setup key that is generated.

![](../.gitbook/assets/image%20%2870%29.png)

Select the Globus Connect download that matches the computer's operating system.

![](../.gitbook/assets/image%20%282%29.png)

Download and run the install wizard. When the 'Set up Endpoint' box comes up, **paste** the setup key into the corresponding text area.

![](../.gitbook/assets/image%20%2849%29.png)

You may be asked about modifying access to your documents.

![](../.gitbook/assets/image%20%2837%29.png)

Under the 'Administered by You' tab, look for the name of the personal endpoint.

![](../.gitbook/assets/image%20%2854%29.png)



