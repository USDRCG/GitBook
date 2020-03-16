---
description: >-
  This page contains information on logging into Globus and linking a Lawrence
  home directory, and a lab directory to Globus as endpoints.
---

# Globus

{% hint style="warning" %}
Connecting to SDDS Globus \(data on Lawrence\) through Globus is **only available to** **USD users** at this time.

If you are **not from USD** but working **with someone who is**, and wish to share data via Globus, please contact **rcg@usd.edu**, and ask them to create a Globus collection with the data to be shared and then share that new collection with your Globus user.

If you are from USD, and would like to share files with a non-USD user, please see the section _Sharing with Other Users_ under the _Adding Lawrence \(Home and Lab Directories\)_ section.
{% endhint %}

## Logging in

### Logging in \(USD users\)

To log into Globus, go to [https://www.globus.org/](https://www.globus.org/) and click the Log in button.

![](../.gitbook/assets/image%20%2852%29.png)

Log into Globus using your USD credentials.

![](../.gitbook/assets/image%20%286%29.png)

It should open your Globus account.

![](../.gitbook/assets/image%20%2834%29.png)

## Adding Lawrence \(Home and Lab Directory\) Endpoints

Select 'Endpoints' from the side menu, then the 'Shared with You' tab.

![](../.gitbook/assets/image%20%2849%29.png)

Click on 'search all endpoints'.

![](../.gitbook/assets/image%20%2844%29.png)

Type in "sdds" then click on the "SDDS - South Dakota Data Store" option.

![](../.gitbook/assets/image%20%2820%29.png)

Click on the "collections" tab.

![](../.gitbook/assets/image%20%2865%29.png)

Click on "Add a Collection"

![](../.gitbook/assets/image%20%2855%29.png)

Click on 'SDDS - South Dakota Data Store \(POSIX\)'

![](../.gitbook/assets/image%20%2864%29.png)

To find the path to your home directory: from within Lawrence, use the **cd** command to return to your home directory, and use **pwd** to print your working directory.

```text
user.name@usd.local@login ~]$ cd
user.name@usd.local@login ~]$ pwd
/home/usd.local/user.name
```

Fill "Path" with **lawrence + the path to your home directory on Lawrence** \(usually something like lawrence/home/usd.local/user.name\). Choose a display name, fill in other details as desired, and click 'Create Collection'.  

![](../.gitbook/assets/image%20%2863%29.png)

After submitting, a confirmation window will appear.  To make a lab directory as well, click on the 'Create another collection from SDDS - South Dakota Data Store ' button.

![](../.gitbook/assets/image%20%2840%29.png)

Fill in the information for your lab directory with **lawrence + the path to your lab directory**.  \(To get the path to your lab directory, log into Lawrence, navigate to the lab directory, type pwd, and copy the output.\)  Add a name for the collection, then fill in other information as desired and click the "Create Collection" button.

![](../.gitbook/assets/image%20%2824%29.png)

Click on "Transfer data to or from this new collection" to return to Globus.

![](../.gitbook/assets/image%20%281%29.png)

### Sharing with Other Users

Select the desired endpoint.

![](../.gitbook/assets/image%20%2848%29.png)

Click on the 'Sharing' tab.

![](../.gitbook/assets/image%20%2823%29.png)

Click on the 'Add Permissions - Share With' button.

![](../.gitbook/assets/image%20%2818%29.png)

Fill in the **path to the directory** \(Note: `/` starts at the endpoint's location, so the path `/globus` in permissions for an endpoint that connects to your home directory \( e.g. `/home/usd.local/user.name` \) will connect to `/home/usd.local/user.name/globus` overall\).  Then make sure **'user'** is selected, and **enter the email address** of the user who is to be given permissions.  Make sure this email address is connected to the user's Globus account.  Then click 'Add'.

{% hint style="info" %}
Note: Keep in mind that all the directories/files within the directory you share will be accessible to the people it is shared with \(be cautious of sharing the path as is, that is, leaving it at root: `/` .  

We recommend having a directory called 'globus', within the home/lab directory and organizing files/directories to share within this directory, rather than sharing the entire directory.
{% endhint %}

![](../.gitbook/assets/image%20%2830%29.png)

Write a message if desired, choose whether to give the recipient write access, and click on 'Add Permission'.

![](../.gitbook/assets/image%20%2815%29.png)

This should now show up under the 'Sharing' tab.

![](../.gitbook/assets/image%20%2829%29.png)

{% hint style="info" %}
Note: If another Globus user with whom you have shared access to your endpoint adds or makes a change to a file, that action will be considered to have been done by you.  

Example: Person A shares an endpoint with person B and person B makes a new file on the shared endpoint: Lawrence will consider the file to be owned by person A.
{% endhint %}

