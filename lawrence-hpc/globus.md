# Globus

## Logging in

### Logging in \(USD users\)

To log into Globus, go to [https://www.globus.org/](https://www.globus.org/) and click the Log in button.

![](../.gitbook/assets/image%20%2846%29.png)

Log into Globus using your USD credentials.

![](../.gitbook/assets/image%20%286%29.png)

It should open your Globus account.

![](../.gitbook/assets/image%20%2829%29.png)

## Adding Lawrence \(Home and Lab Directory\) Endpoints

Select 'Endpoints' from the side menu, then the 'Shared with You' tab.

![](../.gitbook/assets/image%20%2843%29.png)

Click on 'search all endpoints'.

![](../.gitbook/assets/image%20%2839%29.png)

Type in "sdds" then click on the "SDDS - South Dakota Data Store" option.

![](../.gitbook/assets/image%20%2818%29.png)

Click on the "collections" tab.

![](../.gitbook/assets/image%20%2858%29.png)

Click on "Add a Collection"

![](../.gitbook/assets/image%20%2849%29.png)

Click on 'SDDS - South Dakota Data Store \(POSIX\)'

![](../.gitbook/assets/image%20%2857%29.png)

To find the path to your home directory: from within Lawrence, use the **cd** command to return to your home directory, and use **pwd** to print your working directory.

```text
adison.kleinsasser@usd.local@login ~]$ cd
adison.kleinsasser@usd.local@login ~]$ pwd
/home/usd.local/adison.kleinsasser
```

Fill "Path" with **lawrence + the path to your home directory on Lawrence** \(usually something like lawrence/home/usd.local/user.name\). Choose a display name, fill in other details as desired, and click 'Create Collection'.  

![](../.gitbook/assets/image%20%2856%29.png)

After submitting, a confirmation window will appear.  To make a lab directory as well, click on the 'Create another collection from SDDS - South Dakota Data Store ' button.

![](../.gitbook/assets/image%20%2835%29.png)

Fill in the information for your lab directory with **lawrence + the path to your lab directory**.  \(To get the path to your lab directory, log into Lawrence, navigate to the lab directory, type pwd, and copy the output.\)  Add a name for the collection, then fill in other information as desired and click the "Create Collection" button.

![](../.gitbook/assets/image%20%2821%29.png)

Click on "Transfer data to or from this new collection" to return to Globus.

![](../.gitbook/assets/image%20%281%29.png)

