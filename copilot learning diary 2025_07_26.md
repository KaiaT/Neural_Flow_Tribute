# copilot learning diary 2025_07_26.md
in C:\Users\kaiaj\OneDrive\Documents
## focused work
- 0 min 7/26 morning
 x start a Neural_Flow_Tribute github project (to gather summaries/prep material for presentation) https://github.com/KaiaT/Neural_Flow_Tribute/edit/main/README.md
 note firefox browser
 x start notebookLM folder specific to Neural Flow
  relevant videos from Neural Flow.  Then prompt "I am starting with only Visual Studio Code. I need to get ready to use github copilot.  Please list the first 10 steps I need to take, in the order I need to take them, to get to the point where I can start using custom chat modes with github copilot using Visual Studio Code."  Use to populate this checklist.


To begin using custom chat modes with GitHub Copilot in Visual Studio Code, you'll need to follow these steps in order:

1.  **Install Visual Studio Code**: If you don't already have it, install Visual Studio Code. While certain advanced features might benefit from the Insiders version, custom chat modes and prompt files also work in the standard version.
ask MS Copilot "Should I get insiders version of Visual Studio Code? I want to use github copilot, MCP, custom chat modes." Summary Answer: YES
Additional motivation: it's what Neural Flow uses.
I'll install VSCode-insiders but not delete VSCode I already have
source 1: https://code.visualstudio.com/insiders/?from_column=20421&from=20421
source 2: https://apps.microsoft.com/detail/xp8lfczm790f6b?launch=true&mode=full&hl=en-us&gl=us
note 
  PS to check insiders and original are side by side
    Get-Command code | Select-Object Source
    Get-Command code-insiders | Select-Object Source
note configure each version separately
  nothing special is needed. changes in one won’t affect the other unless you manually sync them.
  VS-insiders config file: %APPDATA%\Code - Insiders\User\settings.json



2. I see "use AI features with copilot for free" and am clicking "set up Copilot" button to see if this is a nicely automated shortcut.
  SShot
  This brings me to github where I'm already logged in.
  Always allow... yes.  SShot
  From github: launching Visual Studio Code - Insiders
  voila

these were the original instructions:
2.  **Install the GitHub Copilot Extension**: Open Visual Studio Code, navigate to the Extensions view, and **install the GitHub Copilot extension**.

confirmed my shortcut worked 
  VSCI - opened extensions. yes it was installed already.


3.  **Install the GitHub Copilot Chat Extension**: Similarly, **install the GitHub Copilot Chat extension** from the Extensions view. This is where the chat interface and custom chat modes are primarily accessed.

already done with shortcut from #2




4.  **Enable the "Chat Prompt Files" experimental feature**: This is a crucial step for activating the functionality that supports custom chat modes. Go to Visual Studio Code settings (File > Preferences > Settings or Code > Preferences > Settings on macOS), search for "prompt files," and **enable the `Chat: Prompt Files` setting**. You can enable it for your user or for the entire workspace.

already done


5.  **Open the GitHub Copilot Chat panel**: Once the extensions are installed and the experimental feature is enabled, you can **open the Copilot Chat panel** by pressing `Ctrl+Shift+I` (or `Command+Shift+I` on macOS). This will typically land you in agent mode.

works with no extra steps needed


6.  **Familiarize yourself with the default chat modes**: Before diving into custom modes, it's beneficial to understand the **three default chat modes**: Ask, Agent, and Edit.
    *   **Ask mode** allows you to pose general technical questions about your codebase, best practices, or documentation.
    *   **Edit mode** provides a more controlled experience, letting Copilot edit a specific subset of files to accomplish a single task.
    *   **Agent mode** is the most powerful, allowing Copilot to act as an agent, calling tools, testing output, and iterating to solve problems. Custom chat modes often leverage the capabilities of agent mode.

got it from Neural Flow's videos already

- total today: 60 min	
	
7.  **(Optional but recommended) Add Model Context Protocol (MCP) Servers**: To significantly enhance Copilot's capabilities, you can **add MCP servers** that provide access to additional tools and knowledge bases. For instance, you can add the **Microsoft Learn MCP server** to allow Copilot to search Microsoft documentation. This is done by clicking "add more tools" in the Copilot Chat interface and providing the MCP server URL and ID. Be cautious and trust the source of any MCP server you add, as they run within your environment.

