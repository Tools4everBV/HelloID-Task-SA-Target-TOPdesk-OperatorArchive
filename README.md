# HelloID-Task-SA-Target-TOPdesk-OperatorArchive

## Prerequisites

- [ ] TOPdesk API Username and Key
- [ ] User-defined variables: `topdeskBaseUrl`, `topdeskApiUsername` and `topdeskApiSecret` created in your HelloID portal.

## Description

This code snippet will archive an existing operator within TOPdesk and executes the following tasks:

1. Define a hash table `$formObject`. The keys of the hash table represent the properties necessary to archive an existing operator within `TOPdesk`, while the values represent the values entered in the form.

> To view an example of the form output, please refer to the JSON code pasted below.

```json
{
    "id": "634206ca-6907-4914-8509-da55cfd8b35d",
    "displayName": "Doe, John van der",
    "archivingReasonId" : "73736b19-a69e-5e6b-b6af-ddc655fead0c"
}
```

> :exclamation: It is important to note that the names of your form fields might differ. Ensure that the `$formObject` hash table is appropriately adjusted to match your form fields.
> [See the TOPdesk API Docs page](https://developers.topdesk.com/explorer/?page=supporting-files#/Operators/patchArchiveOperator)

2. Creates authorization headers using the provided API key and secret.

3. archive an existing operator using the: `Invoke-RestMethod` cmdlet. The hash table called: `$formObject` is passed to the body of the: `Invoke-RestMethod` cmdlet as a JSON object.