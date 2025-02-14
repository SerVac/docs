# View L7 load balancer statistics

## View general statistics {#summary}

{{ alb-name }} has general load balancer statistics available without itemization by associated resources.

To view the statistics:

1. In the [management console]({{ link-console-main }}) select the folder where the load balancer was created.
1. Select **{{ alb-name }}**.
1. Click on the name of the load balancer you need.
1. Go to the **Monitoring** tab.
1. Select the time period for which you wish to view statistics.

## View statistics itemized by resources {#resources}

{{ monitoring-name }} provides load balancer runtime statistics itemized by associated load balancer resources, such as HTTP routers, virtual hosts, routes and so on.

To view the statistics:

1. In the [management console]({{ link-console-main }}) select the folder where the load balancer was created.

1. Select **{{ alb-name }}**.

1. Click on the name of the load balancer you need.

1. Go to the **Monitoring** tab.

1. Click **Open in Monitoring**.

1. Select the resources for which you wish to view statistics:
   * **HTTP Router**: [HTTP router](../concepts/http-router.md).
   * **Virtual Host**: HTTP router virtual host.
   * **Route**: Virtual host route.
   * **Backend Group**: [Group of backends](../concepts/backend-group.md).
   * **Backend**: Backend.
   * **Zone**: Availability zone where the load balancer nodes are located. For more information, see [{#T}](../concepts/application-load-balancer.md#lb-location).

   If `*` is the value selected in the field, the dashboard will display aggregate statistics for all resources of the relevant type, such as all HTTP routers.

1. Select the time period for which you wish to view statistics.

1. If you need to configure the dashboard to autoupdate, click ![](../../_assets/monitoring/autorefresh.svg).