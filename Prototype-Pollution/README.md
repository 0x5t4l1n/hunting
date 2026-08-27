# Prototype Pollution

## Description
Prototype pollution is a JavaScript vulnerability that occurs when an attacker is able to inject properties into `Object.prototype` (or another object's prototype chain) via untrusted input. Because nearly every object in JavaScript inherits from `Object.prototype`, a polluted property can alter application behavior globally — enabling denial of service, property injection, authentication/authorization bypass, and in some cases remote code execution when the polluted property is later used in a dangerous sink (e.g. `eval`, `child_process`, template rendering, or `require` paths).

## Common Attack Vectors
- JSON/query bodies parsed with unsafe merge or clone utilities (`extend`, `merge`, `deepMerge`, `lodash.merge`, `jQuery.extend`)
- URL/query string parsers that decode `__proto__`, `constructor`, or `prototype` keys
- YAML/JSON parsers that honor object keys verbatim
- `Object.assign` / spread against attacker-controlled keys
- Nested object assignment handled by custom recursive setters

## Common Techniques
- `__proto__` key injection in JSON bodies
- `constructor.prototype` climbing to reach `Object.prototype`
- `prototype` key pollution in nested merge operations
- DOM/clientside pollution that propagates into `Object.prototype`
- Chained pollution that reaches a dangerous application sink

## Testing Approach
Send crafted JSON/query parameters containing `__proto__`, `constructor`, and `prototype` keys at various nesting depths. Observe whether injected properties appear on plain `{}` objects created afterward (e.g. `({}).polluted === true`). Then map which polluted property the application later consumes in a security-sensitive decision (ACL flags, admin checks, template names).

## Payloads
See `prototype-pollution-payloads.txt` for a comprehensive list of prototype pollution payloads.
