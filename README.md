# sc-ewon-flexy-common-docs
Repository for common documentation used in Ewon Flexy projects

## Requirements

### ScDocusaurusConfig.js
A `ScDocusaurusConfig.js` must exists in the `web-docs` directory and must match the format defined in the sc-java-maven-starter-project [ScDocusaurusConfig.js](https://github.com/hms-networks/sc-java-maven-starter-project/blob/main/web-docs/ScDocusaurusConfig.js) file.

## Example Usage

Example `module.exports` `plugins` section of `docusaurus.config.js`.

```js
plugins: [
  [
      "docusaurus-plugin-remote-content",
      {
          // options here
          name: "imported-docs", // used by CLI, must be path safe
          sourceBaseUrl: "https://raw.githubusercontent.com/hms-networks/sc-ewon-flexy-common-docs/main/docs/", // the base url for the markdown (gets prepended to all of the documents when fetching)
          outDir: "docs/imported", // the base directory to output to.
          documents: [
            "setup/_configuration.mdx",
            "setup/_installation_or_upgrade.mdx",
            "sys_req/_sys_req_ewon_fw.mdx",
            "sys_req/_sys_req_java.mdx",
            "sys_req/_sys_req_maven.mdx",
          ], // the file names to download
      },

  ],
  [
    "docusaurus-plugin-remote-content",
    {
        // options here
        name: "imported-images", // used by CLI, must be path safe
        sourceBaseUrl: "https://raw.githubusercontent.com/hms-networks/sc-ewon-flexy-common-docs/main/img", // the base url for the markdown (gets prepended to all of the documents when fetching)
        outDir: "static/img/imported", // the base directory to output to.
        documents: [
          "ewon/pages/ewon-tag-config-page-hist-logging.webp",
          "ewon/pages/ewon-web-page-home.webp",
          "ewon/setup/add-tag.gif",
          "ewon/setup/modify-tag.gif",
          "github/github-code-btn-download-zip.webp",
          "graphics/green-check-icon-cc0v1.webp",
          "hms/hms-logo-rgb.webp"
        ], // the file names to download
        requestConfig: { responseType: "arraybuffer" }
      }
  ],
  [
    "docusaurus-plugin-remote-content",
    {
        // options here
        name: "imported-js", // used by CLI, must be path safe
        sourceBaseUrl: "https://raw.githubusercontent.com/hms-networks/sc-ewon-flexy-common-docs/main/js", // the base url for the markdown (gets prepended to all of the documents when fetching)
        outDir: "src/components/imported", // the base directory to output to.
        documents: [
          "popover.js",
          "highlight.js"
        ], // the file names to download
      }
  ]
],
```