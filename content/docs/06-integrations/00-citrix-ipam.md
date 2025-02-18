---
title: 'Citrix IPAM'
metaTitle: 'Citrix IPAM'
metaDescription: 'Citrix IPAM Load Balancer pack in Spectro Cloud'
hiddenFromNav: true
type: "integration"
category: ['load balancers']
logoUrl: 'https://registry.spectrocloud.com/v1/lb-citrix-adc/blobs/sha256:17f8ebc0dc69d329a39e5d27fc0ce3574034d18ab1776fabda396c5403b0bd86?type=image/png'
---

import Tabs from 'shared/components/ui/Tabs';
import WarningBox from 'shared/components/WarningBox';
import InfoBox from 'shared/components/InfoBox';
import PointsOfInterest from 'shared/components/common/PointOfInterest';
import Tooltip from "shared/components/ui/Tooltip";


# Citrix IPAM and Ingress controller

The integration helps with IP address management and provides load balancing capabilities for external services deployed on Kubernetes, especially for on-premise deployments.

## Versions Supported

<Tabs>
<Tabs.TabPane tab="1.7.x" key="1.7.x">

* **1.7.6**

</Tabs.TabPane>
</Tabs>

## Components

Integration deploys the following components:

* IPAM controller.
* Ingress controller.

## Notable parameters

| Name | Default Value | Description |
| --- | --- | --- |
| vip.addresses | | The IP address range to be used for external Services |
| vip.namespace | citrix-system | The namespace for IPAM controller |
| citrix-k8s-ingress-controller.namespace | citrix-system | The namespace for Citrix Ingress controller |
| citrix-k8s-ingress-controller.clusterPrefix | | The prefix for resources to load balance applications from multiple clusters |
| citrix-k8s-ingress-controller.nsip | | The IP address of the Citrix ADC |
| citrix-k8s-ingress-controller.username | | Username to connect to Citrix IDC |
| citrix-k8s-ingress-controller.password | | Password to connect to Citrix IDC |

## References

[Citrix IPAM Controller](https://developer-docs.citrix.com/projects/citrix-k8s-ingress-controller/en/latest/crds/vip/)

[Citrix Ingress controller](https://developer-docs.citrix.com/projects/citrix-k8s-ingress-controller/en/latest/network/type_loadbalancer/#expose-services-of-type-loadbalancer-using-an-ip-address-from-the-citrix-ipam-controller)
