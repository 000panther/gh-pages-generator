---
title: "Hardening firebase"
date: 2023-05-17T19:33:18+01:00
tags: [Development,Firebase,Security]
---

Firebase offers unparalelled development speed, handling all the nitty gritty details that you might not want to think about when getting a product to market. It provides hosting, database, storage, cloud functions and much more functionality.

But by default a firebase installation is not focussed on security but developer productivity. If you have an app that has some security requirements you should think about hardening your installation. This can be done by adjusting some settings in the underlying Google Cloud Project.

# General Settings

## API Keys

Firebase uses an API key to access services on your applications behalf. In the default settings this API Key works on every domain - so anybody could read your and use your public data from any page, using your firebase credits.

To remedy:
 * Go to the [APIs and Services -> Credentials](https://console.cloud.google.com/apis/credentials) page in console.cloud.google.com
 * Under API Keys you should see "Browser Key (auto created by Firebase)"
 * Setup an Application Restriction e.g. for Websites only allow your domain
 * Limit the Key to the APIs you actually use, in my case
  * Cloud Firestore API
  * Cloud Functions API
  * Cloud Storage for Firebase API
  * Firebase Installations API
  * Firebase Remote Config API
  * Identity Toolkit API
  * Token Service API 


# Hosting

# Storage

# Cloud Functions

# Firebase

