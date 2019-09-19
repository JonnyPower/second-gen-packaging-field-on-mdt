# Issue with 2GP and Custom Metadata Types

Repository built for Chatter post as below:

> Started packaging a downstream manged second gen package, which adds fields to some custom metadata types that are defined upstream - all in the same namespace.
>
> Packaging fails with: "You can't create custom fields on installed managed custom metadata types."
>
> Is this an intentional limitation? Within the same namespace it would seem normal to add fields in downstream packages, even if the custom metadata type is "managed" and added by an upstream package.

https://partners.salesforce.com/_ui/core/chatter/groups/GroupProfilePage?g=0F9300000001s8i&fId=0D53A00004a2blQ

# Building package-01

```
λ sfdx force:package:version:create -p jpower-case-package-01 -k foobar
Package version creation request is InProgress. Run "sfdx force:package:version:create:report -i 08c0c000000k9dOAAQ" to query for status.
```

```
λ sfdx force:package:version:create:report -i 08c0c000000k9dOAAQ
=== Package Version Create Request
NAME                           VALUE
─────────────────────────────  ─────────────────────────────────────────────────────────────────────────────────
ID                             08c0c000000k9dOAAQ
Status                         Success
Package Id                     0Ho0c000000Kyk9CAC
Package Version Id             05i0c000000fxTiAAI
Subscriber Package Version Id  04t0c000001Ze6NAAS
Tag
Branch
Created Date                   2019-09-19 16:50
Installation URL               https://login.salesforce.com/packaging/installPackage.apexp?p0=04t0c000001Ze6NAAS
```

# Error when building package-02

```
λ sfdx force:package:version:create:report -i 08c0c000000k9dTAAQ
=== Package Version Create Request
NAME                           VALUE
─────────────────────────────  ──────────────────
ID                             08c0c000000k9dTAAQ
Status                         Error
Package Id                     0Ho0c000000KykECAS
Package Version Id
Subscriber Package Version Id
Tag
Branch
Created Date                   2019-09-19 16:52
Installation URL
=== Errors
(1) Foo__mdt.Bar__c: You can't create custom fields on installed managed custom metadata types.
```