can't see "add more tools"
MS copilot "Please help me with steps on how to add MCP servers in Visual Studio Code Insiders.  Please give me the json code for two MCP servers: 1. github and 2. my local filesystem.  I want MCP configuration to be global, under user settings. I also want to enable MCP autodiscovery."
  followed instructions
  in this process, VSCI AND MS copilot crashed, restarted both
notes
  ctrl shft p
  preferences: open user settings (Json)
  fixed path": "/Users/kaiaj/Documents/mcp-data"
  save file  # I turned autosave off in VSCI
  verify setup:
    command palette
	mcp: show installed servers
	DOESN'T work
	restart VSCI
	
	
- total today: 90 min
	
side project: test the "focus session" feature of MS clock for my next
I set 30 min just now. I also have set a backup end-session alarm on my phone for a total of 1 hour continuous work.
	
after restarted VSCI
  command palette
  mcp: show installed servers
  look lower left SShot
  github is there
  why is my local filesystem not listed?
MS c: "I am using Visual Studio Code Insiders.   I have created a global MCP configuration file. Please help me find that file."
  "%APPDATA%\Code - Insiders\User\mcp.json"
MS c: "I am using Visual Studio Code Insiders.  Why am I not seeing my local filesystem MCP server listed when I run "mcp: show installed servers" on the command palette?  I do see github MCP.  Here is my .json file: ''"


"I want to create new token in github.  The token will be used for my MCP server in Visual Studio Code Insiders.  should I select classic token?
When I select classic, I see many unchecked checkboxes. Which ones should I check, in order to have full MCP functionality from Visual Studio Code Insiders?  Please give me step by step instruction to help me create a token that will work."

got token. 
pasted into VSCI
no errors

- total today: 120 min	

after tested with token
  command palette
  mcp: show installed servers
  look lower left YES I see both now SShot


