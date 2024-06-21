### HTTPs server

HTTP data between server and client is not encrypted, so it can be intercepted by third parties to gather data passed from the
server to the client. This can be addressed by using a secure version called HTTPS. **The news-aggregator server has to become
HTTPs instead of HTTP.**

Small hint: **net/http** library allows to achieve that.

#### Something to read
* [What is HTTPs?](https://habr.com/ru/post/593507/)
* [Example of TLS + HTTPs implementation in GoLang](https://gist.github.com/denji/12b3a568f092ab951456)
* [Certificates](https://smallstep.com/blog/everything-pki/#:~:text=A%20certificate%20is%20a%20data,certificate%20is%20called%20the%20subject.)
