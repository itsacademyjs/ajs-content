A content delivery network (CDN) is a group of servers that work together to
transfer assets like HTML pages, JavaScript files, stylesheets, images, and videos
quickly. The servers are geographically distributed to increase delivery speeds.

The popularity of CDN services continues to grow, and today the majority of web traffic
is served through CDNs. This includes traffic from major sites like Facebook, Netflix, and Amazon.

One question that you might have right now is, are CDNs just like web servers? Well, not really.
While a CDN does not host content and can’t replace the need for proper web hosting, it does help
cache content at the network edge, which improves website performance. Many websites struggle to
have their performance needs to be met by traditional hosting services, which is why they opt for
CDNs.

So why do you need to know all this? Well, you are going to be using React from a CDN! At least for
the first half of this chapter. Later, you will learn how to use Create React App using Yarn.

For now, just add the following inside the body of your index.html HTML file.

**index.html**
```html
<script
    crossorigin
    src="https://unpkg.com/react@17/umd/react.development.js"
></script>
<script
    crossorigin
    src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"
></script>
<script src=”/scripts/app.js”></script>
```