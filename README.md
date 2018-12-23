# Ways

An open-ended text adventure engine

## Concept

_Ways_ is intended to allow for a scalable and extendable system for text
adventure games. The system is being planned architecturally prior to code
implementation.

## Contribution

If you have ideas for inclusion, please open an issue to start the discussion.

### Content

Text adventure games operate using a REPL (Read, Evaluate, Print, Loop)
model. Users can type actions which are evaluated by the system. The
outcome of those actions is then printed. Then the system repeats.

Success of this model relies on a few parts:

- `actions` - commands which can be interpreted by the program to cause
  a change in the system or other output. `LOOK` and `GO` are examples.

- `detail` - text feedback to the user describing the environment. This
  could take on the form of a virtual setting, dialogue, etc.

- `state` - in order to generate a malleable environment, actions can
  cause modifications to the underlying state of reality. Is there a gun
  on the mantle or is it in the user's inventory? Did you feed that dog
  a bone or is it hungry?

`Detail` is generated by the current `state`. `State` is changed by user
`actions`. That is the core organizing principle of _Ways_.
