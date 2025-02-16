---
title: Adobe Experience Platform Web SDK FAQ
description: Get answers to frequently asked questions about the Adobe Experience Platform Web SDK.
exl-id: 6ddb4b4d-c9b8-471a-bd2e-135dc4202876
---
# Frequently asked questions

This guide provides answers to questions that are often asked about the Adobe Experience Platform Web SDK.

## What is Adobe Experience Platform Web SDK?

Adobe Experience Platform Web SDK is a client-side JavaScript library that allows customers of Adobe Experience Cloud to interact with the various services in the Experience Cloud.

It sends data in a solution-agnostic way (XDM) to Adobe Experience Platform Edge Network, which then maps the data to solution specific formats and destinations and sends it in real time. 

**More information** 
[Adobe Summit presentation](https://www.adobe.com/summit/2020/with-alloy-js-never-tag-for-an-evar-or-mbox-again.html)

## How does Adobe Experience Platform Web SDK differ from previous solutions?

### Prior to Adobe Experience Platform SDK

Currently, you have to deploy different JavaScript libraries based on each individual solution.

* Each solution has its own JavaScript library, schema, and domain.
* None of these libraries were built to work with each other.
* Cross-solution and Adobe Experience Platform use cases require these disparate libraries to be interdependent, causing deployment friction.

Although Adobe Experience Platform Launch makes it as easy as possible to deploy and manage these libraries, there are still issues with:

* Library size (too much Adobe code on a page)
* Performance (sites take too long to load)
* Multiple calls for a single use case 
* Waiting for ECID return before personalization calls (causes lag)
* Fractured data collection (what is an evar?)
* Schema confusion between solutions (A4T)
* Lots of other less optimal things

Also, there is currently no JavaScript library that sends data directly to Adobe Experience Platform.

### With Adobe Experience Platform Web SDK

The new Web SDK sends data for the following solutions to a single destination (Adobe Experience Platform Edge Network) and solves for the most common aforementioned solution use cases. 

* Adobe Analytics
* Adobe Audience Manager
* Adobe Target
* Visitor ID
* Adobe Experience Platform 

Other solutions will follow later this year. 

Adobe Experience Platform Web SDK can also send data directly to Adobe Experience Platform. This data is in XDM and is mapped to the server-side solution schema. 

## What is the value of this new Web SDK?

**Performance:** The web SDK is smaller than using all of the current Adobe libraries and provides significantly faster page loads. 

**Simplicity:** The combination of XDM, Web SDK, Experience Platform Launch, Experience Edge, Adobe Experience Cloud solutions, and Adobe Experience Platform creates an easy-to-understand and simple-to-follow data collection story. 

* **XDM:** The solution-agnostic schema you use to send data to Adobe. No more tagging for evars or mboxes.
* **Adobe Experience Platform Web SDK:** Makes it easy to send and receive data to Adobe Experience Platform Edge Network. 
* **Experience Platform Launch:** Simplifies deployment and configuration of the Web SDK (and any other JavaScript tags) on a site.
* **Experience Edge:** Easily route the data to Adobe Experience Platform and solutions in the format they need.
* **Adobe Experience Platform and Adobe solutions:** Enable their value proposition.

**Control:** Because all of the data is using a single and connected stream of data, you can logically follow and control what the data looks like at every millisecond of its journey, to and from applications.

**Modern and ready for the future:** The Web SDK and its connection to the Experience Edge Network has enabled Adobe to significantly modernize how Adobe deals with data collection, personalization, consent and the future of 3rd party cookies. (It enables a first party domain, managed by Adobe.)

**Time-to-value:** Adobe has worked hard (and will continue) to make it as easy as possible to deploy the Web SDK via Experience Platform Launch and map client-side data to XDM.  After that work is done, all other Adobe solutions and Adobe Experience Platform services can be turned on or off server-side. For example, if you are using this for Adobe Analytics and you want to turn on Target or Experience Platform, you can simply flip a toggle on the Experience Edge configuration and light up those use cases. 

## What is Alloy?

Alloy is the code name for Adobe Experience Platform Web SDK. It is used within the SDK's source code and filename, though Adobe Experience Platform Web SDK is the official name.

## Do customers need to buy Adobe Experience Platform to use the Web SDK?

No. Any Adobe Digital Experience customer can use it. Totally free. Any customer wanting to use the Web SDK will be given access to create schemas and datasets in the Adobe Experience Platform UI.

## Who should use the Web SDK?

Adobe Experience Platform Web SDK has been developed for the following people:

* Adobe Experience Platform users

    If you need to send data directly from a device to Adobe Experience Platform, this is the officially recommended way. 

    Adobe is aware that using the Adobe Analytics connector is faster if the customer already has Adobe Analytics, but it is not the long-term strategy for data collection. 
    
* Adobe Experience Cloud solution customers

    New Adobe Analytics, Adobe Audience Manager, and Adobe Target customers should start with the new Web SDK and not use legacy libraries.

    Existing customers who want to get the most optimized implementation possible should use the new Web SDK. 


## How do I get access to start using Adobe Experience Platform Web SDK?

The Web SDK is currently available to the general public and can be used to send data to Adobe Experience Cloud products. The ability to send data to third-party solutions is coming in the near future. The SDK is free, is hosted by Adobe for free, and can be downloaded so you can host it on your own servers, if desired, for free. Platform Web SDK requires access to Platform Edge Network configurations and the Adobe Experience Platform XDM schema builder, in order for Adobe's servers to properly handle inbound data coming from the SDK. If you would like to get access, contact your Customer Success Manager (CSM) to start the request process.

## What use cases are currently supported by the Web SDK?

The Web SDK is quickly evolving. More use cases are being worked on. You can find the [list of use cases currently supported here.](https://github.com/adobe/alloy/projects/5)

## Do current customers have to retag their sites?

It depends. Adobe Experience Platform Web SDK can be deployed in two different styles. A future migration document will provide additional details.

* **Just another tag:** If the site is already tagged for solutions and you can't retag, but you want to send data to Adobe Experience Platform Edge Network for Experience Platform use cases or the upcoming Experience Platform Launch server-side features (see below), you can add the `alloy.js` tag to the site, where it works as "just another tag."

* **The one and only tag:** If you want to use the Web SDK for an Experience Cloud solution, you must use it for _all_ of the solutions on that page. For example, if your site is already tagged for Adobe Analytics and you want to use it for Target, you need to use it for both, as well as for any others in the future.  

In other words, if you decide to use Adobe Experience Platform Web SDK for non-solution use cases, you can tag the site with `alloy.js` and move on as if it's a new solution. If you want to use it for Adobe Analytics, Target, or Audience Manager, or for application use cases, you might have to remove any of the legacy code on your page. 

## Can I migrate the ECIDs when I start using Alloy so my website visitors don't start showing up as new visitors?

Yes, Adobe Experience Platform Web SDK provides an Identity Migration feature. Follow the instructions for ID migration in the [Platform Web SDK identity documentation](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=en#id-migration) for more details.

## How is the Web SDK different than Adobe Experience Platform Launch?

* **Experience Platform Launch** is the device code manager. Use it to more easily deploy the code. It is free and powerful.

* **Adobe Experience Platform Web SDK** is the official name of the new code that would be deployed by Experience Platform Launch for Adobe use cases. It is also free and powerful.

* **`alloy.js`** is the file name of the Adobe Experience Platform Web SDK code.

## Do I have to use Adobe Experience Platform Launch to deploy the Web SDK?

No. You can download the `alloy.js` file yourself.

However:

* Adobe Experience Platform Web SDK requires something called an Experience Edge configuration ID so the edge network can identify the stream and determine what to do with the data. This ID is created within Experience Platform Launch. This doesn't mean you have to use Experience Platform Launch to create properties or deploy the JavaScript code, but you do need to use Experience Platform Launch to create a configuration ID.

* Adobe Experience Platform Launch is not only the best available tag and SDK manager, it makes it very easy to deploy `alloy.js` and map data to XDM schemas. If you decide not to use Experience Platform Launch, you will have to manage deploying `alloy.js`, eventing, and mapping your data into XDM before sending it. This is a _much_ more difficult process than using Experience Platform Launch. 

* It is recommended that you use Experience Platform Launch to deploy `alloy.js`, even if it's the only tag you use it for. 

## What is "Adobe Experience Platform Launch Server Side?

Later in 2020, Experience Platform Launch will release server-side forwarding features. If you use our SDKs and send XDM to the Experience Edge, these new features will allow you to install new server-side extensions and map that data to anything--and send it anywhere--from our edge network. Think of it as “data collection as a service.”  This will be available for a cost, as well as being bundled as part of Adobe Experience Platform. 

## What is a CNAME or First Party Domain and why does it matter?

More information about a CNAME is available in the [Adobe documentation](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/cname.html)

## Does the Adobe Experience Platform Web SDK use cookies? If so, what cookies does it use?

Yes, currently the Web SDK uses anywhere between 1-4 cookies depending on your implementation. Below is a list of the 4 cookies that you might see with the Web SDK and the way that they are used: 

**kndct_orgid_identity:** The identity cookie is used to store the ECID, as well as some other information related to the ECID.

**kndctr_orgid_consent:** This cookie stores the user's consent preference for the website. 

**kndctr_orgid_personalization:** This cookie includes session information that Adobe Target uses to personalize webpages. 

**kndctr_orgid_consentcheck:** This session-based cookie signals the server to look up the consent preferences server side.

## Where can I get more info about Adobe Experience Platform Web SDK?

* [Documentation](https://docs.adobe.com/content/help/en/experience-platform/edge/home.html)
* [Source Code](https://github.com/adobe/alloy)
