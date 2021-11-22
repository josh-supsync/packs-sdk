# Interface: ObjectArrayFormulaDef<ParamsT, SchemaT\>

Inputs to declaratively define a formula that returns a list of objects.
That is, a formula that doesn't require code, which like an [EmptyFormulaDef](EmptyFormulaDef.md) uses
a [RequestHandlerTemplate](RequestHandlerTemplate.md) to describe the request to be made, but also includes a
[ResponseHandlerTemplate](ResponseHandlerTemplate.md) to describe the schema of the returned objects.
These take the place of implementing a JavaScript `execute` function.

This type is generally not used directly, but describes the inputs to [makeTranslateObjectFormula](../functions/makeTranslateObjectFormula.md).

## Type parameters

| Name | Type |
| :------ | :------ |
| `ParamsT` | extends [`ParamDefs`](../types/ParamDefs.md) |
| `SchemaT` | extends [`Schema`](../types/Schema.md) |

## Hierarchy

- `Omit`<[`PackFormulaDef`](PackFormulaDef.md)<`ParamsT`, [`SchemaType`](../types/SchemaType.md)<`SchemaT`\>\>, ``"execute"``\>

  ↳ **`ObjectArrayFormulaDef`**

## Properties

### cacheTtlSecs

• `Optional` `Readonly` **cacheTtlSecs**: `number`

How long formulas running with the same values should cache their results for.

#### Inherited from

Omit.cacheTtlSecs

#### Defined in

[api_types.ts:318](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L318)

___

### connectionRequirement

• `Optional` `Readonly` **connectionRequirement**: [`ConnectionRequirement`](../enums/ConnectionRequirement.md)

Does this formula require a connection (aka an account)?

#### Inherited from

Omit.connectionRequirement

#### Defined in

[api_types.ts:310](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L310)

___

### description

• `Readonly` **description**: `string`

A brief description of what the formula does.

#### Inherited from

Omit.description

#### Defined in

[api_types.ts:284](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L284)

___

### examples

• `Optional` `Readonly` **examples**: { `params`: [`PackFormulaValue`](../types/PackFormulaValue.md)[] ; `result`: [`PackFormulaResult`](../types/PackFormulaResult.md)  }[]

Sample inputs and outputs demonstrating usage of this formula.

#### Inherited from

Omit.examples

#### Defined in

[api_types.ts:299](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L299)

___

### extraOAuthScopes

• `Optional` `Readonly` **extraOAuthScopes**: `string`[]

OAuth scopes that the formula needs that weren't requested in the pack's overall authentication
config. For example, a Slack pack can have one formula that needs admin privileges, but non-admins
can use the bulk of the pack without those privileges. Coda will give users help in understanding
that they need additional authentication to use a formula with extra OAuth scopes. Note that
these scopes will always be requested in addition to the default scopes for the pack,
so an end user must have both sets of permissions.

#### Inherited from

Omit.extraOAuthScopes

#### Defined in

[api_types.ts:340](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L340)

___

### isAction

• `Optional` `Readonly` **isAction**: `boolean`

Does this formula take an action (vs retrieve data or make a calculation)?
Actions are presented as buttons in the Coda UI.

#### Inherited from

Omit.isAction

#### Defined in

[api_types.ts:305](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L305)

___

### isExperimental

• `Optional` `Readonly` **isExperimental**: `boolean`

If specified, the formula will not be suggested to users in Coda's formula autocomplete.
The formula can still be invoked by manually typing its full name.

#### Inherited from

Omit.isExperimental

#### Defined in

[api_types.ts:324](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L324)

___

### isSystem

• `Optional` `Readonly` **isSystem**: `boolean`

Whether this is a formula that will be used by Coda internally and not exposed directly to users.
Not for use by packs that are not authored by Coda.

#### Inherited from

Omit.isSystem

#### Defined in

[api_types.ts:330](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L330)

___

### name

• `Readonly` **name**: `string`

The name of the formula, used to invoke it.

#### Inherited from

Omit.name

#### Defined in

[api_types.ts:279](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L279)

___

### network

• `Optional` `Readonly` **network**: [`Network`](Network.md)

**`deprecated`** use `isAction` and `connectionRequirement` instead

#### Inherited from

Omit.network

#### Defined in

[api_types.ts:313](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L313)

___

### parameters

• `Readonly` **parameters**: `ParamsT`

The parameter inputs to the formula, if any.

#### Inherited from

Omit.parameters

#### Defined in

[api_types.ts:289](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L289)

___

### request

• **request**: [`RequestHandlerTemplate`](RequestHandlerTemplate.md)

A definition of the request and any parameter transformations to make in order to implement this formula.

#### Defined in

<<<<<<< HEAD
[api.ts:455](https://github.com/coda/packs-sdk/blob/main/api.ts#L455)
=======
[api.ts:463](https://github.com/coda/packs-sdk/blob/main/api.ts#L463)
>>>>>>> 33154897 (restrict param autocomplete to only string & number, and respect param type in autocomplete shape (#1572))

___

### response

• **response**: [`ResponseHandlerTemplate`](ResponseHandlerTemplate.md)<`SchemaT`\>

A definition of the schema for the object list returned by this function.

#### Defined in

<<<<<<< HEAD
[api.ts:457](https://github.com/coda/packs-sdk/blob/main/api.ts#L457)
=======
[api.ts:465](https://github.com/coda/packs-sdk/blob/main/api.ts#L465)
>>>>>>> 33154897 (restrict param autocomplete to only string & number, and respect param type in autocomplete shape (#1572))

___

### varargParameters

• `Optional` `Readonly` **varargParameters**: [`ParamDefs`](../types/ParamDefs.md)

Variable argument parameters, used if this formula should accept arbitrary
numbers of inputs.

#### Inherited from

Omit.varargParameters

#### Defined in

[api_types.ts:294](https://github.com/coda/packs-sdk/blob/main/api_types.ts#L294)