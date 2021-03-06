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

## Making a Lawrence Endpoint

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

For the next step, you will need the path to the directory to which you want to connect \(e.g. home directory, lab directory, etc.\): to find this, from within Lawrence, use the **cd** command to navigate to the desired directory, then use **pwd** to print your working directory.

```text
user.name@usd.local@login ~]$ cd ~
user.name@usd.local@login ~]$ pwd
/home/usd.local/user.name
```

Fill 'Path' with **lawrence/the\_path\_to/your\_directory\_on\_Lawrence .**  Choose a display name, fill in other details as desired, and click '**Create Collection**'.  

![](../.gitbook/assets/image%20%2874%29.png)

After submitting, a confirmation window will appear.  To make another collection to a directory on Lawrence, click on the '**Create another collection from SDDS - South Dakota Data Store**' button.

![](../.gitbook/assets/image%20%2845%29.png)



## Making a Personal Endpoint

To make a personal endpoint, click on the '**Endpoints**' tab, then '**Create a personal endpoint'.**

![](../.gitbook/assets/image%20%284%29.png)

If the prompt comes up, download the Globus Connect Personal Software.

![](../.gitbook/assets/image%20%2887%29.png)

A new window for the setup should appear. Click "Log in".

![](../.gitbook/assets/image%20%2895%29.png)

Find your organization in the drop-down menu \(For USD users, this will be 'University of South Dakota'\).

![](../.gitbook/assets/image%20%2894%29.png)

Once you have logged into your organization's login, provide a label for the endpoint and click 'Allow'.

![](../.gitbook/assets/image%20%2891%29.png)

![](../.gitbook/assets/screenshot-79-.png)

Go to the window attached to the globus icon on your taskbar.  In this window, verify your identity \(possibly an email address\), enter the collection name \(endpoint\), and enter details if desired.  Also note the "high assurance endpoint" option. Then click on 'Save'.

{% hint style="warning" %}
If a high assurance endpoint is needed, other aspects of the data storage \(such as storage on Lawrence\) may not be equipped with the necessary security measures.  Please contact RCG at rcg@usd.edu for assistance.
{% endhint %}

![](../.gitbook/assets/image%20%2892%29.png)

A message about the success of the setup should appear.

![](../.gitbook/assets/image%20%2893%29.png)



## Making a Group

In the 'Groups' tab, click on 'Create new group'

![](../.gitbook/assets/image%20%2896%29.png)

Add a group name, description if desired, choose the administrator for the group, and whether the group will be viewable by anyone on Globus, or only by those in the group.  Then click 'Create Group'.

![](../.gitbook/assets/image%20%2897%29.png)

The group overview will appear once the group is created.

![](../.gitbook/assets/image%20%2898%29.png)

## Sharing with Other Users \(Individual or Group\)

Sharing an endpoint is a way to give another person access to one's own data, as explained in [Globus Information: Guest Collections & Sub-Collections](https://usdrcg.gitbook.io/docs/globus/globus-information#guest-collections-and-sub-collections).  

First, select the endpoint that is **connected to the data to be shared** \(even if not all the data to which the endpoint is connected will be shared; this can be restricted in another step\).

![](../.gitbook/assets/image%20%2856%29.png)

Click on the '**Sharing**' tab.

![](../.gitbook/assets/image%20%2826%29.png)

Click on the '**Add Permissions - Share With**' button.

![](../.gitbook/assets/image%20%2821%29.png)

{% hint style="info" %}
The next step is separated into two paths based on whether the endpoint needs to be shared with a user or with a group.  Please choose the section accordingly.  
{% endhint %}

### If sharing with an individual user:

Fill in the **path to the directory** \(Note: `/` starts at the endpoint's location, so the path `/Carrots` \(as per the [example](https://usdrcg.gitbook.io/docs/lawrence-hpc/globus-information#guest-collections-and-sub-collections)\) in permissions for an endpoint that connects to the home directory `lawrence/home/usd.local/user.name` will connect to `lawrence/home/usd.local/user.name/Carrots` overall\). 

Ensure **'user' is selected**, and **enter the email address** of the user who is to be given permissions.  Make sure this email address is connected to the user's Globus account.  Then click '**Add**'.

![](../.gitbook/assets/image%20%2880%29.png)

Write a message if desired, choose **whether to give the recipient write access**, and click '**Add Permission**'.

{% hint style="warning" %}
Note: Keep in mind that **all** the **directories/files** **within the shared directory** will be **accessible** to the **people** it is **shared with** \(be cautious of sharing the path as is, _that is_, leaving it at root: `/` .  

For this reason, we recommend making a directory called '**globus**', within the home/lab directory \(this must be done on Lawrence\), organizing files/directories to be shared within that directory, rather than sharing the entire home/lab directory, and then sharing the 'globus' directory. **\(Replace 'Carrots'** in this example **with 'globus'**.\)
{% endhint %}

This should now show up under the '**Permissions**' tab.

![](../.gitbook/assets/image%20%28100%29.png)

{% hint style="info" %}
Note: If another Globus user with whom you have shared access to your endpoint adds or makes a change to a file, **that action will be considered as if it was done by you**.  

Example: Person A shares an endpoint with person B and person B makes a new file on the shared endpoint: Lawrence will consider the file to be owned by person A.
{% endhint %}

### If sharing with a group:

Fill in the **path to the directory** \(Note: `/` starts at the endpoint's location, so the path `/Carrots` \(as per the [example](https://usdrcg.gitbook.io/docs/lawrence-hpc/globus-information#guest-collections-and-sub-collections)\) in permissions for an endpoint that connects to the home directory `lawrence/home/usd.local/user.name` will connect to `lawrence/home/usd.local/user.name/Carrots` overall\). 

Select 'group'.  The window will change to a search window.  Select the desired group, then \(back on the first page\) choose whether to give the group write permissions and click "Add Permissions".

![](../.gitbook/assets/image%20%28101%29.png)

{% hint style="warning" %}
Note: Keep in mind that **all** the **directories/files** **within the shared directory** will be **accessible** to the **people** it is **shared with** \(be cautious of sharing the path as is, _that is_, leaving it at root: `/` .  

For this reason, we recommend making a directory called '**globus**', within the home/lab directory \(this must be done on Lawrence\), organizing files/directories to be shared within that directory, rather than sharing the entire home/lab directory, and then sharing the 'globus' directory. **\(Replace 'Carrots'** in this example **with 'globus'**.\)
{% endhint %}

This should now show up under the '**Permissions**' tab.

![](../.gitbook/assets/image%20%2899%29.png)

{% hint style="info" %}
Note: If another Globus user with whom you have shared access to your endpoint adds or makes a change to a file, **that action will be considered as if it was done by you**.  

Example: Person A shares an endpoint with person B and person B makes a new file on the shared endpoint: Lawrence will consider the file to be owned by person A.
{% endhint %}



