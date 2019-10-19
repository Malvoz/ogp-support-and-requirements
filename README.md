# Open Graph Protocol - Support & requirements

The Open Graph Protocol standard:  
Specification: https://ogp.me  
Github repo: https://github.com/facebook/open-graph-protocol  

<details id="documentation" name="documentation"><summary><strong>Documentation & tools</strong></summary>
<br>
  
Facebook:
- https://developers.facebook.com/docs/sharing/webmasters#markup
- https://developers.facebook.com/docs/sharing/best-practices/
- https://developers.facebook.com/docs/opengraph/music/
- Debugger: https://developers.facebook.com/tools/debug/og/object/
- Debugger: https://developers.facebook.com/tools/debug/sharing/

Twitter:
- https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/getting-started
- https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/markup
- https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/summary
- https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/summary-card-with-large-image
- https://developer.twitter.com/en/docs/tweets/optimize-with-cards/guides/troubleshooting-cards
- Validator: https://cards-dev.twitter.com/validator

Pinterest:
- https://developers.pinterest.com/docs/rich-pins/overview/
- https://developers.pinterest.com/docs/rich-pins/reference/
- https://developers.pinterest.com/docs/rich-pins/articles/
- Debugger: https://developers.pinterest.com/tools/url-debugger/

Yandex:
- https://yandex.com/support/webmaster/open-graph/intro-open-graph.html

LinkedIn:
- https://www.linkedin.com/help/linkedin/answer/46687/making-your-website-shareable-on-linkedin?lang=en

Messenger:
- https://developers.facebook.com/docs/messenger-platform/send-messages/template/open-graph/#metadata

Google+:
- <s>https://developers.google.com/+/web/snippet/</s>

<hr>
<br>
</details>

## Platform support

