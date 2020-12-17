# Template Assets

Each template needs a minimum of two files in order to work on the rM2. The PNG is used on the device while a page is open and being drawn over, while the SVG is used when the document is exported as a PDF.

[[source]](https://remarkablewiki.com/tips/templates)

## What about thumbnails?

You'll notice there are no thumbnails or icons to represent these templates for when the user selects one from the interface. Yep, there aren't any for the stock templates either. Why? Because these images are simple enough and compressible enough to be directly included in the `xochitl` binary. The only reference to them outside of the binary is in the `templates.json` file as the `iconCode` property. 

The JSON references these icons by a Unicode sequence. A list of the ones available and their codes can be found [here](https://remarkablewiki.com/tips/templates). As of right now, this repo will not be diving into making custom icons for the templates and will only be re-using existing ones.

If you're interested in the custom icon side-quest, try starting with the explanation provided [on reddit](https://www.reddit.com/r/RemarkableTablet/comments/kb8eai/custom_template_icons/gffdisx?utm_source=share&utm_medium=web2x&context=3).
