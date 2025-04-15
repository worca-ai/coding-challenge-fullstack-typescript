# TypeScript Programming Challenges for Full-Stack Developers
Each of these challenges is designed to take 10–20 minutes for a skilled full-stack TypeScript developer.

## Challenge 1: Validate a Form Object (Frontend Logic)
Prompt
You’re building a form validation system. Given an object with field values and a set of validation rules, return an object showing the validation errors per field.

```ts
type Rules = {
  [key: string]: (value: any) => string | null;
};

function validateForm(values: Record<string, any>, rules: Rules): Record<string, string | null> {
  // Your code here
}
```

Example Usage
```ts
Copy
Edit
const values = {
  name: "",
  age: 17,
};

const rules: Rules = {
  name: (val) => (val ? null : "Name is required"),
  age: (val) => (val >= 18 ? null : "Must be at least 18"),
};

const result = validateForm(values, rules);

/*
Expected Output:
{
  name: "Name is required",
  age: "Must be at least 18"
}
*/
```

## Challenge 2: Flatten a Nested Object (Backend/Data Logic)
Prompt
Write a function that flattens a nested object. Use dot-notation keys for the nested structure.

```ts
function flattenObject(obj: Record<string, any>): Record<string, any> {
  // Your code here
}
```

Example Input
```ts
const input = {
  a: {
    b: {
      c: 1
    },
    d: 2
  },
  e: 3
};
```

Expected Output
```ts
{
  "a.b.c": 1,
  "a.d": 2,
  "e": 3
}
```

## Challenge 3: Fetch with Timeout (Async Handling)
Prompt
Create a utility function fetchWithTimeout that wraps fetch and rejects with an error if the request takes longer than a specified timeout (in ms).

```ts
async function fetchWithTimeout(url: string, timeout: number): Promise<Response> {
  // Your code here
}
```
Usage

```ts
try {
  const response = await fetchWithTimeout("https://api.example.com", 2000);
  const data = await response.json();
} catch (err) {
  console.error("Request failed:", err);
}
```
