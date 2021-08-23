# Contents:

* [Markdown Primer](https://pa-partner-wiki.ml/Intro%20to%20working%20with%20md%20and%20how%20to%20contribute.md#purpose)
* [Community Guidelines](https://pa-partner-wiki.ml/Intro%20to%20working%20with%20md%20and%20how%20to%20contribute.md#here-s-the-community-guidelines)
* [Security Considerations](https://pa-partner-wiki.ml/Intro%20to%20working%20with%20md%20and%20how%20to%20contribute.md#security-considerations)


## Purpose:

To provide a quick tutorial on how-to-use markdown so an engineer feels confident contributing to tutorials, labs, and other information on this site. 

## What is Markdown?

Markdown is a lightweight markup language for creating formatted text using a plain-text editor. - [Wikipedia](https://en.wikipedia.org/wiki/Markdown)

## Okay, so why is it useful? 

It's useful because it gives an individual the ability create technical documentation which is easy-to-read and easy-to-write. A major advantage of using markdown is it can easily be converted to html for web-based viewing.  

**An example of why markdown is great:**

1. Open up your word processor of choice. (word, google sheets, libra office...etc.)
2. Type in some fake code. 
3. Now try to make it look like this: `Here is my sudo code`. 

How long did that take? 

In markdown it takes about the same amount of time as it takes to type: Here is my sudo code. 

## Wait what, how did you do that?

Simple! Code blocks can be created inline on the fly with markdown. You simply add a ` in front of your code and another backtick at the end. 

**Example:**

Let's say you wanted to instruct someone to type: `echo "hello-world"`

In markdown you'd type: \`echo "hello-world"\`

For larger blocks of code you use three ``` backticks on the line you want the code block to begin on, and then another three backticks on the line you want the code to end. 

For more reference check out this [markdown cheat sheet](https://www.markdownguide.org/cheat-sheet/)

## Okay cool, so where do I practice my md skills?

Here would be a good place! If you notice you can always click edit on every page that I created. In fact, you are welcome to hit the button at the top of the `home` page and select the green `new` button to create a new page! That will take you to a GUI editor with shortcuts built-in to convert text you type to markdown. [Try it out](https://pa-partner-wiki.ml/Home#)! 

_NOTE: If your practicing just ensure you hit cancel when you're done. Use the `Edit` and `Preview Tab` to get practice._

Other places are sites like github! Realize this process is what makes github so valuable. You don't need to be a developer to contribute. 

## Are there any rules or guidelines I need to follow? 

Yes, the goal of this page is to serve the larger community. One of the challenges with a platform like Prisma Cloud is sheer scope of the technology ecosystem it encompasses. I can't tell you how many new tools, concepts, and technologies I've learned since coming here. It can be daunting for someone who is just stepping into the cloud to even know where to begin. I made this page to create a community of experts around different parts of the ecosystem and am asking for your assistance adding your knowledge to the pool. 

## Here's the community guidelines:

1. **Keep security in mind.** This **does not** mean you should only contribute if you're able to write a tutorial which follows every security guideline or hardening standard in the world. But it does mean that if you're not sure, that you should indicate so in your tutorial. A simple rule I follow is to write: _not for production_ so that someone else reading it doesn't create unecessary vulnerabilities in a production environment. You should make best efforts to outline security measures someone should keep in mind when following your tutorial. Lint your code whenever possible. If you're unsure on how to go about doing that, let me know and I'll add a linting tutorial. Lastly, please ensure that you are not posting any information that would be considered internal or sensitive. The world needs more passionate security professionals, not less.  

2. **Share, edit, and contribute.** Maybe you don't have a lot of development knowledge but you're great at proof-reading or spelling. Cool, if you notice a grammatical error or spelling mistake. Edit the page and fix it! That's incredibly helpful to the broader community. Other ideas are adding links to the home page to useful documentation you've come accross pertaining to prisma cloud, cloud security, GRC documentation, or dev tools/technologies. The whole point is paying it forward. It's impossible for any one single person to know everything, and if you felt like this page provided something that was useful to you, then please support your community by adding your specialized knowelege to the pool. 

3. **Be as detailed as possible.** Assume that the person you're writing the documentation for is not a developer. Assume they're not a hardware specialist. Assume they don't understand the security concepts you know. We've all experienced reading documentation that assumes a lot of knowledge and exprienced the hours of frustrations it can create. Try your best to list out any requirements and assumptions you're making when writing a tutorial. List the OS, hardware, and other tools. Provide links to reference documentation. Start your documentation with a brief explaination of why you're creating it to begin with. 

4. **Be kind.** We're in a field where every one of us is constantly learning. We're all at various stages in our learning and development. We can all relate to learning a new technical concept. When people are learning it's important to be supportive and inspire confidence. It was a design decision to ensure that your information or others information is not recorded by default when you're creating documentation. Of course, if you'd like to add your name to it, please do. My hope is to ensure you feel safe contributing without being judged; while also providing an opportunity for you to showcase what you know. 

## But why would I contribute, knowing that my competition might be benefiting from any documentation/knowledge I share?

This is a hilarious mentality to me. Hilarious because if you're thinking this way you're misunderstanding the larger problem. The problem is that technology is acclerating at an exponential rate; faster than any one of us can handle. The problem is that state level actors know this weakness and are breaking into organizations infrastructure using advanced multi-step techniques which are designed to thrive in a complex environment. We need to figure out a way to enable and teach the broader community the skills we've aquired over the years if we have any hope of actually addressing this broader problem. In my opinion, this challenge is too big for any one person, organization, or product. We all benefit by sharing our technical knowledge and increase the chances of deals getting done and products getting sold and infrastructure being secured. In essesance, there's plenty of pie to go around. 

Keep in mind this statistic:

There's currently a shortage of about 3.5 million Cybersecurity jobs: [ref](https://www.pwc.com/gx/en/issues/cybersecurity/digital-trust-insights/cyber-talent-workforce.html)

What that means is, there is currently more demand in the marketplace than there is supply. We need to figure out how to do more with less. This is my attempt at addressing this broader challenge. My goal with this site is create an environment that inspires your assistence in addressing this challenge as well. Thank you!


## Security Considerations

Alright, so let me explain a few things to those who may be concerned about security as it relates to this site. 

First, let me address the basic authentication requirements to access this page. There is nothing on this site which links to anything internal to Palo Alto Networks. If there ever was a link to something internal, it wouldn't be accessible due to multiple layers of security PANW's IT has implemented. I put a layer of basic authentication in to ensure that the general population doesn't access this site.

Realize everyone who signs into this site is given "admin" privilages; meaning they can edit content and create content as they see fit. What they cannot edit is the history of changes or the automatic versioning of documentation. My goal here is to eliminate all barriers that might prevent an individual from wanting to contribute. 

Other security measures I've implemented:

* The site is being served using containers through a reverse proxy. The containers themselves aren't volume mounted to anything close to root. Notice that you cannot access this site over http. 

* There's a strict NSG policy associated with the VM which only allows traffic in and out of port 80 and 443. 

* In addition as you can tell from the qualys report below this is being hosted from a single vm in AWS.  

Now is there a possibility some malicious engineer could put a link to something that's malicious? The answer is yes. To mitigate any risk realize you can hover over any link before clicking and be able to see where you're going to be redirected; in addition, you are welcome to copy the home page or any page contained on this site anytime you'd like simply by hitting the edit button and copying out the code. When you hit the edit button the raw urls are shown so you may inspect them anytime you'd like. 
Thanks to a different partner engineer I had an interaction with or maybe due to...I'm aware that akamai has flagged this site for possible phishing. I've contacted them directly to fix the issue; but because I'm not a customer my ability to get this changed is somewhat limited. 

Here's a link to a qualys report for this site: https://www.ssllabs.com/ssltest/analyze.html?d=pa-partner-wiki.ml

At some point I'll write out a tutorial on how to deploy this site so that others may benefit from this model. If you have security recommendations please feel free to reach out to me directly and I'll address them accordingly! Thank you for your time. 

Kyle Butler
kbutler@paloaltonetworks.com







