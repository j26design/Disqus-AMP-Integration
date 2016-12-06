# Disqus AMP Integration

## How to install

1. [Download amp.html](https://github.com/j26design/Disqus-AMP-Integration/blob/master/amp.html) and host the file on a different domain than where you intend to load Disqus. You can do this for free with [Amazon Cloudfront](https://portal.aws.amazon.com/gp/aws/developer/registration/index.html). **You do not *(and should not)* need to change the *amp.html* file for the integration to work.** The URL location of this file will be the URL that you will provide to the `src` attribute in step 3 below.

2. Place the following code anywhere within the `<body>` where you would like the comments to appear:

    ```html
    <amp-iframe width=600 height=140
                layout="responsive"
                sandbox="allow-scripts allow-same-origin allow-modals allow-popups allow-forms"
                resizable
                src="https://abc123.cloudfront.net/amp.html?shortname=museseo&fontBodyColor=333333&fontBodyFamily=sans-serif&fontLinkColor=03A9F4&url=https://www.j-26.com&identifier=12345">
    </amp-iframe>
    ```
    
## Configuration

Replace the URL in the example *(https://abc123.cloudfront.net/amp.html)* with the URL where you are hosting the `amp.html` file. The `src` URL provides 6 configurations. Only replace the text that comes after `=`.

|Option          |Description  |
|----------------|-------------|
|`shortname`     |Your disqus shortname.|
|`fontBodyColor` |The main font color of the page. **(You must replace with a hex value)**.|
|`fontBodyFamily`|The main font family of the page. Disqus provides 2 options: `sans-serif` or `serif`. Or replace with `inherit`.|
|`fontLinkColor` |The hyperlink font color. **(You must replace with a hex value)**.|
|`url`           |The URL that users will be directed to if they click on a link to the discussion. *This will likely be the canonical URL of the AMP page.*|
|`identifier`    |A unique identifier for the discussion. *This can be used to keep the comments on the AMP page in sync with the comments on the canonical page.* [Read more](https://help.disqus.com/customer/portal/articles/472098-javascript-configuration-variables#thispageidentifier)|

### Required script

Lastly, add the required script tag to the `<head>` of your amp pages to enable the `amp-iframe` tag. [Read more](https://www.ampproject.org/docs/reference/extended/amp-iframe.html):
    
```html
<script async custom-element="amp-iframe" src="https://cdn.ampproject.org/v0/amp-iframe-0.1.js"></script>
```
