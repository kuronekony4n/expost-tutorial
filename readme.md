![Showcase](https://github.com/kuronekony4n/expost-tutorial/raw/main/showcase.jpg)

# Expost? What is this?
Expost is a platform designed to help you easily create and manage lists of links, files, or text in a Directory styles. 
By using JSON or YAML, you have the flexibility to customize your list exactly how you want it. You can choose from a wide variety of objects options, add images or other multimedia, link to external resources, and even embedding an entire websites.

![Comparison](https://github.com/kuronekony4n/expost-tutorial/raw/main/comparison.png)
See the result here: [Expost](https://expost.pages.dev/)

## Tutorial Video!
[Basic Tutorial (with English Subs)](https://youtu.be/Prg6eiUJacw)
[Talking about Live Editor (with English Subs)](https://youtu.be/Lh-EArPmzdQ)

[![OPEN](https://raw.githubusercontent.com/kuronekony4n/expost-tutorial/main/open-live-editor.png)](https://expost.pages.dev/create/creator)

## Shortcut
Blocks: [Metadata](#metadata-block), [Directory](#directory-block), [Title](#title-block), [Text](#text-block), [Link](#link-block), [Admonition](#admonition-block), [Button](#button-block), [Divider](#divider-block), [Space](#space-block), [Image](#image-block), [Audio](#audio-block), [Video](#video-block), [Iframe](#iframe-block)

Other: [Custom CSS](#custom-css), [Hosting](#hosting), [Redirection](#redirection), [Using Github](#using-github), [Contributing](#contributing)

# Create New Library
## Pre-made Examples
[From this JSON](https://github.com/kuronekony4n/expost-tutorial/blob/main/homepage/homepage.json) or [this YAML](https://github.com/kuronekony4n/expost-tutorial/blob/main/homepage/homepage.yaml), become [This Website!](https://expost.pages.dev/)

You can start by editing that JSON/YAML as a template, or Make from scratch!

## Blocks
Blocks is essentialy an item, or objects that you can add. 
Each blocks type will render differently, and have different key you can set.
Optional key means that is not required, you can leave it empty or even delete the key. It will use the default settings.
You can add any blocks inside a directory. Even a bunch of directories inside a directory!

### Metadata Block
#### Using JSON
```json
{
  "img": "https://website.com/logo.png",
  "type": "metadata",
  "css": "",
  "expand": false,
  "nsfw": false,
  "author": "John Doe",
  "author_link": "https://website.com",
  "title": "Welcome to the Library",
  "subtitle": "Hope you have a wonderful day!",
  "info": "This library is containing a lot of useful things!"
}
```
#### Using YAML
```yaml
img: 'https://website.com/logo.png'
type: metadata
css: ''
expand: false
nsfw: false
author: John Doe
author_link: 'https://website.com'
title: Welcome to the Library
subtitle: Hope you have a wonderful day!
info: This library is containing a lot of useful things!
```
This is a special block that **appears only once at the beginning** of the JSON data. It contains information about the Library being represented.

Key | Value | Required | Description
:------: | :------: | :------: | :------
img | `url` | optional | URL for an image or logo. 
type | metadata | required | Specifies that this block is a metadata.
css | `url` | optional | URL for a custom CSS stylesheet.  [How?](#custom-css)
expand | `boolean` | optional | Expand all directories. Good for testing. Default: `false`.
nsfw | `boolean` | optional | Display NSFW warning before opening the library. Default: `false`.
author | `string` | optional | Name of the author. 
author_link | `url` | optional | URL to the author's website. 
title | `string` | optional | The title of the library. 
subtitle | `string` | optional | The subtitle of the library. 
info | `string` | optional | Additional information about the library. 

### Directory Block
#### Using JSON
```json
{
  "name": "directory name",
  "type": "dir",
  "info": "information about this directory",
  "custom_class": "",
  "custom_style": "",
  "hidden": false,
  "data": [
    {
      "name": "directory 2 name",
      "type": "dir",
      "info": "information about this seconds directory",
      "data": []
    },
    {
      "name": "link name",
      "type": "link",
      "info": "information about this link",
      "data": "https://website.com/links"
    }
  ]
}
```
#### Using YAML
```yaml
name: directory name
type: dir
info: information about this directory
custom_class: ''
custom_style: ''
hidden: false
data:
  - name: directory 2 name
    type: dir
    info: information about this seconds directory
    data: ''
  - name: link name
    type: link
    info: information about this link
    data: 'https://website.com/links'
```
This represents a directory or folder. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | required | Directory name.
type | dir | required | To declare that this is a directory.
info | `string` | optional | Information about the directory.
data | `blocks` | optional | Other block(s) for the content inside the directory.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Title Block
#### Using JSON
```json
{
  "name": "Title name",
  "type": "title",
  "info": "title info",
  "font_size": "medium",
  "align": "left",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Title name
type: title
info: title info
font_size: medium
align: left
custom_class: ''
custom_style: ''
hidden: false
```
This represents a title. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | required | Title name.
type | title | required | To declare that this is a title.
info | `string` | optional | Information about the title.
font_size | `small`, `medium`, `large` | optional | Font size for the title. Default: `medium`.
align | `left`, `center`, `right` | optional | Text alignment. Default: `left`.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Text Block
#### Using JSON
```json
{
  "name": "Text name",
  "type": "text",
  "info": "text info",
  "font_size": "medium",
  "align": "left",
  "data": "This is the text content! [n] Very epic.",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Text name
type: text
info: text info
font_size: medium
align: left
data: 'This is the text content! [n] Very epic.'
custom_class: ''
custom_style: ''
hidden: false
```
This represents a text. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | optional | Text name.
type | title | required | To declare that this is a text.
info | `string` | optional | Information about the text.
font_size | `small`, `medium`, `large` | optional | Font size for the text. Default: `medium`.
align | `left`, `center`, `right` | optional | Text alignment. Default: `left`.
data | `string` | required | The text's content. Use `[n]` for making a new line.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Link Block
#### Using JSON
```json
{
  "name": "Link name",
  "type": "link",
  "info": "link info",
  "icon": "rocket",
  "download": false,
  "data": "https://website.com/",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Link name
type: link
info: link info
icon: rocket
download: false
data: 'https://website.com/'
custom_class: ''
custom_style: ''
hidden: false
```
This represents a Link. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | required | Link name.
type | link | optional | To declare that this is a link. (Any type that not in the list will be consider to be a link, so this is optional).
info | `string` | optional | Information about the text.
icon | `string` | optional | Icons for the link. Default: `file`.  [Icons list](https://expost.pages.dev/icons). Tip: add `2x` before the icon's name to enlarge the icon slightly, Example: `bus` became `2xbus`. 
download | `boolean` | optional | Make user download a file on button click. Default: `false`.
data | `url` | optional | URL which the link will redirect to.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Admonition Block
#### Using JSON
```json
{
  "name": "Admonition name",
  "type": "admonition",
  "info": "admonition info",
  "font_size": "medium",
  "align": "left",
  "style": "warning",
  "data": "This is the text content! [n] Very epic.",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Admonition name
type: admonition
info: admonition info
font_size: medium
align: left
style: warning
data: 'This is the text content! [n] Very epic.'
custom_class: ''
custom_style: ''
hidden: false
```
This represents an admonition. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | optional | Admonition name.
type | admonition | required | To declare that this is an admonition.
info | `string` | optional | Information about the admonition.
font_size | `small`, `medium`, `large` | optional | Font size for the text. Default: `medium`.
align | `left`, `center`, `right` | optional | Text alignment. Default: `left`.
style | `note`, `info`, `warning`, `danger` | optional | The admonition's style. Default: `info`.
data | `string` | optional | The text's content.  Use `[n]` for making a new line.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Button Block
#### Using JSON
```json
{
  "name": "Button name",
  "type": "button",
  "info": "button info",
  "font_size": "medium",
  "wide": false,
  "style": "warning",
  "download": false,
  "data": "https://website.com/button",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Button name
type: button
info: button info
font_size: medium
wide: false
style: warning
download: false
data: 'https://website.com/button'
custom_class: ''
custom_style: ''
hidden: false
```
This represents a button. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | required | Button name.
type | button | required | To declare that this is an button.
info | `string` | optional | Information about the button.
font_size | `small`, `medium`, `large` | optional | Font size for the text. Default: `medium`.
wide | `boolean` | optional | Make the button span to the entire width. Default: `false`.
style | `light`, `dark`, `primary`, `secondary`, `success`, `danger`, `warning`, `info` | optional | The button's style. Default: `light`.
download | `boolean` | optional | Make user download a file on button click. Default: `false`.
data | `url` | required | URL which the button will redirect to.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Divider Block
#### Using JSON
```json
{
  "type": "divider",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
type: divider
custom_class: ''
custom_style: ''
hidden: false
```
Divider make a horizontal line to separate element beautifully.

Key | Value | Required | Description
:------: | :------: | :------: | :------
type | divider | required | To declare that this is a divider.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Space Block
#### Using JSON
```json
{
  "type": "space",
  "value": 10,
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
type: space
value: 10
custom_class: ''
custom_style: ''
hidden: false
```
Make a blank space. Use this for separating a non-wide button, or just for spacing problem.

Key | Value | Required | Description
:------: | :------: | :------: | :------
type | space | required | To declare that this is a space.
value | `number` | required | Determine the spaces (in pixel). Example: for making a 20px space between blocks, set the value to 20. You can also put negative number.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Image Block
#### Using JSON
```json
{
  "name": "Image name",
  "type": "image",
  "info": "image info",
  "download": false,
  "url" : "https://website.com/albums",
  "data": "https://website.com/image.png",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Image name
type: image
info: image info
download: false
url: 'https://website.com/albums'
data: 'https://website.com/image.png'
custom_class: ''
custom_style: ''
hidden: false
```
This represents an Image. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | optional | Button name.
type | image | required | To declare that this is an image.
info | `string` | optional | Information about the image.
download | `boolean` | optional | Make user download a file on click. Default: `false`.
url | `url` | optional | URL for user to open on click.
data | `url` | required | URL for the image file.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Audio Block
#### Using JSON
```json
{
  "name": "Audio name",
  "type": "audio",
  "info": "audio info", 
  "download": true,
  "audio_type": "audio/mp3",
  "data": "https://website.com/music.mp3",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Audio name
type: audio
info: audio info
download: true
audio_type: audio/mp3
data: 'https://website.com/music.mp3'
custom_class: ''
custom_style: ''
hidden: false
```
Add audio player. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | optional | Audio name.
type | audio | required | To declare that this is an audio.
info | `string` | optional | Information about the audio.
download | `boolean` | optional | Show download button for the audio. Default: `false`.
audio_type | `string` | required | Audio type template. Example: `audio/mp3`. [Supported list](http://www.iana.org/assignments/media-types/media-types.xhtml#audio).
data | `url` | required | URL for the audio file.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Video Block
#### Using JSON
```json
{
  "name": "Video name",
  "type": "video",
  "info": "video info", 
  "download": true,
  "video_type": "video/mp4",
  "video_poster": "https://website.com/thumbnail.png",
  "data": "https://website.com/video.mp4",
  "custom_class": "",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Video name
type: video
info: video info
download: true
video_type: video/mp4
video_poster: 'https://website.com/thumbnail.png'
data: 'https://website.com/video.mp4'
custom_class: ''
custom_style: ''
hidden: false
```
Add video player. 

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | optional | Video name.
type | video | required | To declare that this is an video.
info | `string` | optional | Information about the video.
download | `boolean` | optional | Show download button for the video. Default: `false`.
video_type | `string` | required | Video type template. Example: `video/mp4`. [Supported list](http://www.iana.org/assignments/media-types/media-types.xhtml#video).
video_poster | `url` | optional | Video's thumbnail.
data | `url` | required | URL for the video file.
custom_class | `string` | optional | Add custom CSS Classes.
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

### Iframe Block
#### Using JSON
```json
{
  "name": "Iframe name",
  "type": "iframe",
  "info": "iframe info", 
  "width": "100%",
  "height": "auto",
  "scrolling": false,
  "allowfullscreen": true,
  "data": "https://www.youtube.com/embed/1m-KtU88K9Y",
  "custom_class": "ar16-9",
  "custom_style": "",
  "hidden": false
}
```
#### Using YAML
```yaml
name: Iframe name
type: iframe
info: iframe info
width: 100%
height: auto
scrolling: false
allowfullscreen: true
data: 'https://www.youtube.com/embed/1m-KtU88K9Y'
custom_class: ar16-9
custom_style: ''
hidden: false
```
Embed external player or an entire website.

Key | Value | Required | Description
:------: | :------: | :------: | :------
name | `string` | optional | Iframe name.
type | iframe | required | To declare that this is an iframe.
info | `string` | optional | Information about the iframe.
width | `string` | optional | The width of the iframe. Example: `50%`/`300px`/`auto`. Default: `100%` (recommended).
height | `string` | optional | The height of the iframe. Example: `50%`/`120px`/`auto`. Default: `auto` (recommended).
scrolling | `boolean` | optional | Enable scrolling. Default: `false`.
allowfullscreen | `boolean` | optional | Allow Fullscreen. Default: `false`.
data | `url` | required | URL for the iframe destination.
custom_class | `string` | optional | Add custom CSS Classes. Tips: For iframe, use `ar16-9` for youtube player so the aspect ratio of the iframe is automaticaly 16:9, you can also use other aspect ratio template: `ar16-9` (landscape), `ar5-7` (potrait), `ar1-1` (square).
custom_style | `string` | optional | Add custom CSS Styles.
hidden | `boolean` | optional | Hide the block.

## Custom CSS
You can edit the default CSS: https://expost.pages.dev/style.css
And then upload it online (ex. github gist) and put the URL in [`css`](#L-1-4) key inside [Metadata Block](#L-1-4).
I recommend you use this [browser extension](https://chrome.google.com/webstore/detail/user-css/okpjlejfhacmgjkmknjhadmkdbcldfcb) when editing the css so you get live result.

## Hosting
There is several way on how to host the JSON or YAML you just created.
Currently we supported:

Website | RAW Data | Result | Support Edit
:------: | :------: | :------: | :------:
direct url | https://website.com/library.yaml | https://expost.pages.dev/?url=https://website.com/library.yaml | Yes
[snippet.host](https://snippet.host) | https://snippet.host/bsgxcc | https://expost.pages.dev/?s=bsgxcc | Yes
[rentry.co](https://rentry.co) | https://rentry.co/custom_url999 | http://expost.pages.dev/?r=custom_url999 | Yes
[pst.moe](https://pst.moe) | https://pst.moe/paste/esmcue | http://expost.pages.dev/?p=esmcue | No

I suggest using Snippet or Rentry when creating or editing, as these websites update instantly unlike Github, which may take 1-2 minutes to reflect changes.

### Redirection
Using [rentry.co](https://rentry.co), you can turn your long direct URL using preserved and short URL.

Make a new Rentry and then put this JSON inside:
```json
{
  "type": "redirect",
  "data": "https://kuronekony4n.github.io/expost-tutorial/example/redirect-destination.json"
}
```
Key `data`'s value is your full long direct URL.

Example RAW Data | Example Result
:------: | :------:
https://rentry.co/redirect-example | https://expost.pages.dev/?u=redirect-example

### Using Github
You can easily store all your JSON or YAML files, as well as any other kind of asset, in a Github repository. However, if you're using Github repository, it's important to keep in mind that simply updating your files won't automatically update the information on expost websites. To ensure that your updates are reflected, create a Github Pages based on your repository and use the links from there. This way, you can avoid having different URLs each time you make changes, and your updates will show up automatically.

### Contributing
You can contribute in many ways:
- Making a Library
- Making a Custom CSS
- Translating this Guide to other language
- Redesign Everything

You can submit your contribution by Creating an Issue. 
