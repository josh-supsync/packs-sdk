---
nav: "PropertyOptionsExecutionContext"
note: "This file is autogenerated from TypeScript definitions. Make edits to the comments in the TypeScript file and then run `make docs` to regenerate this file."
search:
  boost: 0.1
---
# Interface: PropertyOptionsExecutionContext

[core](../modules/core.md).PropertyOptionsExecutionContext

Sub-class of [ExecutionContext](core.ExecutionContext.md) that is passed to the `options` function of
mutable sync tables for properties with `options` enabled.

## Hierarchy

- [`ExecutionContext`](core.ExecutionContext.md)

  ↳ **`PropertyOptionsExecutionContext`**

## Properties

### endpoint

• `Optional` `Readonly` **endpoint**: `string`

The base endpoint URL for the user's account, only if applicable. See
[requiresEndpointUrl](core.BaseAuthentication.md#requiresendpointurl).

If the API URLs are variable based on the user account, you will need this endpoint
to construct URLs to use with the fetcher. Alternatively, you can use relative URLs
(e.g. "/api/entity") and Coda will include the endpoint for you automatically.

#### Inherited from

[ExecutionContext](core.ExecutionContext.md).[endpoint](core.ExecutionContext.md#endpoint)

___

### fetcher

• `Readonly` **fetcher**: [`Fetcher`](core.Fetcher.md)

The [Fetcher](core.Fetcher.md) used for making HTTP requests.

#### Inherited from

[ExecutionContext](core.ExecutionContext.md).[fetcher](core.ExecutionContext.md#fetcher)

___

### invocationLocation

• `Readonly` **invocationLocation**: [`InvocationLocation`](core.InvocationLocation.md)

Information about the Coda environment and doc this formula was invoked from.
This is mostly for Coda internal use and we do not recommend relying on it.

#### Inherited from

[ExecutionContext](core.ExecutionContext.md).[invocationLocation](core.ExecutionContext.md#invocationlocation)

___

### invocationToken

• `Readonly` **invocationToken**: `string`

A random token scoped to only this request invocation.
This is a unique identifier for the invocation, and in particular used with
[Custom](../enums/core.AuthenticationType.md#custom) for naming template parameters that will be
replaced by the fetcher in secure way.

#### Inherited from

[ExecutionContext](core.ExecutionContext.md).[invocationToken](core.ExecutionContext.md#invocationtoken)

___

### propertyName

• `Readonly` **propertyName**: `string`

Which property is being edited.

___

### propertySchema

• `Readonly` **propertySchema**: [`Schema`](../types/core.Schema.md)

Schema of the property being edited.

___

### propertyValues

• `Readonly` **propertyValues**: `Object`

Current values of other properties from the same row. Non-required properties may be missing
if the doc owner elected not to sync them, or if they have a type that's not yet supported
for options context. Properties referencing other sync tables may be missing some or
all of their sub-properties if the reference is broken because the other table is not
added to the doc or hasn't synced the referenced row.

#### Index signature

▪ [propertyValues: `string`]: `any`

___

### search

• `Readonly` **search**: `string`

What the user typed. For example, they may have type "Ja" while searching for a user named
"Jane".

___

### sync

• `Optional` `Readonly` **sync**: [`Sync`](core.Sync.md)

Information about state of the current sync. Only populated if this is a sync table formula.

#### Inherited from

[ExecutionContext](core.ExecutionContext.md).[sync](core.ExecutionContext.md#sync)

___

### temporaryBlobStorage

• `Readonly` **temporaryBlobStorage**: [`TemporaryBlobStorage`](core.TemporaryBlobStorage.md)

A utility to fetch and store files and images that either require the pack user's authentication
or are too large to return inline. See [TemporaryBlobStorage](core.TemporaryBlobStorage.md).

#### Inherited from

[ExecutionContext](core.ExecutionContext.md).[temporaryBlobStorage](core.ExecutionContext.md#temporaryblobstorage)

___

### timezone

• `Readonly` **timezone**: `string`

The timezone of the doc from which this formula was invoked.

#### Inherited from

[ExecutionContext](core.ExecutionContext.md).[timezone](core.ExecutionContext.md#timezone)