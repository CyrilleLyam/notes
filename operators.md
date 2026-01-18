# Programming operators

Common operator categories you will see across many languages.

## Arithmetic

- `+ - * / %` for add, subtract, multiply, divide, remainder.
- Exponent `**` or `^` (language-specific); integer division `//` in some languages.
- Unary plus/minus for numeric coercion or sign.

## Comparison

- Equality/inequality: `== !=` (loose in some langs), strict `===` in JS.
- Relational: `< <= > >=` compare order.
- Pattern/type helpers vary: `instanceof`, `is`, `typeof`, `in`.

## Logical (Boolean)

- `&&`/`and`, `||`/`or`, `!`/`not`; all typically short-circuit.
- Use parentheses to make precedence explicit.

## Assignment

- Basic `=` plus compound `+= -= *= /= %= <<= >>= &= |= ^=`.
- Many langs support destructuring/tuple assignment for multiple values.

## Bitwise

- `& | ^ ~ << >>` for AND, OR, XOR, NOT, shifts; unsigned shift `>>>` in JS.
- Useful for flags/masks; be mindful of sign bits and overflow.

## Conditional/ternary

- `condition ? whenTrue : whenFalse` or language equivalent (`if/else` expressions).
- Keep branches simple for readability.

## Null/undefined helpers

- Nullish coalescing `??` and optional chaining `?.` (JS/TS); Elvis `?:` and safe-call `?.` (Kotlin).
- Use to avoid accidental `NullPointer`/`undefined` errors.

## Precedence reminder

- Highest to lowest (generalized): parentheses → unary (`!`, `~`, unary `-`) → multiplicative → additive → shifts → comparisons/equality → bitwise → logical → assignment.
- When unsure, add parentheses to keep intent clear.
