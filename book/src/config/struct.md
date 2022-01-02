# Struct attributes

The following attributes may be used in a `superstruct` macro invocation on a
`struct` item. All attributes are optional unless stated otherwise.

## Variants

```
#[superstruct(variants(A, B, ...))]
```

Define the list of variants that this type has.
See [variant structs](../codegen/variant-structs.md).

The `variants` attribute is _not optional_.

**Format**: 1+ comma-separated identifiers.

## Cast error

```
#[superstruct(cast_error(ty = "..", expr = ".."))]
```

Define the error type to be returned from [casting methods](../codegen/enum.md#casting-methods).

The expression must be of the given error type, and capable of being evaluated without any
context (it is _not_ a closure).

**Format**: quoted type for `ty`, quoted expression for `expr`

## Partial getter error

```
#[superstruct(cast_error(ty = "..", expr = ".."))]
```

Define the error type to be returned from [partial getter
methods](../codegen/enum.md#getters-and-setters).

The expression must be of the given error type, and capable of being evaluated without any
context (it is _not_ a closure).

**Format**: quoted type for `ty`, quoted expression for `expr`

## Variant attributes

```
#[superstruct(variant_attributes(...))]
```

Provide a list of attributes to be applied verbatim to each variant struct definition.

This can be used to derive traits, perform conditional compilation, etc.

**Format**: any.

## `Ref` attributes

```
#[superstruct(ref_attributes(...))]
```

Provide a list of attributes to be applied verbatim to the generated `Ref` type.

**Format**: any.

## `RefMut` attributes

```
#[superstruct(ref_mut_attributes(...))]
```

Provide a list of attributes to be applied verbatim to the generated `RefMut` type.

**Format**: any.

## No enum

```
#[superstruct(no_enum)]
```

Disable generation of the top-level enum, and all code except the
[variant structs](../codegen/variant-structs.md).