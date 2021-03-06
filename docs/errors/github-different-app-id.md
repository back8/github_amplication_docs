---
id: github-different-app-id
title: Merge conflicts with a different app
sidebar_label: Merge conflicts with a different app
slug: /errors/github-different-app-id
---

# Merge conflicts with a different app

## Message

> The code in the linked GitHub repo was generated from a different app. It may cause conflicts when merged with code generated from the current app.

## What went wrong?

The code generated by Amplication includes a file named **ampconfig.json** with information about the app from which the code was generated.

```json
{
  "dataServiceGeneratorVersion": "0.4.0",
  "appInfo": {
    "name": "My Catering Service",
    "description": "",
    "version": "wi2ip2h2",
    "id": "ckl0nif3y06453wj7mn5lqx711",
    "url": "https://app.amplication.com/ckl0nif3y06453wj7mn5lqx711"
  }
}
```

The ID of the app that is recorded in the file is different than the ID of the app you are currently working on.

This happens if you connect your app to a GitHub repo that already includes code generated by another app.

## What to do?

### When working on a new app

If you are working on a new app, and accidentally connected it to a repo with an existing code, the best thing to do is to connect the app to a new repo.

### When working on an existing app

If you are working on an existing app, and your code in GitHub includes custom code that you don't want to lose, it is first best to identify which other app is connected to the repository. You can do so by looking at the **ampconfig.json** file in the root folder of the repository.

In case you decided to keep using the existing repo, you can continue with committing your changes.

Amplication will create a new Pull Request in the repository and you will be able to compare the differences between the new Pull Request and the current state of the repo before merging the changes.

In case you decided to merge the changes, the **ampconfig.json** file will be updated with the correct values related to the current app.

:::tip
Amplication will never write directly to the main branch on the repo. You always get the chance to review the Pull Request before merging the changes.
:::
