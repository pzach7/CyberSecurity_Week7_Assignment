# CyberSecurity_Week7_Assignment
# Project 7 - WordPress Pentesting

Time spent: **4** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [x] GIF Walkthrough: <img src='https://i.imgur.com/IOMh75W.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' />
  - [x] Steps to recreate: Find any comment box and add java script in the comment box, such as <script>alert(document.cookie);</script>, and submit comment. Now whenever someone loads that page, the script is run and an alert pops up. This will continue until the comment is removed.
  - [x] Affected source code:
    - [Link 1] (https://klikki.fi/adv/wordpress2.html)
2. (Required) WordPress <= 4.2.2 - Authenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.1
    - Fixed in version: 4.2.3
  - [x] GIF Walkthrough: <img src='https://i.imgur.com/5LPxxT3.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' />
  - [x] Steps to recreate: When creating a page or post, or editng a page or post (Which requires contributor or author level accounts), switch the body tab from "Visual" to "Text" and raw html code can be injected, such as <a href="[caption code=">]</a><a title=" onmouseover=alert('test')  ">link</a>. When a user hovers over this, a pop-up will appear.
  - [x] Affected source code:
    - [Link 2](https://klikki.fi/adv/wordpress3.html)
3. (Required) WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [x] GIF Walkthrough: <img src='https://i.imgur.com/o28w47Z.gif' title='GIF Walkthrough' width='' alt='GIF Walkthrough' />
  - [x] Steps to recreate: On a page, add an embedded url youtube link. By using the values of escape characters after a seemingly valid youtube url [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed], html code can be injected after the url. Upon loading the page containing the embedded url, the injection is seen
  - [x] Affected source code:
    - [Link 3](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
1. (Optional) Vulnerability Name or ID
  - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

I had some difficulties attempting to recreate the media file upload vulnerability, even though I know it exists in the version I was testing on

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.