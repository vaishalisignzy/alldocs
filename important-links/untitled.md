---
description: My cute description
---

# Let's rpcl

```
var matchNamesIblSequence = function(name1, name2) {

  name1 = name1.toLowerCase();
  name2 = name2.toLowerCase();

  var matchingMatching = false;

  // Exact match case
  if (name1 == name2) {
    matchingMatching = true;
  }

  // Matches in reverse order
  if (name1 == name2.split(' ').reverse().join(' ')) {Are
    matchingMatching = true;
  }

  // Check if both names are of length 2
  if (name1.split(' ').length > 2 && name2.split(' ').length > 2) {
    // statement

    var splitName1 = name1.split(' ');
    var splitName2 = name2.split(' ');

    try {
      // If first of name1 matches first of name2
      // and last of name1 matches last of name2
      // and first letters of firstnames of name1 and name2 match (This condition seems random)

      if (splitName1.shift() == splitName2.shift() && splitName1.pop() == splitName2.pop() && splitName1[0][0] == splitName2[0][0]) {
        matchingMatching = true;
      }
    } catch (e) {
      console.log(e);
    }
  }

  if (name1.split(' ').length < 3 && name2.split(' ').length < 3 && name1.split(' ').length > 1 && name2.split(' ').length > 1) {

    // If first letter of name1 and name 2 match
    // OR
    // firt name's firstname is equal to 

    if (name1.split(' ')[0] == name2.split(' ')[0] || name1.split(' ')[0] == name2.split(' ')[name2.length - 1]) {
      matchingMatching = true;
    }

    if (name1.split(' ')[name1.length - 1] == name2.split(' ')[0] || name1.split(' ')[name1.length - 1] == name2.split(' ')[name2.length - 1]) {
      matchingMatching = true;
    }
  }

  return matchingMatching;
}
```

{% swagger baseUrl="https://signzy.com" path="/api" method="post" summary="SOMETHING" %}
{% swagger-description %}
Some descirption
{% endswagger-description %}

{% swagger-parameter in="path" name="" type="string" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="" type="number" %}
Some description
{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
{
    "chacha": "chow"
 }
 
```
{% endswagger-response %}
{% endswagger %}

{% embed url="https://signzy.com/" %}

{% embed url="https://www.youtube.com/embed/2C6RD0vTeyE" %}

{% embed url="https://api.apiembed.com/?source=https://signzy.xyz/cdn/indiagate/login.json" %}

{% embed url="https://codepen.io/davidkpiano/pen/wMqXea" %}

{% embed url="https://codepen.io/yuyudhan/pen/oJqqWY" %}

> Something
>
> Awesome

```markup
<iframe src="https://api.apiembed.com/?source=https://signzy.xyz/cdn/indiagate/login.json" frameborder=0 style="width: 600px; height: 500px;"> </iframe>
```

{% tabs %}
{% tab title="First Tab" %}

{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

