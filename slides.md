---
theme: apple-basic
layout: intro
highlighter: shiki
fonts:
  sans: Montserrat
---

<div class="flex gap-10">
<img src="/media/logo.png" class="h-17"/>
<h1>Jarvis</h1>
</div>
Your human-level AI assistant

<div class="absolute bottom-10">
  <span class="font-700">
    Alex Ramalho
  </span>
</div>

<!--
GOAL:
- Make an AI agent actually usable for common day to day problems
-->

---
layout: center
---

## Problem 1 – Ideas 💡

<v-click>
<br>

> <em> An idea is like a a cloud. If you look a moment later, it could be quite a bit different. And if you look at it an hour later, it may very well be gone.</em>

–Andrew Huberman on his Podcast (with Rick Rubin, author of The Creative Act)

</v-click>

---

## Problem 2 – Papers 📝

<Papers />
---


## Solution Overview

<img src="/media/agent.png" class="absolute left-50 h-120"/>

---

## Solution 1

<div class="flex gap-5">
<v-click>
<img src="/media/prints/ideas-setup.jpg" style="height: 300px; border-radius: 16px"/>
  </v-click>
<div class="flex flex-col gap-10 relative">
    <img v-click src="/media/prints/ideas-before.png" class="rounded-lg border border-gray-300" />
  <img v-click src="/media/prints/ideas-after.png" class="absolute rounded-lg border border-gray-300" />
</div>
</div>

---

## Solution 2

<div class="flex gap-5">
<v-click>
<img src="/media/prints/reads.jpg" style="height: 300px; border-radius: 16px"/>
  </v-click>
<div class="flex flex-col gap-10 relative">
    <img v-click src="/media/prints/reads-before.png" class="h-100 rounded-lg border border-gray-300" />
  <img v-click src="/media/prints/reads-after.png" class="absolute h-100 rounded-lg border border-gray-300" />
</div>
</div>


---

## Modular

```python {all|4-11|2}
class FullAgent(Agent):
    def __init__(self, medium: CommunicationMedium, memory: Memory, user: User, **kwds):
        self.tools = [
            SearchInternetTool(medium=medium, user=user),
            InvestigateLinkTool(medium=medium),
            InvestigateUserUploadedFileTool(user_id=user.id, medium=medium),
            ManageUserNotesTool(user_id=user.id, medium=medium),
            ManageUserRemindersTool(user_id=user.id, medium=medium),
            ManageUserScheduledTasksTool(user=user, medium=medium),
            StoreUserFeedbackTool(user=user, medium=medium),
            UpdateUserPreferencesTool(user_id=user.id, medium=medium),
        ]
        super(FullAgent, self).__init__(
            medium=medium,
            memory=memory,
            user=user,
            **kwds,
        )
```

---

```python {1-10|10-20}
class CommunicationMedium(ABC):

    @abstractmethod
    def input(self, message: str):
        pass    
    
    @abstractmethod
    def output(self, message: str):
        pass


class Memory(ABC):
    def write(self, message: Message):
        pass

    def read_all(self, max_words: int = None) -> List[Message]:
        pass
```

---

# An interesting Challenge

- Everything as text

```python{none|1-5|6-15}

URL_DISPATCHER = {
    r"github\.com/[^/]+/[^/]+/issues/\d+": GitHubIssuesHandler,
    r"youtube\.com/watch\?v=": YouTubeTranscriptHandler,
    # ... add other regex pattern-to-handler mappings here
}

class GitHubIssuesHandler(BaseURLHandler):
    def process(self, soup: BeautifulSoup) -> BeautifulSoup:
        classes = ["js-issue-title", "gh-header-meta", "js-discussion"]
        soups = [str(soup.find(class_=c)) for c in classes]
        combined_soup = BeautifulSoup("".join(soups), "html.parser")
        return combined_soup

```


---

# Thank you

<div class="flex gap-10 justify-around text-center">
  <div class="flex flex-col gap-10 m-auto">
    <img src="/media/qr-me.png" style="height: 200px"/>
    <h4>Get in contact</h4>
  </div>
  <div class="flex flex-col gap-1 m-auto">
    <img src="/media/qr-j.png" style="height: 300px"/>
    <h4>👆 Project Page </h4>
    <p><u>https://heyjarvis.co</u></p>
  </div>
</div>
