## About the Noctus Theme

> [!WARNING]
> ATTENTION - This is the discontinued version of the theme! Only have it around to bridge the gap for a rework.
> A remake in SCSS has been started [here](https://codeberg.org/Shaydelity/obsidian-noctus-theme).

The Noctus Theme for Obsidian is a theme made with the intent to be as modular **as possible**, which is why it was initially known as the "Modulo Theme". It uses Oklch instead of RGB as a color space, which allows for more modular treatment of colors and better gradients **BUT also leads to many snippets becoming incompatible with this theme. *Yet we intend to make snippets of our own to both extend the functions of this theme but also offer beloved snippets compatible with our theme.***

Initially, this theme was just a modified version of the [Obsidian Encore Theme by Carbonateb](https://github.com/carbonateb/obsidian-encore-theme) but overtime I, Shayde, looked at other themes, like the [Minimal Theme](https://github.com/kepano/obsidian-minimal) by kepano, and started making it a theme of its own.

Around that time I also started working on an obsidian snippet that would change the colors, functions, and similar of callout when putting in different callout (meta-) data, which has become a major function in this theme and has long surpassed the snippet since. I have added formats, like a timeline callout based on harr's [Timeline CSS](https://forum.obsidian.md/t/css-snippet-timeline-as-callout/93652) and more.

### Installation

As the theme is still a work in progress, it is not yet in the official Obsidian theme store; Thus, if you want it to be kept up to date, using the [BRAT Plugin by TfTHacker](https://github.com/TfTHacker/obsidian42-brat) is recommended.

#### Steps

1. Install the BRAT plugin from the obsidian plugin store
2. Enable it and go into the options
3. Below "Beta themes list", press "Add beta theme" and paste this repository's link into it (`https://github.com/Reparse-dev/noctus-obsidian-theme`)
4. Press "Add theme" and presto- it's done! Enjoy the Noctus Obsidian Theme ^-^

### Features

1. Usage of Oklch instead of RGB: Allows more precise gradients and more modular coloring.
2. New Callout Formats: Timeline callouts and a reverse callout (places title below content).
3. New Callout Presets: Highlight, Result, and Solution.
4. Modular Callouts: Allows changing colors and icons of all Presets and Formats, even down to precise color value changes and more!
5. Options using the [Style Settings Plugin](https://github.com/mgmeyers/obsidian-style-settings)
6. A focus on PDF compatibility and enhancements (if there is anything lacking, please let us know by opening an issue!)

#### Style Settings

1. Line-length, featuring line lengths made to approximate PDF exports (based on their export font size) and line lengths for [optimal readability](https://baymard.com/blog/line-length-readability). Can be used for only reading view, or with live and source editing view as well!
2. Text-Alignment, featuring block (or justify), right aligned, left aligned, and centered options! Can be changed on a per-notes basis using the css classes which are formated like this: `text-align-[alignment]` (alignment options: block (or justify), right, left, center)

> For changing colors you will find simple instructions in the **Color Styling** section!

#### Plugin Integrations

We integrate CSS for plugins we personally use into the base theme, given the CSS for it is not exessive as to warrant a CSS Snippet of its own. All of these plugins are worth checking out!

**List of currently integrated Plugins**
- [Calendar Plugin by Liam Cain](https://github.com/liamcain/obsidian-calendar-plugin)
- [Dataview Plugin by Michael Brenan](https://github.com/blacksmithgu/obsidian-dataview)
- [Datacore Plugin by Michael Brenan](https://github.com/blacksmithgu/datacore)
- [Chat View by Aditya Majethia](https://github.com/adifyr/obsidian-chat-view) (WIP)
- [Excalidraw Plugin](https://github.com/zsviczian/obsidian-excalidraw-plugin) (Currently only removes the Excalidraw welcome)

### Making CSS Snippets

Obsidian Snippets are CSS files that are put in the `.obsidian/snippets` (You might have to make hidden files visible in your explorer to find the .obsidian folder!) folder and overwrite/alter the theme CSS. To make one, you create a text file and write CSS code in it and change its extension from `.txt` to `.css` afterwards.

#### Color Styling

One of the main aspects of this theme is that it relies on the oklch color space. Thus, the color picking from the style settings plugin is not used as it only supports hex and rgb color spaces.

> If you are not well accustomed to CSS, skip to the template section!

Every color in this theme is split into multiple variables, like this:

`--colorname-lightness`, `--colorname-chroma`, `--colorname-hue`

`--colorname-color: var(--colorname-lightness) var(colorname-chroma) var(colorname-hue)`

For some, like blockquote or callout color we also have opacity variables: `--colorname-opacity`

And then, for each element, the colors are implemented akin to this:
```css
element {
  color: oklch(var(--colorname-color) / var(--colorname-opacity))
}
```
##### Template for Primary & Accent Color changes

> To know what your favorite hex or rgb color is in oklch, use this website: [oklch.com](https://oklch.com/)!

Copy and paste this into a text file and change the [new value] to oklch values. Once done, change the file extension from `.txt` to `.css` and put it into the `.obsidian/snippets` (You might have to make hidden files visible in your explorer to find the .obsidian folder!).

```css
body {
  /* Changing Text Color (default: white) */
  --primary-lightness: [new value]%;
  --primary-chroma: [new value];
  --primary-hue: [new value];
  --primary-color: var(--primary-lightness) var(primary-chroma) var(--primary-hue);

  /* Changing Primary Accent Color (default: violet) */
  --primary-accent-lightness: [new value]%;
  --primary-accent-chroma: [new value];
  --primary-accent-hue: [new value];
  --primary-accent-color: var(--primary-accent-lightness) var(primary-accent-chroma) var(--primary-accent-hue);

  /* Changing Secondary Accent Color (default: crimson (red)) */
  --secondary-accent-lightness: [new value]%;
  --secondary-accent-chroma: [new value];
  --secondary-accent-hue: [new value];
  --secondary-accent-color: var(--secondary-accent-lightness) var(secondary-accent-chroma) var(--secondary-accent-hue);
}
```

#### Theme Snippets



### Contributing

Contributions via documentation, and general improvements (like "bug fixes") are always welcome. For more major feature work, make an issue about the feature idea / reach out to me so we can judge if it is right for us and how best to implement it.

#### Dev Ressources

- https://oklch.com/
- https://lucide.dev/icons/
- https://github.com/chrisgrieser/obsidian-theme-design-utilities
