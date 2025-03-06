# Flutter Tailwind Colours

A complete collection of Tailwind CSS v3's default colours saved as Dart constants for Flutter projects.

This makes it _much_ easier for your mobile app to match your Tailwind website by using the exact same colours with similar names that you already know off by heart.

## Overview

This repo provides all Tailwind CSS v3's default colours and their tints as Dart `Colour` constants, making it easy to integrate the Tailwind colour system into your Flutter app. The constants are named as the colour and the tint (e.g., `slate700`, `amber500`) that matches Tailwind's naming convention.



## Installation

Add the `tailwind_colours` folder anywhere in your project's `lib/` directory, e.g. `lib/styles`.

If there are any colours that you don't use at all (Fuchsia), you can just delete the file with that name.

## Usage

Import the relevant file(s) and use the colour constants in your Flutter widgets. Your IDE should autosuggest the colour names as you type and add the imports for you:

```dart
import 'package:your_app_name/styles/tailwind_colours/blue.dart';
import 'package:your_app_name/styles/tailwind_colours/slate.dart';

Container(
  color: blue500,
  child: Text(
    'This background is Tailwind blue500 and the text is slate100',
    style: TextStyle(
        color: slate100
    ),
  ),
)
```

The colours are saved as separate files by colour family to avoid a huge single import (242 colours). Most Tailwind projects only use a handful of colours and tints, so this organisation allows you to import only what you need.

If you don't want to deal with multiple imports, you can always copy and paste the colours you used in your project into a single file, or create separate files for different pages.

For example, you could make a 'stylesheet' file for your buttons like below, and a single import will give you all the colours you need for your buttons:

```dart
import 'dart:ui';

const Color red500 = Color(0xFFEF4444);
const Color red600 = Color(0xFFDC2626);

const Color green500 = Color(0xFF22C55E);
const Color green600 = Color(0xFF16A34A);

const Color neutral500 = Color(0xFF737373);
const Color neutral600 = Color(0xFF525252);
```


## Colour Palettes

This repo includes all 22 colour palettes from Tailwind CSS v3:

- Amber
- Blue
- Cyan
- Emerald
- Fuchsia
- Gray (you can also use grey)
- Green
- Indigo
- Lime
- Neutral
- Orange
- Pink
- Purple
- Red
- Rose
- Sky
- Slate
- Stone
- Teal
- Violet
- Yellow
- Zinc

Each palette includes the tints from 50 to 950 (e.g., `amber50`, `amber100`, `amber200`, ..., `amber950`).

## Custom Colours
You probably have a custom colour set up on your site, something like:

```json
{
    "theme": {
        "extend": {
            "colors": {
                "primary": {
                    "50": "#F8EBE4",
                    "100": "#F2D7CC",
                    "200": "#E5AC9C",
                    "300": "#D87B6C",
                    "400": "#CB463B",
                    "500": "#9F2A2A",
                    "600": "#83232A",
                    "700": "#661B26",
                    "800": "#4A1420",
                    "900": "#2E0C16",
                    "DEFAULT": "#9F2A2A"
                }
            }
        }
    }
}
```

If you'd like to make your own stylesheet for it, you'll have to convert the colours to a Dart Color value.

To do this, I found a very useful webpage which will convert hex to Dart values: https://jonas-rodehorst.dev/tools/flutter-color-from-hex

Just paste your hex value into the box and it will give you the Dart colour.

Then add a line like the one below, giving it the proper name and replacing everything inside the parentheses with your Dart colour.

Remember to import dart:ui so you have access to Dart's Color objects.

```dart
import 'dart:ui';

const Color primary400 = Color(0xFFCB463B);
const Color primary500 = Color(0xFF9F2A2A);
const Color primary600 = Color(0xFF83232A);
```
