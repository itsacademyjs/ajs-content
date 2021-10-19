One of the main reasons HTML was created in the first place was to display text in a structured manner. Before we learn about displaying text in an HTML document, there are some things you need to know about white space characters.

White space characters consists of spaces, tabs and newlines. HTML treats these characters a little differently from the rest of the characters.

In general, a single whitespace character–including newlines–or a sequence of whitespace characters are treated as a single space and leading/trailing whitespace is eliminated. This is known as ‘collapsing whitespace’. Therefore the following two paragraphs are treated as if they were identical. 

Before we understand what Flow is, we need to know the difference between phrasing content and flow content.

Phrasing content is mainly whatever you put into paragraphs. For longer parts of text content inside your page, most of it should usually be organized into paragraphs. Paragraphs are the most basic level of structuring text content, same as you would have it in a traditional written text in a book or similar.

Phrasing content is made up of text content, embedded content elements and phrasing elements, possibly interspersed with HTML comments and/or white space.

Flow content is a broad category that encompasses most elements that can go inside the `<body>` element, including heading elements, sectioning elements, phrasing elements, embedding elements, interactive elements, and form-related elements. It also includes text nodes (but not those that only consist of white space characters).