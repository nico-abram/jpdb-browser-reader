# JPDB Web Reader Extension

A browser extension that parses any text in your browser using JPDB, and allows you to mine new vocabulary from any page!

## Is this ready to use yet?

Not really. It works, but it is buggy and the interface is quite ugly.

## Current Limitations

-   Always adds furigana
-   Overwrites existing furigana (including gikun)
-   Probably has many bugs

## Ongoing Work

-   Add customization options for furigana
-   Add Wikipedia integration
-   Make the UI nicer (particularly the mining dialog)
-   Make it work with a non-persistent background page
-   Add customization menus that don't require entering custom CSS directly

## Installation

### Chrome and other Chromium-based browsers
1.  Download the latest `.zip` file from the releases page
2.  Unpack the zip file in a location of your choosing
3.  Open up your browser and navigate to `chrome://extensions/`
4.  Check the `Developer mode` switch at the top right of your window
5.  Click the `Load unpacked` button at the top left
6.  In the file picker dialog, navigate to the folder you unpacked earlier. You should see a file called `manifest.json` inside the folder
7.  Click select/open/choose to exit the dialog and load the extension

### Firefox
1.  Download the latest `.xpi` file from the releases page
2.  Open Firefox
3.  Drag and drop the `.xpi` file into the Firefox window

That's it, you are done. If you are experiencing issues with drag and drop, you can try this alternate approach:

1.  Download the latest `.xpi` file from the releases page
2.  Open Firefox and navigate to `about:addons`
3.  Click on the little gear icon to the right of `Manage Your Extensions`
4.  Click `Install Add-on from File...`
5.  In the file picker dialog, select the `.xpi` file

## Building

You can run the following command to build a zip file:
The resulting file will be located in the `dist` folder
```sh
$ npm install
$ npm run build
```

For development, you can also run the build in watch mode:
```sh
$ npm install
$ npm run watch
```
This will continuously rebuild the source code as it changes, and place the output in the folder `build`.
It can be loaded as an unpacked extensino from there.
Please remember to reload (Firefox) / update (Chrome) the extension on the "manage extensions" page before testing your changes.

## Usage

On ttu reader (and Wikipedia, eventually): Parsing begins automatically on page load.

On all other pages: Select some text, right click, click "Parse ... with jpdb".

Words will be colored according to their state. Hover over words to see their meaning, and to mine or review them.

## Can I set it to only color new words?

Yes, paste this into the Custom Word CSS box in the settings:
```css
.jpdb-word.unparsed     { }
.jpdb-word.locked       { color: inherit; }
.jpdb-word.redundant    { color: inherit; }
.jpdb-word.not-in-deck  { color: rgb(126, 173, 255); }
.jpdb-word.new          { color: rgb(75, 141, 255); }
.jpdb-word.learning     { color: inherit; }
.jpdb-word.known        { color: inherit; }
.jpdb-word.never-forget { color: inherit; }
.jpdb-word.due          { color: inherit; }
.jpdb-word.failed       { color: inherit; }
.jpdb-word.suspended    { color: inherit; }
.jpdb-word.blacklisted  { color: inherit; }
```

## Contributing

Issues with feedback or ideas are welcome. You can also message me on the JPDB Discord server.

Because this project is still very early in development, the code will likely move too fast to meaningfully contribute to.
If that does not disuade you, feel free to submit pull requests anyway.

## License

[MIT](https://choosealicense.com/licenses/mit/)
