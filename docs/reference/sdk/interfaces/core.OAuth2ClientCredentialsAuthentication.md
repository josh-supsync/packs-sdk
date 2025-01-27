---
nav: "OAuth2ClientCredentialsAuthentication"
note: "This file is autogenerated from TypeScript definitions. Make edits to the comments in the TypeScript file and then run `make docs` to regenerate this file."
search:
  boost: 0.1
---
# Interface: OAuth2ClientCredentialsAuthentication

[core](../modules/core.md).OAuth2ClientCredentialsAuthentication

Authenticate using OAuth2 client credentials.
You must specify the token exchange URL here as part of the pack definition.
You'll provide the application's client ID and client secret when authenticating.

**`Example`**

```ts
pack.setUserAuthentication({
  type: coda.AuthenticationType.OAuth2ClientCredentials,
  // This URL comes from the API's developer documentation.
  tokenUrl: "https://api.example.com/token",
});
```

## Hierarchy

- `BaseOAuthAuthentication`

  ↳ **`OAuth2ClientCredentialsAuthentication`**

## Properties

### credentialsLocation

• `Optional` **credentialsLocation**: [`TokenExchangeCredentialsLocation`](../enums/core.TokenExchangeCredentialsLocation.md)

When making the token exchange request, where to pass the client credentials (client ID and
client secret). The default is [Automatic](../enums/core.TokenExchangeCredentialsLocation.md#automatic), which should
work for most providers. Pick a more specific option if the provider invalidates authorization
codes when there is an error in the token exchange.

#### Inherited from

BaseOAuthAuthentication.credentialsLocation

___

### endpointDomain

• `Optional` **endpointDomain**: `string`

When requiresEndpointUrl is set to true this should be the root domain that all endpoints share.
For example, this value would be "example.com" if specific endpoints looked like {custom-subdomain}.example.com.

For packs that make requests to multiple domains (uncommon), this should be the domain within
[networkDomains](core.PackVersionDefinition.md#networkdomains) that this configuration applies to.

#### Inherited from

BaseOAuthAuthentication.endpointDomain

___

### getConnectionName

• `Optional` **getConnectionName**: [`MetadataFormula`](../types/core.MetadataFormula.md)

A function that is called when a user sets up a new account, that returns a name for
the account to label that account in the UI. The users credentials are applied to any
fetcher requests that this function makes. Typically, this function makes an API call
to an API's "who am I" endpoint and returns a username.

If omitted, or if the function returns an empty value, the account will be labeled
with the creating user's Coda username.

#### Inherited from

BaseOAuthAuthentication.getConnectionName

___

### instructionsUrl

• `Optional` **instructionsUrl**: `string`

A link to a help article or other page with more instructions about how to set up an account for this pack.

#### Inherited from

BaseOAuthAuthentication.instructionsUrl

___

### nestedResponseKey

• `Optional` **nestedResponseKey**: `string`

In rare cases, OAuth providers send back access tokens nested inside another object in
their authentication response.

#### Inherited from

BaseOAuthAuthentication.nestedResponseKey

___

### networkDomain

• `Optional` **networkDomain**: `string` \| `string`[]

Which domain(s) should get auth credentials, when a pack is configured with multiple domains.
Packs configured with only one domain or with requiresEndpointUrl set to true can omit this.

Using multiple authenticated network domains is uncommon and requires Coda approval.

#### Inherited from

BaseOAuthAuthentication.networkDomain

___

### postSetup

• `Optional` **postSetup**: [`SetEndpoint`](core.SetEndpoint.md)[]

One or more setup steps to run after the user has set up the account, before completing installation of the pack.
This is not common.

#### Inherited from

BaseOAuthAuthentication.postSetup

___

### requiresEndpointUrl

• `Optional` **requiresEndpointUrl**: `boolean`

If true, indicates this has pack has a specific endpoint domain for each account, that is used
as the basis of HTTP requests. For example, API requests are made to <custom-subdomain>.example.com
rather than example.com. If true, the user will be prompted to provide their specific endpoint domain
when creating a new account.

#### Inherited from

BaseOAuthAuthentication.requiresEndpointUrl

___

### scopeParamName

• `Optional` **scopeParamName**: `string`

In rare cases, OAuth providers may want the permission scopes in a different query parameter
than `scope`.

#### Inherited from

BaseOAuthAuthentication.scopeParamName

___

### scopes

• `Optional` **scopes**: `string`[]

Scopes that are required to use this pack.

Each API defines its own list of scopes, or none at all. You should consult
the documentation for the API you are connecting to.

#### Inherited from

BaseOAuthAuthentication.scopes

___

### tokenPrefix

• `Optional` **tokenPrefix**: `string`

A custom prefix to be used when passing the access token in the HTTP Authorization
header when making requests. Typically this prefix is `Bearer` which is what will be
used if this value is omitted. However, some services require a different prefix.
When sending authenticated requests, a HTTP header of the form
`Authorization: <tokenPrefix> <token>` will be used.

#### Inherited from

BaseOAuthAuthentication.tokenPrefix

___

### tokenQueryParam

• `Optional` **tokenQueryParam**: `string`

In rare cases, OAuth providers ask that a token is passed as a URL parameter
rather than an HTTP header. If so, this is the name of the URL query parameter
that should contain the token.

#### Inherited from

BaseOAuthAuthentication.tokenQueryParam

___

### tokenUrl

• **tokenUrl**: `string`

The URL that Coda will hit in order to exchange the temporary code for an access token.

#### Inherited from

BaseOAuthAuthentication.tokenUrl

___

### type

• **type**: [`OAuth2ClientCredentials`](../enums/core.AuthenticationType.md#oauth2clientcredentials)

Identifies this as OAuth2 client credentials authentication.
