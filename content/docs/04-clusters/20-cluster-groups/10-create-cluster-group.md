---
title: "Create and Manage Cluster Groups"
metaTitle: "Create and Manage Palette Cluster Group"
metaDescription: "Learn how to create and manage Palette Cluster Groups"
hideToC: false
fullWidth: false
---

import Tabs from 'shared/components/ui/Tabs';
import InfoBox from 'shared/components/InfoBox';
import WarningBox from 'shared/components/WarningBox';
import PointsOfInterest from 'shared/components/common/PointOfInterest';
import Tooltip from "shared/components/ui/Tooltip";

# Create a Cluster Group

Use the instructions below to create a cluster group.



## Prerequisites

* To create a Palette Host Cluster Group, you need to deploy a healthy running [Palette host cluster](/clusters). 


* The host clusters must match the network endpoint type of the cluster group.


## Enablement

1. Log in to [Palette](https://console.spectrocloud.com).


2. Navigate to the left **Main Menu** and select **Cluster Groups**.


2. Click **+New Cluster Groups** to create a new cluster group and provide the following information to the creation wizard.


   * **Basic Information: **

  |         Parameter           | Description  |
  |-------------------------------|-----------------|
  |Group Name                 | A name for the cluster group.|
  |Description (optional)   | Description of the group, if any. | 
  |Tag (optional)               | Assign tags to the cluster group.|


3. Select **Next** to continue.



4. Use the **Select clusters** drop-down menu to add available host clusters. 
 
<InfoBox>

 Only host clusters created under the current scope are available to add to a cluster group. You can add host clusters created under the current project or at the tenant scope. You cannot add host clusters that were created in another project scope.


</InfoBox>

5. Click **Next** once you have added all the host clusters you wish to include.


6. Review the configuration options for **Host Clusters Config** and **Virtual Clusters Config**.


#### Cluster Group Configurations

    
|**Host Cluster Config**        |        **Description**                    |
|--------------------------------------|-------------------------------------------|
|Oversubscription (%):                 | The allowed oversubscription for cluster in terms of resources. Default is 120%.|
|Cluster endpoint type:                | Load balancer or Ingress.|
|Host DNS:                             | If the selected cluster endpoint is **Ingress**, then for each selected host cluster provide the host DNS pattern. Ensure that a wildcard DNS record exists that maps the provided host pattern to the ingress controller load balancer for this cluster. Check out the [Setup Ingress](/clusters/cluster-groups/ingress-cluster-group) for additional guidance.|


#### Palette Virtual Cluster Configuration

The configuration applied to all virtual clusters launched into the host clusters. Use the **Advanced Config** for further customization. The request sizing applies to the maximum amount of resources a virtual cluster is allowed to claim.

<br />

|**Palette Virtual Cluster Resource ** | **Default**   |**Minimum Limit**|
|------------------------------|-------------------|-----------------|
|CPU (per request)             | 6                 | 4               |
| Memory (per request)         | 8 GiB             | 4 GiB           |
| Storage (per request)        | 10 GiB            | 2 GiB           |


<WarningBox>

A virtual cluster requires a minimum of 4 CPU, 4 GiB of memory, and 2 Gib of storage to launch successfully. The default settings in the cluster group virtual cluster configuration YAML file has the following values:

```yaml
vcluster
  resources:
    limits:
      cpu: 1000m
      memory: 1Gi
      ephemeral-storage: 1Gi
    requests:
      cpu: 200m
      memory: 256Mi
      ephemeral-storage: 128Mi
```

Increasing the limit and request values could result in a virtual cluster requiring more resources than the default values of 4 CPU, 4 GiB of memory, and 2 Gib of storage.

</WarningBox>

To enable virtual clusters for OpenShift, review the OpenShit [instructions below](#enable-virtual-cluster-for-openshift). 


7. Click **Next** to complete the cluster group creation process.


8. Click **Finish Configuration**.

## Validation

To review your cluster group, navigate to the left **Main Menu** and select **Cluster Groups**. Your newly created cluster group is now displayed and ready for use. 


# Manage your Cluster Group

Once the cluster group is created, the day two operations can be performed from the cluster group's **Settings** options. To access cluster group settings, navigate to the left **Main Menu** and select **Cluster Groups**. Select a cluster group, and click the **Settings** button.


## Add a Host Cluster to the Group

You can add additional host clusters to a cluster group. Navigate to the left **Main Menu** and select **Cluster Groups**. Select the cluster group you want to add additional host clusters. Click on the **+ Add Host Cluster**. Select the desired host clusters and verify the oversubscription and cluster endpoint type settings.

## Delete your Cluster Group

To delete a cluster group, navigate to the left **Main Menu** and select **Cluster Groups**. Select the cluster group you want to review or modify the settings. Click on the **Settings** button. Select **Delete Cluster**, enter the cluster name, and confirm the delete operation.


# Enable Virtual Clusters for OpenShift 

To deploy a virtual cluster on OpenShift:


1. Create a new Cluster Group or edit an existing one and click **Settings**.


2. Select **Settings** in the **Cluster Group Settings** pane.


3. In the **Advanced Config** file, locate the securityContext section.


4. Comment out these lines: 

    * ``fsGroup``
    * ``runAsGroup``
    * ``runAsUser``
    
4. Set `openshift.enable:` to  `true`.  


5. Verify these default parameter values are set as follows:   

    * ``allowPrivilegeEscalation: false``
    * ``capabilities.drop: [all]``
    * ``runAsNonRoot: true``

The following example shows the required configuration for OpenShift.

**Example**


```yaml 
#fsGroup: 12345
securityContext:
  allowPrivilegeEscalation: false
  capabilities:
    drop:
    - all
  
  #runAsGroup: 12345
  #runAsUser: 12345
  runAsNonRoot: true

openshift:
  enable: true
```



<br />
