# Globus Information

{% hint style="danger" %}
This page is under construction, and may have incomplete or missing information.  Hardhats are not required.
{% endhint %}

## Availability

Connecting to SDDS Globus \(data on Lawrence\) through Globus is **only available** to send/receive data to/from **USD users** at this time. If you are not from USD but working with someone who is, and wish to share data via Globus, please contact rcg@usd.edu, and ask them to create a Globus collection with the data to be shared and then share that new collection with your Globus user. If you are from USD, and would like to share files with a non-USD user, please see the section Sharing with Other Users under the Adding Lawrence \(Home and Lab Directories\) section.

## Adding a Collection

### Meta Information



### Choosing a Base Path

The base path of a collection is the location to which the collection connects.  

For example, a base path:

```text
lawrence/home/usd.local/jane.smith
```

would lead to Jane Smith's home directory, if Jane Smith's home directory was located at "/home/usd.local/jane.smith" on Lawrence.

{% hint style="warning" %}
Note: the path to a home directory may be different.  To find the path to your home directory, log in to Lawrence, and use the command

pwd

to show the path to your home directory, then put "lawrence" in front of it.
{% endhint %}

Keep in mind that the base path shows the highest point in the file system of the destination computer that the Globus connection can reach. For example, a researcher using a collection with this base path:

```text
lawrence/home/usd.local/jane.smith/folder2
```

will only be able to reach items in "folder2", not in the rest of Jane Smith's home directory.

### Common base paths

Common options for collection base paths include:

* Individual home directories \(on Lawrence\)
* Lab directories \(on Lawrence\)
* SDDS lab

## Sub-Collections



## User Groups



## Sharing

