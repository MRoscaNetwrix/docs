# Understanding Browser Router Rules

When you make a new Browser Router policy, you have several ways to make site rules: __URL__, __Wildcard__, __RegEx__, and __Internet Security Zone__.

![about_policypak_browser_router_14](/static/img/product_docs/policypak/policypak/browserrouter/about_policypak_browser_router_14.png)

## Examples

The following table shows different types of pattern rules and how they would match. Note that __Wildcard__ can be used to match against Schema, Host, Port, and Path. __RegEx__ can only be used to match against Host.

| Pattern Rule | Example | Matches |
| --- | --- | --- |
| Specific URL String | www.policypak.com | [www.policypak.com](http://www.policypak.com/) |
| Wildcard String | www.pol\*.com | policypak.com, politicos.com, pollution.org |
| RegEx (Regular Expression) | (.\*)(pol)(.\*).com | SpolE.com, ESpol24.com, pol.com, etc. |
| Windows IE Zone Pattern | Trusted sites, intranet sites, etc. | All trusted sites, intranet sites, etc. |

When a pattern matches, it is routed to the correct browser, blocked, or delivered to a custom browser.

![about_policypak_browser_router_15](/static/img/product_docs/policypak/policypak/browserrouter/about_policypak_browser_router_15.png)

__NOTE:__ For specific URL strings, __Apply to child URLs__ is set to __yes__ by default. This means that any website that falls underneath that URL will also be affected.

You can also select __Block__, which means Endpoint Policy Manager Browser Router won't launch the URL in any supported browser (Internet Explorer, Firefox, or Chrome), blocking it from launching. There is also a special type called __Custom__. This can be set to any application that the administrator wants an end user to open a URL with. One good use for this is that you can specify a custom entry to open virtualized browsers when using App-V or ThinApp, or route to an alternate browser such as Opera, Vivaldi, or anything else that can open HTML pages.

## Wildcard Matching

While __RegEx__ can only be used to match against the host name, Wildcard matching can be utilized to match against other parts of a site identifier/URL. Patterns are not case-sensitive. A site identifier consists of the following:

```
[Schema://]host[:port][/path]
```

where

- __Schema__ must be http, https, \*, or not specified at all.
- __host__ is required and must be either a host name, wildcard host name, or \* for any host.
- __port__ is optional, and if no port is specified, all ports match.
- __path__ is optional, and specified as either a particular path or wildcard path. If a path is not specified, it matches all paths on host.

Examples of wildcard matching are shown below.

Example 1:  Criteria matching only a host name

Criteria: ```*policy*```

Description: Matches any port and path on a URL with a matching host name that contains the word "policy"

Matching examples:

- http://www.policypak.com
- https://www.policypak.com
- http://www.policypak.com:1234/
- http://www.policypak.com:5678/any\_other\_path

Example 2:  Criteria matching all hosts and a wildcard path

Criteria: ```*/app/*Create*```

Description: Matches any host and port with a path containing the word "Create" anywhere in the path. Since host is always mandatory, we MUST specify \* at the beginning for ANY host:

Matching examples:

- http://appsvr/app/Create\_user.aspx
- https://appsvr/app/Create\_item.aspx
- http://appsvr:99/app/Create\_prd.aspx
- http://appsvr/app/Create/newrec.aspx

Example 3: Criteria matching a host, wildcard path, and specific port

Criteria:```aa.com:8080/*app*/```

Description:  Matches the aa.com host (www is implied) on port 8080 with the word "app" anywhere in the path

Matching examples:

- http://www.aa.com:8080/app
- https://www.aa.com:8080/res/app/load.aspx
- http://www.aa.com:8080/lib/resapp.aspx
- http://www.aa.com:8080/ffapp/main.aspx
