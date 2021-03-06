---
layout: page
title: "JavaScript stream_context_get_default function"
comments: true
sharing: true
footer: true
sidebar: false
alias:
- /functions/view/stream_context_get_default:845
- /functions/view/stream_context_get_default
- /functions/view/845
- /functions/stream_context_get_default:845
- /functions/845
---
<!-- Generated by Rakefile:build -->
A JavaScript equivalent of PHP's stream_context_get_default

{% codeblock stream/stream_context_get_default.js lang:js https://raw.github.com/kvz/phpjs/master/functions/stream/stream_context_get_default.js raw on github %}
function stream_context_get_default (options) {
  // http://kevin.vanzonneveld.net
  // +   original by: Brett Zamir (http://brett-zamir.me)
  // -    depends on: stream_context_create
  // %          note 1: Although for historical reasons in PHP, this function can be used with
  // %          note 1: its options argument to set the default, it is no doubt best to use
  // %          note 1: stream_context_set_default() to do so
  // *     example 1: var context = stream_context_get_default();
  // *     example 1: get_resource_type(context);
  // *     returns 1: 'stream-context'
  // BEGIN REDUNDANT
  this.php_js = this.php_js || {};
  // END REDUNDANT
  if (!this.php_js.default_streams_context) {
    this.php_js.default_streams_context = this.stream_context_create(options);
  }
  if (options) {
    this.php_js.default_streams_context.stream_options = options;
  }

  return this.php_js.default_streams_context;
}
{% endcodeblock %}

 - [view on github](https://github.com/kvz/phpjs/blob/master/functions/stream/stream_context_get_default.js)
 - [edit on github](https://github.com/kvz/phpjs/edit/master/functions/stream/stream_context_get_default.js)

### Example 1
This code
{% codeblock lang:js example %}
var context = stream_context_get_default();
get_resource_type(context);
{% endcodeblock %}

Should return
{% codeblock lang:js returns %}
'stream-context'
{% endcodeblock %}


### Other PHP functions in the stream extension
{% render_partial _includes/custom/stream.html %}
