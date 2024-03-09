# Drum Notes App
Drum beat shorthand.

```
// this is a comment

// start a part for individual drums with the `|`

| closed-hat: 1, 1+, 2, 2+, 3, 3+, 4, 4+
| kick: 1, 2+, 4+
| snare: 3

// alternately, you can specify a drum "block" by surrounding some lines with `||`
|| "boom-boom boom-tap"
  closed-hat: 1, 1+, 2, 2+, 3, 3+, 4, 4+
  kick: 1, 2+, 4+
  snare: 3
||

// write accents like this:
| snare: >1, 1e, 1+, >1a, 2, 2e, >2+, 2a, 3, >3e, 3+, 3e, >4, 4e, 4+, 4a

// 32nds can be written thusly
| snare: 1, 1u, 1e, 1eu, 1+, 1+u, 1a, 1au, 2

// you can specify the number of beats for the phease as shown below. If not specified, the largest number in the phrase  will be used to calculate the length of the phrase.
|| in-seven 7
  kick: >1, 1a
||

|| ride-pattern 4
  |
||
```

```
ride-pattern:[ride 4 4]{1 2(>tri let) 3 4(>tri let)}
ride-pattern:[ride quarter]{x, >tri let, x, >tri let}
```

```
pattern syncopated-hat = {+}

patch my-groove = [
  beats:4
  subdivision:quarter
  kit:17
  @1:rack-tom
  @2:floor-tom
]{
  ride: 3{x +}{x}
  kick: {x a, +, , +}
  snare: {e, >x, , e a}
  hat: 4syncopated-hat
  @1: {}|{, a, e a,}
  @2: {, +,,}|{,,, +}
}

cue>
  my-groove(4)
  my-groove(2) my-groove.alt(2)
```

# Random Notes
- definitely going to want some sort of tagging system
  - The concept of a pattern (or pattern snippet) literal is going to be crucial in my imagining of how someone might use this module. It's kinda hard to think of meaningful names for something like a snippet of a drum part. That said, we will want to store these pattern snippets as part of our library of patches, so having some semblance of organization via tags will be useful.
