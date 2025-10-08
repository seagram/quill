<div align="center">
  <img src="./assets/quill.svg" alt="Quill Logo" width="200">
  <h1>Quill</h1>
  Lightweight, modern, extensible markup language for screenplays.
  
  <p>
    <a href="#about">About</a> •
    <a href="#motivation">Motivation</a> •
    <a href="#features">Features</a> •
    <a href="#documentation">Documentation</a> •
    <a href="#status">Status</a> •
    <a href="#philosophy">Philosophy</a>
  </p>
</div>

## About

Quill is a plain text markup language for writing screenplays.
With Quill, you can:

- Write in plain text.
- Use version control.
- Export to industry-standard formats like Fountain and Final Draft.

## Motivation

Quill was created to resolve some limitations of [Fountain](https://github.com/nyousefi/Fountain), the most widely used open-source screenplay markup language.

### Problems with Fountain

**Ambiguous parsing rules:** Fountain relies heavily on implicit syntax and context-dependent parsing.
The result is a language with lots of edge cases and inconsistent behaviour.
This forces parsers to "guess" the intent of the writer which can cause unexpected results.

**Whitespace sensitivity**: Fountain's whitespace sensitivity treats every carriage return as intentional.
This means an unintentional whitespace can change an element from the one you intended to another.
For example, a newline can change an action block into a character cue.

**Inconsistent syntax**: Fountain syntax is somewhat opinionated. It uses special characters to delineate elements like `@` for characters, `.` for scene headings and `>` for transitions.
This can make writing in the language feel like an exercise in memory, rather than intuition. There is little extensibility to tailor the language to your specific use case.

**No formal specification**: Fountain lacks a formal grammar specification which makes it difficult to implement language tooling like parsers, validators, and formatters.

## Features

**Explicit over implicit:** Clear, customizable syntax that doesn't require context to parse.

**Extensible by design**: Supports custom metadata and nested elements.

**Formal specification**: A proper grammar, enabling consistent parsing across implementations.

**Backwards compatible**: Quill files can be compiled to Fountain (`.fountain`) or Final Draft (`.fdx`) formats.

## Documentation

### File Extension

Quill files use the `.ql` extension.

### Syntax

Quill uses hash-prefixed functions and bracket-based content blocks to define screenplay elements. It resembles markup languages like [Typst](https://github.com/typst/typst).

Each element is defined by prefixing a `#` to its element name or _element identifier_. The element's content is wrapped inside square brackets (`[]`). This is called the _content field_.

#### Example

```quill
#scene[INT. RESTAURANT - NIGHT]
```

Here, `#scene` is the element identifier and `[INT. RESTAURANT - NIGHT]` is the content field.

Some elements can take parameters. For example, the `#dialogue` element takes a parameter of `character`.

Parameters are supplied in a _parameter field_ defined by square brackets (`[]`) before the content field.

#### Example

```quill
#dialogue[WAITER][
  Can I take your order?
]
```

Elements can contain nested elements inside them. For example, the `#dialogue` element can contain a nested `#paren` element.

#### Example

```quill
#dialogue[CUSTOMER][
  #paren[under breath]
  About time...
]
```

Nested elements are also used for elements like `#dualdialogue`.

#### Example

```quill
#dualdialogue[
  #dialogue[MAN 1][Wow, look at that!]
  #dialogue[MAN 2][I can't believe it!]
]
```

Nested elements can have their own nested elements and so on and so forth.

```quill
#dualdialogue[
  #dialogue[MAN 1][
    #paren[laughs]
    Ha! I told you!
  ]
  #dialogue[MAN 2][
    #paren[over shoulder]
    You tricked me!
  ]
]
```

### Example Screenplay

```quill
#titlepage[
  #title[Rebel Without A Cause]
  #author[Stewart Stern]
  #draft[First Draft]
  #date[1955-08-27]
]

#scene[INT. POLICE STATION - NIGHT]

#action[The juvenile division. JIM STARK, seventeen, lies on a bench, drunk.]

#action[A JUVENILE OFFICER approaches JIM.]

#dialogue[OFFICER][
  All right, kid. On your feet.
]

#transition[CUT TO:]

#scene[INT. RAY'S OFFICE - CONTINUOUS]

#action[
  Jim slumps into the chair across from him.
]

#dialogue[RAY][
  What's the story this time, Jim?
]

#dialogue[JIM][
  #paren[mumbled]
  No story. Just celebrating.
]
```

## Status

Quill is still under active development. The final specification has yet to be formalized.

## Philosophy

1. Plain text forever - No proprietary formats, no lock-in.
2. Human-readable first - It should write and read like a screenplay.
3. Explicit over implicit - Prioritize clarity over context.
4. Extensible by design - Easy to parse, validate, and transform.

## Acknowledgements

Thank you to John August, Nima Yousefi, and Stu Maschwitz for creating Fountain and pioneering open-source software in the screenwriting industry.

---

Note: Quill is not in any way affiliated with or endorsed by the Fountain project.

```

```
