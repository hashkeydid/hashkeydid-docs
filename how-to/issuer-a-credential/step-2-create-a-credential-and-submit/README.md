---
description: >-
  After you deploy your own contract, you can create your credentials on it.
  This section will show you how to create the credentials and submit.
---

# Step 2: Create a credential and submit

First, go to the **Credential MGT page** in the issuer management.

<figure><img src="../../../.gitbook/assets/image (12) (1).png" alt=""><figcaption></figcaption></figure>

Then click '**Create Credential**'.

Choose the contract that you created before, we now only support PlatON and Klaytn.\
Then click '**Next**', it will lead you to the creating page.

<figure><img src="../../../.gitbook/assets/image (7).png" alt=""><figcaption><p>Create Credential - choose a contract</p></figcaption></figure>

On the creating page, you need to upload the credential file and fill in the corresponding fields. Below is an instruction about how to fill the form correctly.

![](https://lh5.googleusercontent.com/sQI4UwcZpc8bbRbi9rs5zxa6OQLumeFU5S7Ir3YGfmNZ\_ixxmG4s55YiS9Hb\_iYB3m4oREiWANF67II5Nq4F6qytcTQzZJveOWCaN4ZJXWdKLg9tCz5mCQOzfaQBuHtpgkXnUH0YX7mvyEgaeGDnfNJWfoKjj3ure71Sr4zth5KzqXktHe4t3xbiHkzCrQ)



Instructions for each field:

| Field name              | Field description                                                                                                                                                                                                                                                                       |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Credential File         | Upload your credential file. The file formats supported are JPG, PNG and GIF, with a maximum size of 4MB.                                                                                                                                                                               |
| Credential Name         | The name of your credential. Supports a maximum of 80 characters.                                                                                                                                                                                                                       |
| Custom URL              | <p>A specific URL for your credential.</p><p>This URL is unique for the credential and cannot be duplicated with other credentials on the platform. An error will be reported if the same URL is encountered.</p>                                                                       |
| Type                    | The type of your credential, we now only support OST(non-transferable).                                                                                                                                                                                                                 |
| Credential introduction | Describe the credential in detail.Like its background, story, utility, etc. Supports a maximum of 500 characters.                                                                                                                                                                       |
| Issue amount            | <p>There will be two options: limited and unlimited amounts.</p><p>If you set the amount limit, you need to pay gas fee when you issue the credential.</p>                                                                                                                              |
| Gas fee payer           | <p>When users claim this credential, the roles will be responsible to pay gas fee for the claiming process. </p><p></p><p>There will be two options: Users and HashKey DID Platform. </p><p><strong>Please ensure you have communicated with DID platform for this option.</strong></p> |
| Claim period            | The time interval during which the users can claim the credential.                                                                                                                                                                                                                      |
| Credential claim rules  | Set up the credential claim rules. You can add up to 10 claim rules per Credential. please refer to '[Set claim rules](claim-rules.md)' for details.                                                                                                                                    |



You can click '**Save**' to save your current progress of the credential creation. And then find it on the **Drafts** page.

You can click '**Submit**' to submit your credential infomation. We will then review it.

