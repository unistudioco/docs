# Conditional Display Documentation

This guide details how to use the Conditional Display system to dynamically show or hide controls in the builder based on the values of other controls.

## Basic Usage

The `show_if` property in a control definition determines its visibility.

### 1. Single Value Equality
Display a control if another control has a specific value.

```json
"show_if": "{{control_id}} === 'value'"
```

**Example:**
```json
"show_if": "{{section_container}} === 'custom'"
```

### 2. Inequality
Display a control if another control does **NOT** equal a value.

```json
"show_if": "{{control_id}} !== 'value'"
```

### 3. Multiple Values (IN)
Display a control if another control's value matches one of the items in a set.

```json
"show_if": "{{control_id}} in { 'small', 'medium' }"
```

## Logical Grouping

You can combine multiple conditions using **AND** (implicit in arrays) or **OR** (explicit object).

### AND Logic (Default)
All conditions must be true for the control to display. Pass an array of condition strings.

```json
"show_if": [
    "{{section_container}} === 'custom'",
    "{{show_advanced}} === true"
]
```

### OR Logic
At least one condition must be true. Use a configuration object with `relation: 'OR'`.

```json
"show_if": {
    "relation": "OR",
    "conditions": [
        "{{status}} === 'active'",
        "{{role}} === 'admin'"
    ]
}
```

## Supported Operators

| Operator | Description | Example |
| :--- | :--- | :--- |
| `===` | Strict Equality | `{{id}} === 'value'` |
| `!==` | Strict Inequality | `{{id}} !== 'value'` |
| `==` | Equality (loose) | `{{id}} == 1` |
| `!=` | Inequality (loose) | `{{id}} != 1` |
| `>` | Greater Than | `{{width}} > 100` |
| `>=` | Greater/Equal | `{{width}} >= 100` |
| `<` | Less Than | `{{width}} < 50` |
| `<=` | Less/Equal | `{{width}} <= 50` |
| `in` | Value exists in set | `{{type}} in { 'a', 'b' }` |
| `!in` | Value NOT in set | `{{type}} !in { 'a', 'b' }` |
| `contains` | Array var contains value | `{{tags}} contains 'new'` |
