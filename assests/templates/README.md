# Template Assets

Each template needs a minimum of two files in order to work on the rM2. The PNG is used on the device while a page is open and being drawn over, while the SVG is used when the document is exported as a PDF. Both files need to be brought over to the `/usr/share/remarkable/templates` directory, and the `template.json` file needs to be modified to include your new template.

The `template.json` file is one large JSON object with a single property, `templates`. This property is a list of objects, which of which describes the properties of each template. Here is an example of one template JSON object:

```json
{
    "name": "Blank",
    "filename": "Blank",
    "iconCode": "\ue9fd",
    "landscape": true,
    "categories": [
        "Creative",
        "Lines",
        "Grids",
        "Life/organize"
    ]
}
```

Each of these objects is separated by a comma and has at most five properties.

| Key | Required? | Description |
|-----|:---------:|-------------|
| name | yes | The name displayed on the tablet for the template|
| filename | yes | The name of the template file on the device without the document suffix (`.svg` or `.png`) |
| iconCode | yes | The Unicode sequence for the desired thumbnail |
| landscape | no | A boolean value to set the object as a landscape only template |
| categories | yes\* | A list of strings used to group templates in the interface |

\* Before the 2.6 update for reMarkable devices, the `categories` property was not required. It now is, but it can just be set to an empty list (`"categories": []`) to achieve the same effect as ommitting it in earlier versions.

The base filenames for each template should be the same so all relevant processes can identify them correctly. The only difference between these files should be their `.png` or `.svg` document types.

The only difference between some templates is whether or not the `landscape` property is included. The stock "Blank" templates use the same template files but the landscape view has the `"landscape": true` property applied to its object.

Categories are arbitrary. Any template that is included in the JSON file will be in the "All" list on the tablet. Templates with `"landscape": true` will only appear if the "Landscape" radio button is selected. Templates without it only appear if the "Portrait" radio button is selected. Aside form that, the category names are pulled from this template file, so if no templates have any categories, then no categories (besides "All") will appear when selecting a template. This also means you can add/remove whatever categories you want.

Don't forget to run `systemctl restart xochitl` when you've finished configuring your templates.

[[source]](https://remarkablewiki.com/tips/templates)

## What about thumbnails?

You'll notice there are no thumbnails or icons to represent these templates for when the user selects one from the interface. Yep, there aren't any for the stock templates either. Why? Because these images are simple and compressible enough to be directly included in the `xochitl` binary. The only reference to them outside of the binary is in the `templates.json` file as the `iconCode` property.

The JSON references these icons by a Unicode sequence. A list of the ones available and their codes can be found [here](https://remarkablewiki.com/tips/templates). As of right now, this repo will not be diving into making custom icons for the templates and will only be re-using existing ones.

If you're interested in the custom icon side-quest, try starting with the explanation provided [on reddit](https://www.reddit.com/r/RemarkableTablet/comments/kb8eai/custom_template_icons/gffdisx?utm_source=share&utm_medium=web2x&context=3).

## Available Templates

### Budgeting

<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/budgeting.png" width="15%" />

### Bug Form

<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/bugForm.png" width="15%" />

### Calendar

<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/calendar_day.png" width="15%" />

### Checklists

<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/checklist_1box3line_portrait.png" width="15%" style="display: inline-block;" />
<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/checklist_4box3line_portrait.png" width="15%" style="display: inline-block;" />

### Micro Pages

These templates were designed because the stock "small" templates still felt too big. There is currently variants for dot, grid, and ruled papers. Dot and graph templates are suitable for both portrait and landscape.

These were designed by using the same size and color dots as the original "small" dots template, but re-arranged into a 26px spaced grid. This makes for a 54 by 72 box grid. This is the same spacing for the grid and ruled papers. The ruled template has 105px top and left margins.

<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/dots_micro.png" width="15%" style="display: inline-block;" />
<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/grid_micro.png" width="15%" style="display: inline-block;" />
<img src="https://github.com/DanielRunningen/rM2Mods/blob/main/assests/templates/ruled_micro.png" width="15%" style="display: inline-block;" />
