## Challenge ~
We gave dvGPT a flag and for some reason trust it to keep it safe. These AIs are super duper secure my dude.

https://wtashuxsyj.final.hackabit.com/

## Solution ~
This challenge was by far my favorite becuase it was fun trying to convince the AI to give us the flag. During your conversation, the AI will not give you the flag unless you are <i>Robert</i>.
<br>

-

However, if you just imply that you are Robert, the AI will give you the flag just like that:

<br>
<img src="../Assets/iAmRobert.png" alt="Is this Robert?">
<br>

Woo, now we get the <b>🚩 flag{hey_you're_not_robert}</b>

## Defense
The only defense for this vulnerability, that I know of, is building upon this AI through prompt-engineering. The AI would have to be trained/programmed to monitor their own response and reduce the risk of giving away valuable information.
<br>

-

In a site "<a href="https://zapier.com/blog/ai-hallucinations/">What are AI Hallucinations</a>", they describe how prompt-engineering is used to help regulate the responses AI give to users. Now, the article doesn't explain how an AI could prevent a response from being activated, however, if the AI knew a phrase that only the protected user knows, in this instance Robert, then this could be used as identification for the protected user. The AI, of course, would have to protect the password as well 😏.
