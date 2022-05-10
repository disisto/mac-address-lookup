<p align="center">
<a href="https://troubleshooting.tools/lookup/mac/"><img src="https://troubleshooting.tools/assets/img/troubleshooting.tools/gh_logo.png" height="200"></a>
</p>

# MAC Address Lookup 

MAC address lookup by troubleshooting.tools resolves the entered MAC/OUI/CID/IAB address to the assign vendor including additional information like vendor name, address, block category, size and range.

## Content
<ol>
<li>) Web page</li>
<li>) Webhook</li>
<li>) Open Graph</li>
<li>) OpenSearch</li>
<li>) HTML search form</li>
<li>) API</li>
<li>) Limitations and caveats</li>
</ol>


## 1.) Web page

Look up single MAC address
<ol>
<li>Visit with a web browser https://troubleshooting.tools/lookup/mac/</li>
<li>Enter a MAC address in the search form</li>
<li>Hit enter key or submit button</li>
</ol>

Look up multiple MAC addresses simultaneously
<ol>
<li>Visit with a web browser https://troubleshooting.tools/multi/lookup/mac/</li>
<li>Paste the ARP table that has been copied from the Windows CMD, MAC/Linux terminal or similar in the search form</li>
<li>Hit enter key or submit button</li>
</ol>


## 2.) Webhook

Beside the classic form input on the web page, the web page supports also webhooks. This possibility is ideal to share a link and guide the recipient directly to the results.

**URL:** **`https://troubleshooting.tools/lookup/mac/`** `{mac_address}` <br><br>
Example: `https://troubleshooting.tools/lookup/mac/B8F2551F2E3D`

## 3.) Open Graph

Sharing the Webhook link into a web page or app that support the Open Graph protocol gives the opportunity to share a small excerpt of the results, without that the recipient need to visit the webpage itself.

Examples

Slack:<br>
<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opengraph/slack.jpg" style="width: 50%; height: 50%">

Discord:<br>
<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opengraph/discord.jpg" style="width: 50%; height: 50%">

Mattermost:<br>
<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opengraph/mattermost.jpg" style="width: 50%; height: 50%">

WhatsApp:<br>
<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opengraph/whatsapp.jpg" style="width: 50%; height: 50%">

Telegram:<br>
<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opengraph/telegram.jpg" style="width: 50%; height: 50%">

Twitter:<br>
<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opengraph/twitter.jpg" style="width: 50%; height: 50%">


## 4.) Open Search

The browser integration of troubleshooting.tools allows to use the browser address bar as a search input field, when needed, without visiting the original web page before.

This function is called OpenSearch and works with Apple Safari, Microsoft Edge, Mozilla Firefox and Google Chrome. Before we can start using it, we have to setup our browser for this function. Here an example for Google Chrome:

At the top right, click More <img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/0_menu.jpg"> and then **Settings**.

<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/1_google_chrome_settings.jpg">

Under "Search engine," click **Manage search engines**.

<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/2_manage_search_settings.jpg">

To the right of "Other search engines," click **Add**.

<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/3_search_engine_settings.jpg">

Fill out the text fields as shown below and click **Add**.

<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/4_edit_search_engine.jpg" align="right">

**Search engine:**<br>
`Enter troubleshooting.tools or a name of your choice.`

**Keyword:**<br>
`Enter the character "t" or a keyword of your choice, to trigger later the search function.`

**URL with %s in place of query:**<br>
`https://troubleshooting.tools/lookup/mac/%s`

<br><br><br><br><br>

The setup is complete. You are still able to continue to enter a URL in the address bar or any search terms that trigger a Google search.

<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/5_google_search_bar.jpg">

The new feature is, if you enter an "t" followed by a space, then you activate the troubleshooting.tools search.

<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/6_troubleshooting.tools_search_bar_a.jpg">

<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/7_troubleshooting.tools_search_bar_b.jpg">

This cause that Google Chrome address bar react like the search field on this website.

<img src="https://github.com/disisto/mac-address-lookup/blob/main/img/opensearch/8_troubleshooting.tools_search_bar_c.jpg">

## 5.) HTML search form

To integrate the search bar into a different web page a few line are needed. The look and feel can be adjusted as desired.

```html
<form method="post" action="https://troubleshooting.tools/lookup/mac/">
  <input type="text" name="MACADDRESS" placeholder="">
  <input type="submit" value="&#128269;">
</form>
```

## 6.) API

The API allows to integrate the results of the MAC Address Lookup results on a different web page or app. Different formats of outputs are available, which can be adjust based on the need.

| Format | Level      | URL | Output |
| ----------------- |:------- | :---| :---|
| Plaintext   | 0 | `https://api.troubleshooting.tools/lookup/mac/` `{mac_address}` | Vendor |
| JSON   | 0 | `https://api.troubleshooting.tools/lookup/mac/json/` `{mac_address}` | OUI, Block category, Block size, Block range, Vendor name, Vendor address |

Error handling:
- Invalid input: Every input that can\'t be identified as MAC address will trigger an error message.
- No entry found: Entered MAC address has a valid format, but there is no mach with database.
- Rate Limit: IP addresses of clients that make more than 250 requests/second<sup>[1]</sup> get blocked for 60 minutes.

## 7.) Limitations and caveats

### API rate limit

- <sup>[1]</sup>The rate calculation is based on laboratory values ​​and is adapted to the real conditions under constant monitoring.

---
All mentioned trademarks are the property of their respective owners.
