
# Azure API management

### Gateway:\
Routing to appropriate backends\
Security: Verifies API keys, tokens\
Enforces usage quotas and rate limits\
Transforms requests and responses as specified in policy statements\
Emits logs for observability

### Self hosted gateway
Packaged as a Linux based docker container

### Management plane:
- To Provision and Configure
- Define or import schemas from OpenAPI, WSDL, GraphQL
- Setup Policies like quotas or transformations
- Get insights from analytics
- Manage users


### Developer portal:
- Open source developer portal automatically generated
- Read API Documentation
- Create account and subscribe to get API keys
- Manage API keys

### API Management tiers
- Classic: Basic, standard, Premium
- V2: Basic, standard, Premium with enhanced virtual networking integration.
- Consumption: Designed for serverless workloads.
### APIs
- APIs represents set of operations available to developers
- Each API contains a reference to backend service, API operations are mapped to backend operations
### Products
- Products are how APIs are surfaced to developers
- Products can be open or protected.
- Open products can be consumed freely
- Protected products needs subscription

### Groups
- Groups are used to manage the visibility products to developers
- Developers: Authenticated developers
- Guests

### Developers
- Developers are user accounts in API Management service instance.

### Workspaces
- Workspaces allows decentralized API development for individual teams

### Policies
 - Set of statements executed sequentially on request or response
 - Example is ratelimiting.
 
 Policies structure:

 ```xml:
 <policies>
  <inbound>
    <!-- statements to be applied to the request go here -->
  </inbound>
  <backend>
    <!-- statements to be applied before the request is forwarded to 
         the backend service go here -->
  </backend>
  <outbound>
    <!-- statements to be applied to the response go here -->
  </outbound>
  <on-error>
    <!-- statements to be applied if there is an error condition go here -->
  </on-error>
</policies> 
 ```

Rate limiting

```xml:
<rate-limit calls="number" renewal-period="seconds"  retry-after-header-name="custom header name, replaces default 'Retry-After'" 
        retry-after-variable-name="policy expression variable name"
        remaining-calls-header-name="header name"  
        remaining-calls-variable-name="policy expression variable name"
        total-calls-header-name="header name">
    <api name="API name" id="API id" calls="number" renewal-period="seconds" >
        <operation name="operation name" id="operation id" calls="number" renewal-period="seconds" />
    </api>
</rate-limit>
```
Send request:
```xml:
<send-request mode="new | copy" response-variable-name="" timeout="60 sec" ignore-error
="false | true">
  <set-url>request URL</set-url>
  <set-method>...</set-method>
  <set-header>...</set-header>
  <set-body>...</set-body>
  <authentication-certificate thumbprint="thumbprint" />
  <proxy>...</proxy>
</send-request>
```


 # Azure Routing
 System routes

 User defined routes
Example: next hop virtual appliance

 # Azure NSG

























