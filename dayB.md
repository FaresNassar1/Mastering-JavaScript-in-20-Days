## JavaScript DEEP JS FOUNDATIONS

# 4-2# Day Training

---

### Table of Contents

- [Static Typing](#)
- [Scope](#)

---

### TypeScript, Flow, and type-aware linting

### Benefits:
1. Catch type-related mistakes
2. Communicate type intent
3. Provide IDE feedback

### Caveats:

1. Inferencing is best-guess, not a
guarantee
2. Annotations are optional
3. Any part of the application that
isn't typed introduces uncertainty

### Example
` var x="fares";`
`x={name:nassar};`
**Error:can't assign object to string**
and the same if 
`var x:string="fares";  x={name:"nassar"};//error ca....`
**note**: can't subtract string 🔨

## Pros
1. They make types more obvious in code
2. Familiarity: they look like other language's type systems
3. Extremely popular these days
## corns 
1. They require* a build process, which raises the barrier to entry
2. Their sophistication can be intimidating to those without prior formal types experience
   etc....

   ---

   ## Scope

* Scope: where to look
for things
