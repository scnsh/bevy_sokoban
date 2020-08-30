# bevy_sokoban

This is Sokoban implemented by following [@iolivia](https://github.com/iolivia)'s [Rust sokoban](https://sokoban.iolivia.me) tutorial — but in [Bevy](https://bevyengine.org/) instead of [ggez](https://ggez.rs/).

This is literally my first experience in gamedev, so the code is probably not very idiomatic and/or clean — all feedback is very much appreciated!

If you get ```thread 'main' panicked at 'called `Result::unwrap()` on an `Err` value: MismatchedDynamicOffsetCount { actual: 0, expected: 2 }'``` on launch, it is probably because of https://github.com/bevyengine/bevy/issues/134. Consider commenting out the following line: https://github.com/ropewalker/bevy_sokoban/blob/f4cfe92f53652a760619771cfad7f03cde1959ac/src/systems/setup.rs#L22 or remove creation of UI Camera here: https://github.com/ropewalker/bevy_sokoban/blob/f4cfe92f53652a760619771cfad7f03cde1959ac/src/systems/setup.rs#L19 (both will disable text labels, so you will never know when you won the game, but TextComponents don't seem to be able to coexist with SpriteSheetComponents because of that bug).

If something else is not working, please note that Cargo.toml points at the master branch of Bevy, not at the crates.io version. At the moment of writing Bevy is still at the very early stages of development. Please consider [contributing](https://bevyengine.org/learn/book/contributing/) or [donating](https://github.com/sponsors/cart) :)
