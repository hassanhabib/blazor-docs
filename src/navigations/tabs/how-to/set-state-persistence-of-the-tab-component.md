---
title: "Set state persistence of the Tab component"
component: "Tab"
description: "This example demonstrates how to retain the current model value in the browser cookies for state maintenance of the Blazor Tab component."
---

# Set state persistence

State persistence allows the Tab to retain the current modal value in the browser cookies for state maintenance. This action is handled through the [EnablePersistence](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor~Syncfusion.Blazor.Navigations.SfTab~EnablePersistence.html) property which is set to false by default.
When it is set to true, some of the Tab component model values will be retained even after refreshing the page.

> Tab **ID** is essential to set state persistence .

The following sample demonstrates how to set state persistence of the Tab component.

```csharp
@using Syncfusion.Blazor.Navigations

<SfTab ID="Tab" Width="600px" EnablePersistence="true" >
    <TabItems>
        <TabItem Content="@Content1">
            <ChildContent>
                <TabHeader Text="Twitter"></TabHeader>
            </ChildContent>
        </TabItem>
        <TabItem Content="@Content2">
            <ChildContent>
                <TabHeader Text="Facebook"></TabHeader>
            </ChildContent>
        </TabItem>
        <TabItem Content="@Content3">
            <ChildContent>
                <TabHeader Text="WhatsApp"></TabHeader>
            </ChildContent>
        </TabItem>
    </TabItems>
</SfTab>

@code {
    public string Content1 = "Twitter is an online social networking service that enables users to send and read short 140-character " +
            "messages called 'tweets'. Registered users can read and post tweets, but those who are unregistered can only read " +
            "them. Users access Twitter through the website interface, SMS or mobile device app Twitter Inc. is based in San " +
            "Francisco and has more than 25 offices around the world. Twitter was created in March 2006 by Jack Dorsey, " +
            "Evan Williams, Biz Stone, and Noah Glass and launched in July 2006. The service rapidly gained worldwide popularity, " +
            "with more than 100 million users posting 340 million tweets a day in 2012.The service also handled 1.6 billion " +
            "search queries per day.";
    public string Content2 = "Facebook is an online social networking service headquartered in Menlo Park, California. Its website was " +
            "launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo " +
            "Saverin, Andrew McCollum, Dustin Moskovitz and Chris Hughes.The founders had initially limited the website  " +
            "membership to Harvard students, but later expanded it to colleges in the Boston area, the Ivy League, and Stanford " +
            "University. It gradually added support for students at various other universities and later to high-school students.";
    public string Content3 = "WhatsApp Messenger is a proprietary cross-platform instant messaging client for smartphones that operates " +
            "under a subscription business model. It uses the Internet to send text messages, images, video, user location and " +
            "audio media messages to other users using standard cellular mobile numbers. As of February 2016, WhatsApp had a user  " +
            "base of up to one billion,[10] making it the most globally popular messaging application. WhatsApp Inc., based in " +
            "Mountain View, California, was acquired by Facebook Inc. on February 19, 2014, for approximately US$19.3 billion.";
}
```