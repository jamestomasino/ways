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

- `action` - commands which can be interpreted by the program to cause
  a change in the system or other output. `LOOK` and `GO` are examples.

- `detail` - text feedback to the user describing the environment. This
  could take on the form of a virtual setting, dialogue, etc.

- `state` - in order to generate a malleable environment, actions can
  cause modifications to the underlying state of reality. Is there a gun
  on the mantle or is it in the user's inventory? Did you feed that dog
  a bone or is it hungry?

`Detail` is generated based upon the current `state`. `State` is changed
by user `actions`. That is the core organizing principle of _Ways_.

- `scene` - building-blocks of the text adventure. These can be thought of
  as screens that you are navigating. A living room, a dusty road, or the
  creepy attic are all good examples. Scenes are where `detail` is
  rendered based on the current `state`. Scenes also provide a list of
  available `actions`. The available actions can change in a scene based
  on the state.

- `domain` - A collection of scenes. Domains define a private `state`
  object. This ensures that your BLUE KEY doesn't get mixed up with
  another person's BLUE KEY.