8.  **Install the "suggest awesome GitHub Copilot chat modes" prompt file**: This prompt file allows you to discover and install community-sourced chat modes directly from within Copilot Chat. To get it, you first need to install this specific prompt file into your **user data folder** (so it's available across all repositories). You can do this by going to `github.com/github/awesomecopilot` and clicking the "install VS Code" or "install VS Code Insiders" button for the "suggest awesome GitHub Copilot chat modes" prompt.

notes
  firefox - https://github.com/github/awesome-copilot
  search
    suggest aw
	suggest awesome GitHub Copilot chat modes
  "install VS Code Insiders" button (left, grey)
  VSCI pop-up do you want this? YES
  I tried supplying dir "C:\Users\kaiaj\Documents\mcp-data" 
  hit enter didn't work
  opened folder C:\Users\kaiaj\Documents\mcp-data
  github "install VS Code Insiders" button (left, grey)
  cool, now it suggests a name and uses that folder that I had open
  I look for the folder, find: "C:\Users\kaiaj\Documents\mcp-data\.github\prompts\suggest-awesome-github-copilot-prompts.prompt.md"


9.  **Use the "suggest awesome GitHub Copilot chat modes" prompt to find and install a custom chat mode**: Once installed, in your Copilot Chat panel, type `/suggest awesome GitHub copilot chat modes` and press Enter. Copilot will then analyze your repository content and recommend relevant chat modes. You can then instruct it to "install the [chat mode name]" (e.g., "install the C#.net janitor"). These found chat modes will typically be installed into your repository's `.github/chatmodes` folder, making them specific to that workspace.

notes 
  type /sug
  autocomplete /suggest awesome GitHub copilot chat modes
  warning about malicious code from the web
  ok. Neural Flow, all my base belong to you.
  I get a list, and am told: Next Steps:
If you want to add any of these prompts, I can automatically download the selected prompt files from the awesome-copilot repository and place them in your prompts directory. Please confirm which prompts you want to add.
  Let's do this
  hmm. I clicked on one, nothing happened. same with second.
  prompt in VSCI: "I want you to automatically download all the prompts listed"
  yeah.
All listed prompts have been downloaded and added to your prompts directory:

code-review.prompt.md
documentation.prompt.md
debugging.prompt.md
test-generation.prompt.md
refactoring.prompt.md
You now have the full set of suggested awesome-copilot prompts available locally. Let me know if you need anything else!

I mean, there are more in awesome-github-copilot-prompts but I was initially offered just a sample.

check upper left VSCI and I see new Dir
SShot
winning!

10a.
I have no code yet in this parallel version of VSCI.  
Before I start a custom chat mode, I want to see if there is another chat in github to produce initial code.
Pulling the URL to the choices from 
Reading through https://github.com/github/awesome-copilot/tree/main/prompts

"how can I preview an .md file I have open in the editor in Visual Studio code?"
ctrl-shft-v NO YOU LIAR
ctrl-shft-p markdown:open preview
that doesn't appear
do I need another plugin?
ms cp: 
I want to search in the visual studio code extensions dialog for every extension containing "markdown" published by Microsoft.  What should I type into my search?
  markdown @publisher:Microsoft
  no hits


ooh I found VS Code Speech and added that.
 AI toolkit
 
MCP servers from MS https://code.visualstudio.com/insider/mcp
  installed: sequential thinking

got off track.
goal: look at an .md file in preview mode.

ms cp: I have opened an .md file in visual studio code insider.  I am looking at the plain text file.  I want to open it in preview mode. Tell me 5 different options on how to do this.
"the keyboard option ctrl-k, v is not a command"
just ctrl-k works. now it is waiting.
capital V fails too

ms cp: in visual studio code Insider, I click ctrl+shift+P, type in "markdown" and there are no matches.  I am expecting to see options that start with "markdown:". Please help me fix this
extension search: @builtin markdown
3 markdowns listed, all enabled.
Restart VSCI
  no change
settings , markdown
  couldn't find any setting that needed changing
extensions, @builtin markdown
  disabled and re-enabled all 3
  
- total today: 180 min	total treadmill-desk:60 min

10b. solve another problem: when I told gh copilot to install some things from https://github.com/github/awesome-copilot?tab=readme-ov-file it didn't actually install them.
I ended up with files in the correct directory.  But the files didn't have the content.  Example from documentation prompt:
'
# Documentation Prompt

Generate project documentation using Copilot prompts.

For more details, see: https://github.com/github/awesome-copilot/blob/main/prompts/documentation.md
'
yes that's it.
So trying to see about installing manually now.
oh wow page not found: https://github.com/github/awesome-copilot/blob/main/prompts/documentation.md
This page is still there: https://github.com/github/awesome-copilot?tab=readme-ov-file
trying a new one https://github.com/github/awesome-copilot/blob/main/chatmodes/software-engineer-agent-v1.chatmode.md
I asked vs code: please install this prompt: https://github.com/github/awesome-copilot/blob/main/chatmodes/software-engineer-agent-v1.chatmode.md
same nonsense
'
# Software Engineer Agent v1 Chatmode Prompt

This prompt configures Copilot to act as a software engineer agent, following best practices for code generation, review, and collaboration.

For more details, see: https://github.com/github/awesome-copilot/blob/main/chatmodes/software-engineer-agent-v1.chatmode.md
'
ask notebookLM: I have installed suggest-awesome-github-copilot-prompts.prompt.md in visual studio code insider.  Now I want to install https://github.com/github/awesome-copilot/blob/main/chatmodes/software-engineer-agent-v1.chatmode.md .  Please tell me each step I need to take to do this.
It should pull instructions from youtube video.

oops:
You have already taken an excellent first step by installing Visual Studio Code Insiders and the suggest-awesome-github-copilot-prompts.prompt.md prompt file. However, to install a chat mode like software-engineer-agent-v1.chatmode.md, you will need to use the suggest awesome GitHub copilot chat modes prompt, as the one you mentioned (suggest-awesome-github-copilot-prompts.prompt.md) is specifically designed to find and suggest prompts, not chat modes.

found chat modes in https://github.com/github/awesome-copilot?tab=readme-ov-file#-custom-chat-modes
the content looks good. Or, full, at least.

yea well I can't get software-engineer-agent-v1.chatmode.md installed from prompt

try the exact prompt notebookLM suggests: install the expert software engineer
same sparse (wrong) File

restart VSCI
no change

ms cp: I want to install https://github.com/github/awesome-copilot/blob/main/chatmodes/software-engineer-agent-v1.chatmode.md into visual studio code insider.  It is failing.  I have a free GitHub account.  Do I have to upgrade my GitHub account in order to use agentic mode?

apparently it should work. but check settings.json for:
{  "copilot.chat.chatModeDiscovery.enabled": true
}
added.

what if I just grabbed the content from github and pasted into the file?
https://github.com/github/awesome-copilot/blob/main/chatmodes/software-engineer-agent-v1.chatmode.md?plain=1

that was easy

how about expert-software-engineer?
https://github.com/github/awesome-copilot/blob/main/chatmodes/expert-software-engineer.chatmode.md
404

I see the v1 chat mode
SShot

I wonder if the install works on only some of the stuff listed in github.
Suggest Awesome GitHub Copilot Chatmodes
uninstalled
went back to GitHub, chose the install button, 
worked perfectly!
So that one can be reliably installed any number of times.
- [ ]  to do: is this pattern seen by anybody else?  Is there a way to fix in GitHub?

restart VSCI
problem: it didn't remember my fixes (delete crap prompt files)
Maybe I need to close VSCI, then delete from c:, then re-open?
- [ ]  to do: test close VSCI, C:\Users\kaiaj\Documents\mcp-data, delete crap, re-open VSCI

ask notebookLM how to get agent to write Code
excerpt: "It's important to note that Copilot agents utilize premium queries from GitHub Copilot and may use GitHub Actions runner minutes. Also, for policy reasons, Copilot (or you, if you initiated the work with Copilot) cannot be the sole reviewer or approver for the PRs it creates"

ask ms cp: I have an unpaid subscription level to github.  do I have to change my subscription to utilize premium queries from GitHub Copilot?

looks like I'm ok so far.

write an interactive kanban board with 4 columns, all within one html file named kanban1.html
I want to be able to drag and drop a task from one column to any other column

these prompts are appearing in the "history" bottom left.
But I have to copy/paste them to a notepad file one by one manually.

extensions
git history @popular

message to Ray Alner:
I learned that i can go to extensions in visual studio codes, and do this search: git history @popular         There's an extension that has 14.5M downloads, so... probably.. trustworthy

did some more iterative development of kanban.html
SShot



10. **Select and begin using your custom chat mode**: After installation, your new custom chat mode will be available. In the Copilot Chat window, you can **select your custom mode from the "Custom" section** (e.g., "AVM bicep" or "mentor"). Once selected, you can interact with Copilot within the context and defined behavior of that specific custom chat mode.

(2 hours on UL chat, with at least an hour of this project, 30 minutes focus after that.)


- total today: 240 min	total treadmill-desk:60 min

can I get the commands I typed into github copilot yesterday through the git history extension that I installed yesterday?
view git history fails when
  typed into terminal
  typed into command pallette (I find it, select it, see nothing changed)
  typed into github copilot (it tells me to use the terminal
  
terminal
`git log --oneline --graph --decorate --all`
`fatal: not a git repository (or any of the parent directories): .git
PS C:\Users\kaiaj\Documents\mcp-data> ``

oops, right. I need to clone my git repo into an appropriate local tree, then cd into it
Anyways I don't want the history of my git commands right now.  I want a summary of all the prompts I typed into github copilot 

ms cp: I am using Visual Studio Code insider with github copilot.  I want to create a text file containing a summary of all the prompts I typed into github copilot.  Please give me all the steps I need to take to do this.

option 3: add logging in MCP server configuration
"local-fs": {
  "type": "filesystem",
  "path": "C:\\Users\\Kaia\\Documents\\copilot-logs",
  "watch": true
}
ahahha "then write a script to append each prompt to a .log or .md file"
thanks ms cp.

wondering. can I have 2 MCP configs for 2 different local file trees?
testing....
manually created copilot-logs\
manually updated  settings.json with code above
ctrl-i
 syntax check
no results
manually save
  autosave is intentionally off
close all files
restart VSCode-insiders

after restart, I listed mcp Servers
github was stopped. started it.  output window had log error: 2025-07-27 07:43:22.194 [error] Failed to set MCP server log level: Error: MPC -32603: session does not support setting logging level
- [ ]  to do: is it important to dig deeper into the error?

actually all 3 were stopped. proceeded to start first MCP file system
2025-07-27 07:47:48.071 [info] Connection state: Error Error sending message to file:///undefined: TypeError: fetch failed

start second:
ahahaha no second fs MCP server. it's a sequential 
thinking server.
2025-07-27 07:47:48.071 [info] Connection state: Error Error sending message to file:///undefined: TypeError: fetch failed
2025-07-27 07:47:48.072 [error] Server exited before responding to `initialize` request.

I remember yesterday seeing a sequentialthinking folder somewhere I didn't expect. I thought it was a duplicate/mistake and deleted it. 

goals
1. get one mcp filesystem working
2. reinstall sequentialthinking
3. read up on a second mcp filesystem. can it work?

1. get one mcp filesystem working
reverted to the windows-exclusive path syntax that ms cp gave me:
    "local-fs": {
      "type": "filesystem",
      "path": "C:\\Users\\Kaiaj\\Documents\\mcp-data",
      "watch": true
    }
copy "C:\\Users\\Kaiaj\\Documents\\mcp-data"
ctrl-c
ctrl-r
ctrl-v
confirm that files shows me that dir exists

save changes
	ctrl-shft-p
	mcp: list Servers
start server 
2025-07-27 07:57:19.639 [info] Starting server local-fs
2025-07-27 07:57:19.643 [info] Connection state: Starting
2025-07-27 07:57:19.645 [info] Starting server from LocalProcess extension host
2025-07-27 07:57:19.645 [info] Connection state: Running

why did github mcp server stop? I didn't stop it.
restarted github MCP

oooh.
I think I'm working in 2 spaces here.
I want my MCP servers to be globally configured (in all workspaces) like Neural Fusion.
I think I have one local? 
	ctrl-shft-p
	mcp: list Servers
	show configuration
	it pulled up .. nevermind, code - insiders > user > {} mcp.json > {} servers > {} local-fs
	that's not another path, it's the syntax for navigating to the file and then the stanza within the File
	SShot

well thar's mah problem:
The "type" for "local-fs" is set to "http", but the "path" field suggests it should be a local file system type (e.g., "fs" or "local"). Using "http" may cause runtime errors if the server expects a different protocol.

Suggested change:

- 			"type": "http",
+ 			"type": "fs",

GitHub Copilot
The path uses Windows-style backslashes (\). For cross-platform compatibility, consider using forward slashes (/) or normalizing the path at runtime.

Suggested change:

- 			"path": "C:\\Users\\Kaiaj\\Documents\\mcp-data\\local-fs",
+ 			"path": "C:/Users/Kaiaj/Documents/mcp-data/local-fs",

and here is sequentialthinking:
		"sequentialthinking": {
			"type": "stdio",
			"command": "npx",
			"args": [
				"-y",
				"@modelcontextprotocol/server-sequential-thinking@latest"
			],
			"gallery": true
		}
error pop-up: could not find the command npx
log says:
2025-07-27 07:55:12.550 [info] Starting server from LocalProcess extension host
2025-07-27 07:55:12.571 [info] Connection state: Starting
2025-07-27 07:55:12.577 [info] Connection state: Error spawn npx ENOENT
probably I deleted It
I'll just comment those lines for now.

handy commands: 
please adjust white space for consistency
please fix file
syntax checks

here's what still bothers me. mcp is defined in two files: mcp.json and also settings.json.
Just now I've been working on mcp.json

gh cp: reset chat
gh cp: I am using Visual Studio Code insider with github copilot.  Looking at my filesystem, I see that mcp is defined in two files: mcp.json and also settings.json.  Please explain if this is a problem.

it told me it wasn't a problem but I think the scope is different

gh cp: is the scope of each of these open files different? For example is one for the workspace only and one global?

Yes, the scope is different:

settings.json in vscode-userdata is global—it applies to all VS Code workspaces for your user profile.
mcp.json in your project folder is workspace-specific—it only affects the current workspace/project.
Global settings affect all projects unless overridden by workspace settings. Workspace settings only affect the current project. This separation helps you manage project-specific vs. user-wide configuration.

gh cp: please help me move all my configuration to settings.json

There is no mcp.json file in your workspace, so all your configuration should be moved or managed in settings.json. If you have any specific configuration you want to add, let me know and I can help you format and insert it into your global settings.

huh. I've got it mcp.json open in the editor. But it's not in my mcp-data tree.  should I make the top of the tree "code - insiders" ?

emptied mcp.json
saved the empty file
restart VSCode-insiders
wow!
MCP: list servers has no servers!  prompts me to add a server!

gh cp: it looks like settings.json was not been loaded when VSCode started.  I have it open in the editor.  Please tell me how to fix this.

path C:/Users/<YourUser>/AppData/Roaming/Code/User/settings.json

"/Code/" ? I'm "/Code - Insiders/" 
Double checked: yes I am running Code - Insiders and not my other installation of classic code.
I think that's correct.

SShot of choices - user or workspace. Assuming user is a wider scope covering all my workspaces.

Open Command Palette (Ctrl+Shift+P), type "Preferences: Open Settings (JSON)" to confirm you are editing the correct file.
3 choices. none was "Preferences: Open Settings (JSON)"
SShot
I chose user settings.

yes the same file opens

- today's total: 67 minutes  treadmill: 67 minutes

note minute 6:00 in https://www.youtube.com/watch?v=klKXZsB7FSw
  janitor chat mode is installed in workspace
  (it is applicable specifically to that workspace, so that is where we want it)
- [ ]  to do: sort out config files/workspaces later.
  
using the fast way now.  I don't understand the problem but know how I can move ahead.
re-installed mcp Servers from https://code.visualstudio.com/insider/mcp
  github
  filesystem
    "path": "C:\\Users\\Kaia\\Documents\\mcp-data",
	there is no user kaia, it should be kaiaj
  etc. I was picking up stuff like a door crasher on black Friday
  sequentialthinking required additional installation of npx, https://nodejs.org/en/download, which also needs chocolatey. Chose yes to all the dependencies.  an additional win installer pops up and needs reassurance, too, before it's all installed. 3GB disk.  This script can be found in the Start menu under Node.js.
Detailed instructions to install these
tools manually are available at https://github.com/nodejs/node-gyp#on-windows
 
research then install OBS to create a walk-through video
  https://obsproject.com/welcome
  optimize for recording (planning no streaming)

research then install ghostwriter markdown editor
  https://ghostwriter.kde.org/
  extract to C:\Program Files\Ghostwriter
  pin to start: ghostwriter.exe 
  quick video tutorial https://www.youtube.com/watch?v=O_yIPQOPQxA
  

- [ ] to do: share the notebookLM folder. Add link on github.
re-subscribe to Github copilot - what level?

AIprompt	What speech to text tool can I use to dictate directly into insiders version of Visual Studio Code?  What tool does the youtube channel "neural flow" use in https://www.youtube.com/watch?v=32N9GvIndg8&t=1297s? 
  x summary from ms Copilot: VS Code Speech Extension or OpenAI’s Whisper model (likely run Whisper locally or via a Python script)



- way future
- [ ]  to do: github - read up on license options. I chose GNU. Is that what I meant?

===== take it easy
markdown
  (any AI) topic: markdown review + quiz
   blueprint for personal tutor video Nate Jones https://www.youtube.com/watch?v=2uC5WllehxY
   convert notepad++ docs to .md where content matches
youtube list from firefox search for 20250726

browse through docs https://code.visualstudio.com/docs/?dv=win64user&build=insiders

VSCode plugins
research vs code plugin "markdown preview mermaid support" safe to add? matt bierner 3M downloads
  container @publisher:Microsoft
  read up on already installed: https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-speech
  
MCP servers from MS https://code.visualstudio.com/insider/mcp
  installed: sequential thinking

- [ ]  to do: review MCP servers best-of from email: EP173