# sc-ewon-flexy-common-docs
Repository for common documentation used in Ewon Flexy projects

## Requirements

### ScDocusaurusConfig.js
A `ScDocusaurusConfig.js` must exists in the `web-docs` directory and must match the format defined in the sc-java-maven-starter-project [ScDocusaurusConfig.js](https://github.com/hms-networks/sc-java-maven-starter-project/blob/main/web-docs/ScDocusaurusConfig.js) file.

## Example Usage

Example `module.exports` `plugins` section of `docusaurus.config.js`.

```js
  // Plugins
  plugins: [
    [
      "docusaurus-plugin-remote-content",
      {
        // Imported documents
        name: "imported-docs",
        sourceBaseUrl: ScDocusaurusConfig.commonDocsRepoUrl + 'docs/',
        outDir: "docs/imported",
        documents: [
          "setup/_configuration.mdx",
          "setup/_installation_or_upgrade.mdx",
          "sys_req/_sys_req_ewon_fw.mdx",
          "sys_req/_sys_req_java.mdx",
          "sys_req/_sys_req_maven.mdx",
        ],
      },
    ],
    [
      "docusaurus-plugin-remote-content",
      {
        // Imported images
        name: "imported-images",
        sourceBaseUrl: ScDocusaurusConfig.commonDocsRepoUrl + 'img',
        outDir: "static/img/imported",
        documents: [
          "ewon/pages/ewon-tag-config-page-hist-logging.webp",
          "ewon/pages/ewon-web-page-home.webp",
          "ewon/setup/add-tag.gif",
          "ewon/setup/modify-tag.gif",
          "github/github-code-btn-download-zip.webp",
          "graphics/green-check-icon-cc0v1.webp",
          "hms/hms-logo-rgb.webp"
        ],
        requestConfig: { responseType: "arraybuffer" }
      }
    ],
    [
      "docusaurus-plugin-remote-content",
      {
        // Imported javascript
        name: "imported-js",
        sourceBaseUrl: ScDocusaurusConfig.commonDocsRepoUrl + 'js',
        outDir: "src/components/imported",
        documents: [
          "highlight.js",
          "popover.js"
        ],
      }
    ]
  ],
```