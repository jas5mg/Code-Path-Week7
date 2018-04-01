# Project 7 - WordPress Pentesting

Time spent: **7** hours spent in total

> Objective: Find, analyze, recreate, and document affecting an old version of WordPress

## Pentesting Report

1. (Required) Vulnerability Name or ID: Unauthenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: Comments longer that 64 kb, can cuase a trucated database insertion. This insertion can lead to a malformated HTML page generation which can be used to create an XSS attack.
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.1
  - [ ] GIF Walkthrough: ![Alt Text](https://github.com/jas5mg/Code-Path-Week7/blob/master/Vuln_1.gif)
  - [ ] Steps to recreate: As an unauthenticated user, leave a reply with the following comment. <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...'></a> where the AAAAAAAAA is repeated for at least 64kb worth of data. When this reply is viewed by any user, an XSS attack will be triggered. 
  - [ ] Affected source code:
    - [Link 1]()

2. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: As an editor, it is possible to save a draft of a post containing an XSS attack. If another user, such as an admin attempts to preview this draft, the Javascript injected in the post draft will trigger the XSS attack.
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: ![Alt Text](https://github.com/jas5mg/Code-Path-Week7/blob/master/Vuln_2.gif)
  - [ ] Steps to recreate: As an editor, login to WordPress. Create a draft of a post containing an XSS attack such as <img src=1 onerror=alert('XSS')>.  When the admin previews this post, an alert will be triggered when the image fails to load.
  - [ ] Affected source code:
    - [Link 2]()

3. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: Due to issues with how Wordpress sanitizes Embeded YouTube URLs, it is possible to added malicious code to the link. When the page is loaded, the additional Javascript that is added to the Embeded YouTube URL is triggered creating an XSS attack.
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: ![Alt Text](https://github.com/jas5mg/Code-Path-Week7/blob/master/Vuln_3.gif)
  - [ ] Steps to recreate: As an editor, login to WordPress. Create a page that contains the following link: [embed src='https://youtube.com/embed/BLAH\x3csvg onload=alert(6)\x3e'][/embed]. When the page is loaded, the alert will be triggered.
  - [ ] Affected source code:
    - [Link 3]()


## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work
Takes a lot of memory to host all of the VMs. 

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
