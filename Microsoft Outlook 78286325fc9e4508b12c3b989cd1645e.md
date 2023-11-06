# Microsoft Outlook

## **Connecting MS Outlook and Folder**

```python
### Connecting to the MS outlook
import **win32com.client**
outlook = **win32com.client.Dispatch**("Outlook.Application").**GetNamespace("MAPI")**
```

**For Navigation**

```python
### Navigating to the Default Folder(6) = Inbox  (3  Deleted Items  |  4  Outbox  |  5  Sent Items  |  6  Inbox  |  14 Drafts)
main_folder = outlook.GetDefaultFolder(6)

### Navigating to the designated sub-folder
sub_folder = main_folder.Folders['Sample Folder']
```

**Locating the Mail Object**

```python
### Retrieve the first email (the last received email under normal circumstances)
message = inbox.Items.GetFirst()                                                                                                         
message = inbox.Items.GetLast()

### Looping every email in the designated inbox                                                                                              
for message in sub_folder.Items                                                                                                              

### Loop only messages within certain period of time
for message in messages.Restrict("[ReceivedTime]>= '2022-01-01'")
```

---

## Properties of Mall Object

Ref.:  [https://docs.microsoft.com/en-us/dotnet/api/microsoft.office.interop.outlook.mailitem?redirectedfrom=MSDN&view=outlook-pia#properties](https://docs.microsoft.com/en-us/dotnet/api/microsoft.office.interop.outlook.mailitem?redirectedfrom=MSDN&view=outlook-pia#properties_)

```python
message.subject
message.body
message.ReceivedTime
message.ReceivedTime.day
message.FlagStatus
message.Importance
message.Recipients
message.Sender
message.Sender.Address
message.Attachments
```

---

## Work-around With Attachment

```python
### Identify specific attachment
attachments = message.Attachments
attachment = attachments.Item(1)

### Save every attachment
for attachment in message.Attachments:
       attachment.SaveAsFile(os.path.join(path, str(attachment)))
```

![Untitled](Microsoft%20Outlook%2078286325fc9e4508b12c3b989cd1645e/Untitled.png)

---

## **Chapter 1 - Why Advertising Matters. Honestly.**

Advertising matters because it is an art form and shapes our culture

- **An Art Form**
    - **Mark Fenske:** Art is something that reinterprets for people the life they're leading; it allows you to experience what you know about life.
    And because advertising deals with the minutiae of everyday life, any art that comes out of it is going to be particularly relevant and powerful.
    - **Andy Berlin:** Advertising can be a popular art form - but that should happen by coincidence, not design.
    - **Greg DiNoto:** Persuasion - advertising - can be art, but ultimately that's for the consumer and the world at large to decide.
    - **Tim Delaney:** Persuasion can certainly be thought of as an art form - particularly when it brings together a combination of creative elements that are not entirely logical.
    - **George Louis:** Art is the lie that tells the truth. Almost all products are comparable in quality, but when advertising is great advertising - when it's inventive, irreverent, audacious, and loaded with chutzpah - it literally becomes a benefit for the product, and Picasso's "lie" becomes the truth. Food tastes better, clothes feel better, cars drive better.
- **Shaping Popular Culture**

![Untitled](Microsoft%20Outlook%2078286325fc9e4508b12c3b989cd1645e/Untitled.jpeg)

![Untitled](Microsoft%20Outlook%2078286325fc9e4508b12c3b989cd1645e/Untitled%201.jpeg)

**Pre-1960s Period**

Before 1960, ads were mundane and advertisers believe that ads should follow simple formulas to manipulate consumers. The founder of Ted Bates, Rosser Reeves, come up the idea of Unique Selling Proposition (USP). The idea at that time was to "Get a message into the heads of as many people as possible with the lowest possible cost." - It was a cold and efficient science of the business world. 

When Bill Bernbach found DDB in 2949, he thought that ads were fundamentally persuasion and that persuasion was more art than science. 

DDB's doctrine mentioned that there is no room for cleverness or ornamentation that was not directly tied to selling the product. If you are going to show a man upside down in an ad it should be for a reasons - such tas to show that the pockets in his pants keep his money from falling out. Besides studying the products, the team at DDB also figures out the emotion connection between the product and the consumers.