This support table identifies the support of Open Graph Protocol metadata across different platsforms. The supported properties are marked as either "Optional" or "Required", as interpreted from the corresponding [documentation](#documentation).

| Property 	| Facebook(<a href="#fb">*</a>) 	| Twitter(<a href="#twitter">*</a>) 	| Pinterest(<a href="#pinterest">*</a>) 	| LinkedIn 	| Yandex 	| Messenger(<a href="#fb-messenger">*</a>) 	|
|-----------------------------------	|----------------------------------------------	|---------	|-----------	|----------	|--------	|--------------	|
| `prefix="og: http://ogp.me/ns#"` 	|  	|  	|  	|  	|  	|  	|
| `og:type` 	|  Required	| Required	| Required: `article` 	|  	| Required 	|  	|
| `og:title` 	| Required 	|  Required (max 70 characters)	| Required 	| Required 	| Required 	| Required 	|
| `og:description` 	| Required 	| Required (max 200 characters) 	| Required 	| Required 	| Optional 	|  	|
| `og:url` 	|  Required 	| Required 	| Optional 	| Required 	| Required 	|  	|
| `og:site_name` 	| Optional 	|  	| Optional 	|  	| Optional 	| Required 	|
| `og:locale` 	|  Optional 	| 	| 	| 	| Optional 	|  	|
| `og:locale:alternate` 	| Optional 	| 	| 	| 	| Optional 	|  	|
| `og:audio` (or `og:audio:url`) 	|  Optional 	|  	|  	|  	| Optional 	| Required 	|
| `og:audio:type` 	| `audio/vnd.facebook.bridge` (non-standard MIME-Type value) for the Object Type [`music.song`](https://ogp.me/#type_music.song)	|  	|  	|  	| Optional 	|  `audio/vnd.facebook.bridge` (non-standard MIME-Type value) for the Object Type [`music.song`](https://ogp.me/#type_music.song)	|
| Allowed `audio` file size 	|  	|  	|  	|  	|  	|  	|
| `og:image` (or `og:image:url`) 	| Optional (only accepts `gzip` and `deflate` encodings) 	|   Required 	| Optional 	| Required 	| Required 	|  	|
| `og:image:type` 	| `image/jpeg`, `image/png`, `image/gif` 	| `image/jpeg`, `image/png`, `image/webp`, `image/gif` 	|  	|  	| Optional 	|  	|
| `og:image:height` 	| Optional	|  	|  	|  	| Optional 	|  	|
| `og:image:width` 	| Optional	| 	|  	|  	| Optional 	|  	|
| Allowed `image` file size 	| <span title="Equal to or less than">≤</span>8MB</span> 	| <span title="Less than"><</span>5 MB 	|	| <span title="Equal to or less than">≤</span>5 MB 	|	|  	|
  | Allowed `image` dimensions<br>(width x height in pixels) 	| <span title="Equal to or great than">≥</span>200x200 (Recommends <span title="Equal to or great than">≥</span>600x314) 	| <span title="Equal to or great than">≥</span>144x144,<br><span title="Equal to or less than">≤</span>4096x4096	|  	| <span title="Equal to or less than">≤</span>1200x627	|  	|  	|
| `image` aspect ratio 	| 1.91:1 (Recommended. Maximum 3:1) 	| 1:1 (Required)	|  	| 1.91:1 (Recommended) 	|  	|  	|
| `og:video` (or `og:video:url`) 	| Optional 	|  	|  	|  	| Optional 	| 	|
| `og:video:type` 	| `video/mp4`, `application/x-shockwave-flash` 	|  	|  	|  	| 	|  	|
| `og:video:height` 	| Required for `og:video` 	|  	|  	|  	|  Optional	|  	|
| `og:video:width` 	| Required for `og:video` 	|  	|  	|  	| Optional 	|  	|
| Allowed `video` file size 	|  	|  	|  	|  	|  	|  	|
| Allowed `video` dimensions (pixels) 	|  	|  	|  	| 	|  	|  	|
| `video` aspect ratio 	|  	|  	|  	|  	|  	|  	|
| `article:published_time` 	|  	|  	|  	|  	|  	| 	|
| `article:modified_time` 	|  	|  	| Optional 	|  	|  	| 	|
| `article:expiration_time` 	|  	|  	|  	|  	|  	| 	|
| `article:author` 	| Optional (Recommended if `property="og:type" content="article"` is used) 	|  	|  Optional	|  	|  	| 	|
| `article:section` 	|  	|  	| Optional 	|  	|  	| 	|
| `article:tag` 	|  	|  	| Optional 	|  	|  	| 	|
<!--| `book:author` 	|  	|  	| 	|  	|  	| 	|
| `book:isbn` 	|  	|  	| 	|  	|  	| 	|
| `book:release_date` 	|  	|  	| 	|  	|  	| 	|
| `book:tag` 	|  	|  	| 	|  	|  	| 	|
| `profile:first_name` 	|  	|  	| 	|  	|  	| 	|
| `profile:last_name` 	|  	|  	| 	|  	|  	| 	|
| `profile:username` 	|  	|  	| 	|  	|  	| 	|
| `profile:gender` 	|  	|  	| 	|  	|  	| 	|-->

<br>

## Notes

### `og:type`
`og:type` defaults to `website` per the specification (https://ogp.me), however most debuggers/validators complain when the property is missing, and will not show a link ("rich object/card") preview.

### `og:locale`

`og:locale` defaults to `en_US`, so if the `og:` property values are written in another language than (US) English (and therefore presumably the language of the HTML document is other than `<html lang="en(-XX)">`) then `og:locale` should be specified, with the appropriate ISO codes for `language_TERRITORY`.

### `og:image:alt`

`og:image:alt` isn't required by any of the reviewed platforms, however the property should always be specified, to provide alternative text for users with screen readers.

### `og:{image|video}:{height|width}`

According to the documentation, none of the platforms require dimensions to be set for images and videos, however it is recommended to do so, to enable pre-caching. This is best documented in Facebook's "Sharing Best Practices: [Pre-caching images](https://developers.facebook.com/docs/sharing/best-practices#precaching)".

### `og:{audio|image|video}:type`

The value of `og:{audio|image|video}:type` should correspond to the actual MIME-type of the media file.

### URLs
`og:url`, `og:{audio|image|video}(:url)` should preferrably all be absolute URLs. Relative URLs (specifically for images) would likely cause images not to be displayed in some platforms.

#### `og:{audio|image|video}:url VS og:{audio|image|video}:secure_url`?

If the resource is available over HTTPS - it is recommended to set `og:{audio|image|video}:url` (with `https://` in the URL) over `og:{audio|image|video}:secure_url` because both properties ultimately do the same thing, while the former is shorter, and not all the reviewed platforms' documentation mention the `:secure_url` version, so in worst case scenario it may not be supported everywhere `:url` is. Taking it one step further, `og:{audio|image|video}` is synonymous with `og:{audio|image|video}:url`, which is even shorter.

## Caveats

### <a name="fb" id="fb">Facebook</a>

Facebook supports `og:audio` and other audio-related properties, however the documentation for audio (or rather specifically music: https://developers.facebook.com/docs/opengraph/music/) says that it is only available for whitelisted partners. Only `og:audio:type` with the **non-standard** (MIME-Type) value `audio/vnd.facebook.bridge` is supported - forcing developers to set a value that other platforms most likely do not consume.

### <a name="fb-messenger" id="fb-messenger">(FB) Messenger</a>

Facebook Messenger [only supports sharing of _songs_](https://developers.facebook.com/docs/messenger-platform/send-messages/template/open-graph/#metadata).

### <a name="twitter" id="twitter">Twitter</a>

Twitter states that their parser will fall back to using OGP's `property="og:..."` as opposed to `name="twitter:..."`, does this imply they support the equivalent `og:` properties to their documented `twitter:` properties? E.g. `twitter:image:alt` is supported but there is [no mention of `og:image:alt`](https://developer.twitter.com/en/docs/tweets/optimize-with-cards/overview/markup).

### <a name="pinterest" id="pinterest">Pinterest</a>

With Pinterest you must **manually enable** "rich pins", by first [validating](https://developers.pinterest.com/tools/url-debugger/) the markup, and then apply to enable:

> You'll need to verify your Rich Pins before they'll appear on Pinterest.
>
> To validate and apply for Rich Pins:
>
> 1. Choose any page on your site that you've added metadata to. Enter your chosen URL below and click Validate.
> 2. Correct any problems you see with your metadata.
> 3. Select one of three options depending on how you marked up your page:
> [...]
> 4. Click Apply now. Your Rich Pins will show up within the hour.
>
> Note: You only need to validate and click apply for one link on your site to enable Rich Pins across your whole domain.


## Usage summary

As the support table suggests, for the widest coverage and to get the most benefit out of your Open Graph Protocol markup, it is recommended to specify at least these following properties:

- `og:type`
- `og:title`
- `og:description`
- `og:url`
- `og:site_name`
- `og:locale` if the Open Graph property values are written in another language than US English (and also `og:locale:alternate` if applicable)
- All URLs should be absolute
- Always use `https://` in URLs if possible

While some platforms "require" an image to be specified, it may not be possible/relevant for every web application and for every property. If possible, specify the properties and adhere to the following requirements:

- `og:image`
- `og:image:type` with a value of `image/jpeg`, `image/png`, `image/gif` or `image/webp` (should correspond to the actual MIME-Type of the file)
- `og:image:height` and `og:image:width` to allow for pre-caching images
- `og:image:alt` to provide an accessible name for visually impaired users who are using screen readers to understand your image
- A maximum image file size of 5MB
- The dimension of the image(s) should be at least `200x200`px and maximum `4096x4096`px

And in general, always specify sub-properties where possible, for example if `og:video` is used; then also set `og:video:type`, `og:video:height` and `og:video:width`, as some platforms may require it.
