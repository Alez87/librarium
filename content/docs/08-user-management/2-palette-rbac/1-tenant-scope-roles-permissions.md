---
title: "Tenant Scope Roles and Permissions"
metaTitle: "Tenant Roles"
metaDescription: "The list of Global Tenant Roles under Tenant Scope"
icon: ""
hideToC: false
fullWidth: false
---

import Tabs from 'shared/components/ui/Tabs';
import WarningBox from 'shared/components/WarningBox';
import InfoBox from 'shared/components/InfoBox';
import PointsOfInterest from 'shared/components/common/PointOfInterest';
import Tooltip from "shared/components/ui/Tooltip";

# Global Tenant Scope

Tenant is an isolated workspace within the Palette Console. Users and teams with specific roles can be associated with the [tenants](/glossary-all#organization) and [projects](/glossary-all#project) you create.

Palette has adopted the security principle of least privilege. Each user is assigned a role and permissions, which apply to the scopes, resources, and resourceKey. The Permissions format is `resourceKey.operation`, where resourceKey refers to resource or the API functionality, and Operation refers to the permitted action or activity.

To view the list of the predefined roles and permissions, ensure you are in the project scope **Tenant**. Next, navigate to the left **Main Menu** and click on  **Tenant Settings** > **Roles**, and you will find the list of **Global Roles**. If you need to extend permissions, create a custom role by using  the [Create Role](/user-management/palette-rbac#createcustomroleinpalette) option. 

Below is the list of Roles and Permissions that already predefined for the Global Tenant Scope.

<br />

<InfoBox>

All users can view tags assigned to a resource. In technical terms, all users inherit the permission `tag.get` by default.

</InfoBox>

<br />

# Tenants 
----------------------------

|Role Names   | Description  |
|---|---|
|Tenant Admin  |Allows the user to create projects and manage projects within the tenant, covered under all operations related to projects|
|Tenant Viewer| Provides a read only access to all the project resources|
|Tenant Project Admin|The role with complete access to an existing project|

The table enlists the role wise resourceKeys and Operations that are predefined under the Global Tenant Scope:

<br />
<br />

<Tabs>

<Tabs.TabPane tab="Tenant Admin" key="Tenant Admin">

<br />

## Tenant Admin

<br / >
<table>
    <tr>
        <td width="400"><b>resourceKeys</b></td>
        <td><b>Operations</b></td>
    </tr>
</table>
<hr />

|                    | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| ------------------ | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **apiKey**         | √          | √          | √       | √        | √          |            |             |            |             |
| **audit**          |            |            | √       | √        |            |            |             |            |             |
| **cloudaccount**   | √          | √          | √       | √        | √          |            |             |            |             |
| **cloudconfig**    | √          | √          | √       | √        | √          |            |             |            |             |
| **cluster**        | √          | √          | √       | √        | √          | √          |             |            |             |
| **clusterProfile** | √          | √          | √       | √        | √          |            | √           |            |             |
| **clusterRbac**    | √          | √          | √       | √        | √          |            |             |            |             |
| **dnsMapping**     | √          | √          | √       | √        | √          |            |             |            |             |
| **edgehost**       | √          | √          | √       | √        | √          |            |             |            |             |
| **location**       | √          | √          | √       | √        | √          |            |             |            |             |
| **machine**        | √          | √          | √       | √        | √          |            |             |            |             |
| **macro**          | √          | √          | √       | √        | √          |            |             |            |             |
| **packRegistry**   | √          | √          | √       | √        | √          |            |             |            |             |
| **privateGateway** | √          | √          | √       | √        | √          |            |             |            |             |
| **project**        | √          | √          | √       | √        | √          |            |             |            |             |
| **role**           | √          | √          | √       | √        | √          |            |             |            |             |
| **sshKey**         | √          | √          | √       | √        | √          |            |             |            |             |
| **team**           | √          | √          | √       | √        | √          |            |             |            |             |
| **tag**            |            |            |         |          | √          |            |             |            |             |
| **user**           | √          | √          | √       | √        | √          |            |             |            |             |
| **workspace**      | √          | √          | √       | √        | √          |            |             | √          | √           |

<br />
<br />
<br />

</Tabs.TabPane>
<Tabs.TabPane tab="Tenant Viewer" key="Tenant Viewer Role">


## Tenant Viewer

<br / >
<table>
    <tr>
        <td width="400"><b>resourceKeys</b></td>
        <td><b>Operations</b></td>
    </tr>
</table>
<hr />

 |                    | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
 | ------------------ | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
 | **apiKey**         |            |            | √       | √        |            |            |             |            |             |
 | **audit**          |            |            | √       | √        |            |            |             |            |             |
 | **cloudaccount**   |            |            | √       | √        |            |            |             |            |             |
 | **cloudconfig**    |            |            | √       | √        |            |            |             |            |             |
 | **cluster**        |            |            | √       | √        |            |            |             |            |             |
 | **clusterProfile** |            |            | √       | √        |            |            |             |            |             |
 | **clusterRbac**    |            |            | √       | √        |            |            |             |            |             |
 | **dnsMapping**     |            |            | √       | √        |            |            |             |            |             |
 | **edgehost**       |            |            | √       | √        |            |            |             |            |             |
 | **location**       |            |            | √       | √        |            |            |             |            |             |
 | **machine**        |            |            | √       | √        |            |            |             |            |             |
 | **macro**          |            |            | √       | √        |            |            |             |            |             |
 | **packRegistry**   |            |            | √       | √        |            |            |             |            |             |
 | **privateGateway** |            |            | √       | √        |            |            |             |            |             |
 | **project**        |            |            | √       | √        |            |            |             |            |             |
 | **role**           |            |            | √       | √        |            |            |             |            |             |
 | **sshKey**         |            |            | √       | √        |            |            |             |            |             |
 | **team**           |            |            | √       | √        |            |            |             |            |             |
 | **user**           |            |            | √       | √        |            |            |             |            |             |
 | **workspace**      |            |            | √       | √        |            |            |             |            |             |


</Tabs.TabPane>
<Tabs.TabPane tab="Tenant Project Admin" key="Tenant Project Admin">

<br />

## Tenant Project Admin 

<br / >
<table>
    <tr>
        <td width="400"><b>resourceKeys</b></td>
        <td><b>Operations</b></td>
    </tr>
</table>
<hr />

|                    | **Create** | **Get** | **Delete** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| ------------------ | ---------- | ------- | ---------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **apiKey**         |            | √       |            | √        |            |            |             |            |             |
| **audit**          |            | √       |            | √        |            |            |             |            |             |
| **cloudaccount**   | √          | √       | √          | √        | √          |            |             |            |             |
| **cloudconfig**    | √          | √       | √          | √        | √          |            |             |            |             |
| **cluster**        | √          | √       | √          | √        | √          | √          |             |            |             |
| **clusterProfile** | √          | √       | √          | √        | √          |            | √           |            |             |
| **clusterRbac**    | √          | √       | √          | √        | √          |            |             |            |             |
| **dnsMapping**     | √          | √       | √          | √        | √          |            |             |            |             |
| **edgehost**       | √          | √       | √          | √        | √          |            |             |            |             |
| **location**       | √          | √       | √          | √        | √          |            |             |            |             |
| **machine**        | √          | √       | √          | √        | √          |            |             |            |             |
| **macro**          | √          | √       | √          | √        | √          |            |             |            |             |
| **packRegistry**   | √          | √       | √          | √        | √          |            |             |            |             |
| **privateGateway** | √          | √       | √          | √        | √          |            |             |            |             |
| **project**        | √          | √       | √          | √        | √          |            |             |            |             |
| **sshKey**         | √          | √       | √          | √        | √          |            |             |            |             |
| **tag**            |            |         |            |          | √          |            |             |            |             |
| **workspace**      | √          | √       | √          | √        | √          |            |             | √          | √           |


</Tabs.TabPane>
</Tabs>

<br />
<br />

## Cluster Profile 

----------------------------

|Role Names   | Description  |
|---|---| 
|Tenant Cluster Profile Admin  | A role which has complete access to all the `Cluster Profile` related operations|

|                    | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| ------------------ | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **clusterProfile** | √          | √          | √       | √        | √          |            | √           |            |             |
| **macro**          | √          | √          | √       | √        | √          |            |             |            |             |
| **packRegistry**   |            |            | √       | √        |            |            |             |            |             |
| **tag**            |            |            |         |          | √          |            |             |            |             |
<br />
<br />
<br />

## Tenant Role 

----------------------------

|Role Names   | Description  |
|---|---|
|Tenant Role Admin  | A role which has complete access to all the `Role` related perations  |

|          | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| -------- | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **role** | √          | √          | √       | √        | √          |            |             |            |             |


<br />
<br />
<br />

## Tenant Team

----------------------------

|Role Names   | Description  |
|---|---|
|Tenant Team Admin | A role which has complete access to all the `Team` related operations  |

|            | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| ---------- | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **apiKey** |            |            | √       | √        |            |            |             |            |             |
| **audit**  |            |            | √       | √        |            |            |             |            |             |
| **team**   | √          | √          | √       | √        | √          |            |             |            |             |
| **user**   |            |            | √       | √        |            |            |             |            |             |


<br />
<br />
<br />

## Tenant User

----------------------------

|Role Names   | Description  |
|---|---|
|Tenant User Admin Role|A role which has complete access to all the `User` related operations|



|            | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| ---------- | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **apiKey** | √          | √          | √       | √        | √          |            |             |            |             |
| **audit**  |            |            | √       | √        |            |            |             |            |             |
| **user**   | √          | √          | √       | √        | √          |            |             |            |             


<br />


# Tenants Cluster Group
----------------------------

|Role Names   | Description  |
|---|---|
|Tenants Cluster Group Admin |Allows the user to create and manage cluster groups within the tenant, covered under all operations related to cluster groups|
|Tenants Cluster Group Editor|The role can perform edit operations related to a cluster group, but the user is not able to create or delete a cluster group|
|Tenants Cluster Group Viewer|Provides a read only access to all the cluster group resources|

The table lists role resourceKeys and operations that are predefined under the Global Tenant Scope:

<br />
<br />

<Tabs>

<Tabs.TabPane tab="Tenants Cluster Group Admin" key="Tenant Admin">

<br />

## Tenant Cluster Group Admin

<br / >
<table>
    <tr>
        <td width="400"><b>resourceKeys</b></td>
        <td><b>Operations</b></td>
    </tr>
</table>
<hr />

|                    | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| ------------------ | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **cluster**        |            |            | √       | √        |            |            |             |            |             |
| **clusterGroup**   | √          | √          | √       | √        | √          |            |             |            |             |
| **tag**            |            |            |         |          | √          |            |             |            |             |


<br />
<br />
<br />

</Tabs.TabPane>
<Tabs.TabPane tab="Tenants Cluster Group Editor" key="Tenants Cluster Group Editor Role">


## Tenant Cluster Group Editor

<br / >
<table>
    <tr>
        <td width="400"><b>resourceKeys</b></td>
        <td><b>Operations</b></td>
    </tr>
</table>
<hr />

|                    | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| ------------------ | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **cluster**        |            |            | √       | √        |            |            |             |            |             |
| **clusterGroup**   |            |            | √       | √        | √          |            |             |            |             |
| **tag**            |            |            |         |          | √          |            |             |            |             |



</Tabs.TabPane>
<Tabs.TabPane tab="Tenants Cluster Group Viewer" key="Tenant Project Viewer">

<br />

## Tenant Cluster Group Viewer

<br / >
<table>
    <tr>
        <td width="400"><b>resourceKeys</b></td>
        <td><b>Operations</b></td>
    </tr>
</table>
<hr />

|                    | **Create** | **Delete** | **Get** | **List** | **Update** | **Import** | **Publish** | **Backup** | **Restore** |
| ------------------ | ---------- | ---------- | ------- | -------- | ---------- | ---------- | ----------- | ---------- | ----------- |
| **cluster**        |            |            | √       | √        |            |            |             |            |             |
| **clusterGroup**   |            |            | √       | √        |            |            |             |            |             |


</Tabs.TabPane>
</Tabs>

<br />


