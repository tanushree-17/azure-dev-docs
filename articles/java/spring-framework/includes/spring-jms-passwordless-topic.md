#### [Passwordless (Recommended)](#tab/passwordless)

> [!NOTE]
> Azure Service Bus JMS supports using Azure Active Directory (Azure AD) to authorize requests to Service Bus resources. With Azure AD, you can use [Azure role-based access control (Azure RBAC)](/azure/role-based-access-control/overview) to grant permissions to a [security principal](/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object), which may be a user or an application service principal.

> [!IMPORTANT]
> Before you start, ensure that you've assigned the **Azure Service Bus Data Owner** role to the Azure AD account you're currently using. For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).

   ```properties
   spring.jms.servicebus.namespace=<ServiceBusNamespace>
   spring.jms.servicebus.topic-client-id=<ServiceBusSubscriptionID>
   spring.jms.servicebus.pricing-tier=<ServiceBusPricingTier>
   spring.jms.servicebus.passwordless-enabled=true
   ```

The following table describes the fields in the configuration:

| Field                                        | Description                                                                                                                                                                                                                  |
|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `spring.jms.servicebus.namespace`            | Specify the namespace you obtained in your Service Bus service instance from the Azure portal.                                                                                                                               |
| `spring.jms.servicebus.pricing-tier`         | Specify the pricing tier of your service bus. Supported values are *premium*, *standard*, and *basic*. Premium uses Java Message Service (JMS) 2.0, while standard and basic use JMS 1.0 to interact with Azure Service Bus. |
| `spring.jms.servicebus.topic-client-id`      | Specify the JMS client ID, which is your Service Bus subscription ID in the Azure portal.                                                                                                                                    |
| `spring.jms.servicebus.passwordless-enabled` | Specify whether to use passwordless.                                                                                                                                                                                         |

#### [Connection string](#tab/connection-string)

   ```properties
   spring.jms.servicebus.connection-string=<ServiceBusNamespaceConnectionString>
   spring.jms.servicebus.topic-client-id=<ServiceBusSubscriptionID>
   spring.jms.servicebus.pricing-tier=<ServiceBusPricingTier>
   ```

The following table describes the fields in the configuration:

| Field                                     | Description                                                                                                                                                                                                                  |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `spring.jms.servicebus.connection-string` | Specify the connection string you obtained in your Service Bus namespace from the Azure portal.                                                                                                                              |
| `spring.jms.servicebus.pricing-tier`      | Specify the pricing tier of your service bus. Supported values are *premium*, *standard*, and *basic*. Premium uses Java Message Service (JMS) 2.0, while standard and basic use JMS 1.0 to interact with Azure Service Bus. |
| `spring.jms.servicebus.topic-client-id`   | Specify the JMS client ID, which is your Service Bus subscription ID in the Azure portal.                                                                                                                                    |

---
