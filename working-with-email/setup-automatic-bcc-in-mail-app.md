# Setup automatic Bcc in Mail App

Some email providers such as Gmail does not allow you to setup an automatic Bcc address. However, with a little magic you can also do this locally with some email clients such as Apple Mail.

### 1. Open terminal app

Type _terminal_ in spotlight search and hit return to start the terminal application.

### 2. Perform magic

Start by typing the following into your terminal and pressing enter.

```
defaults read com.apple.mail UserHeaders
```

This command should return something like _"The domain/default pair of (com.apple.mail, UserHeaders) does not exist"._ If so, continue with the following command and replace yourco-id@user.wobaka.com with your Mailbox address.

```
defaults write com.apple.mail UserHeaders '{"Bcc" = "yourco-id@user.wobaka.com";}'
```

{% hint style="info" %}
You can find your Mailbox address in Wobaka under **Settings > Mailbox**.
{% endhint %}

That's it! All outgoing emails sent from Apple Mail will now be sent as **Bcc** to Wobaka. 🙌

### How to disable automatic Bcc

If you want to disable your automatic Bcc you need to start the terminal application again, type the following and hit enter.

```
defaults delete com.apple.mail UserHeaders
```
