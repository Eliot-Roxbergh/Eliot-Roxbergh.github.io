# Test

words

## Ttest

{% include_relative posts/GPL_compliance.md %}

test

{% capture my_include %}{% include posts/GPL_compliance.md %}{% endcapture %}
{{ my_include | markdownify }}
