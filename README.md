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
    - [Link 1](Reference: https://wpvulndb.com/vulnerabilities/7945)
    - [Link 2](Reference: http://klikki.fi/adv/wordpress2.html)
    - [Link 3](Reference: http://packetstormsecurity.com/files/131644/)
    - [Link 4](Reference: https://www.exploit-db.com/exploits/36844/)
    
    

2. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting (XSS)
  - [ ] Summary: As an editor, it is possible to save a draft of a post containing an XSS attack. If another user, such as an admin attempts to preview this draft, the Javascript injected in the post draft will trigger the XSS attack.
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.3
  - [ ] GIF Walkthrough: ![Alt Text](https://github.com/jas5mg/Code-Path-Week7/blob/master/Vuln_2.gif)
  - [ ] Steps to recreate: As an editor, login to WordPress. Create a draft of a post containing an XSS attack such as <img src=1 onerror=alert('XSS')>.  When the admin previews this post, an alert will be triggered when the image fails to load.
  - [ ] Affected source code:
    - [Link 1](Reference: https://wpvulndb.com/vulnerabilities/8111)
    - [Link 2](Reference: https://wordpress.org/news/2015/07/wordpress-4-2-3/)
    - [Link 3](Reference: https://twitter.com/klikkioy/status/624264122570526720)
    - [Link 4](Reference: https://klikki.fi/adv/wordpress3.html)
    - [Link 5](Reference: https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5622)
    - [Link 6](Reference: https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2015-5623)

3. (Required) Vulnerability Name or ID: Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [ ] Summary: Due to issues with how Wordpress sanitizes Embeded YouTube URLs, it is possible to added malicious code to the link. When the page is loaded, the additional Javascript that is added to the Embeded YouTube URL is triggered creating an XSS attack.
    - Vulnerability types: Cross-Site Scripting (XSS)
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: ![Alt Text](https://github.com/jas5mg/Code-Path-Week7/blob/master/Vuln_3.gif)
  - [ ] Steps to recreate: As an editor, login to WordPress. Create a page that contains the following link: [embed src='https://youtube.com/embed/test\x3csvg onload=alert(6)\x3e'][/embed]. When the page is loaded, the alert will be triggered.
  - [ ] Affected source code:
    - [Link 1](Reference: https://wpvulndb.com/vulnerabilities/8768)
    - [Link 2](Reference: https://wordpress.org/news/2017/03/wordpress-4-7-3-security-and-maintenance-release/)
    - [Link 3](Reference: https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
    - [Link 4](Reference: https://blog.sucuri.net/2017/03/stored-xss-in-wordpress-core.html)
    - [Link 5](Reference: https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-6817)


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
