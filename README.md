# Crafting Controller — unofficial Carbon hotfix

This repository tracks MajikTom’s compatibility patch for [Crafting Controller](https://umod.org/plugins/crafting-controller), a Rust server plugin maintained by Whispers88. Mughisi is the original author, and Nivex also helped maintain the plugin.

The `main` branch contains the upstream 3.3.7 plugin. The [3.3.8 hotfix](https://github.com/MajikTom/rust-craftingcontroller-hotfix/blob/fix/carbon-crafting/CraftingController.cs) is on the `fix/carbon-crafting` branch. See the [pull request](https://github.com/MajikTom/rust-craftingcontroller-hotfix/pull/1) for the code changes and [LICENSE](LICENSE) for the upstream MIT terms.

## What changed

The hotfix updates `OnItemCraft` and `ReturnCraft` for Carbon builds where `ItemCraftTask.cancelled` is unavailable. It removes writes to that field during bulk crafting and refunds for rejected crafts. Players receive refund notices in chat.

## Plugin compatibility

I tested the patch on a Carbon server with the [Instant Craft hotfix](https://github.com/MajikTom/rust-instantcraft-hotfix/pull/1) loaded. Rock crafting was blocked as configured, and instant crafting worked. The only change after that test was the Crafting Controller version bump to 3.3.8.

Compatibility with the following plugins has not been tested with this hotfix:

- [Craft Multiplier](https://umod.org/plugins/craft-multiplier)
- [Firearm Modifier](https://umod.org/plugins/firearm-modifier)
