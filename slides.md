# Open Kedro Retro #1
### June 2021



<div grid="~ cols-2 gap-4">
<div class="pt-12">
<p>
  <span @click="$slidev.nav.next" class="px-2 p-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press <kbd>space</kbd> for next page <carbon:arrow-right class="inline"/>
  </span>
  </p>
</div>
<div class="w-90 h-150"><KedroIcon /></div>
</div>

---
theme: apple-basic
class: text-left
highlighter: shiki
layout: iframe-right
url: https://quantumblacklabs.github.io/kedro-viz
---

# Today's agenda

We’re excited to show you some of the cool stuff we’re currently cooking up and our vision for the future and Kedro's place within the ML ecosystem.

- 🤔 What actually is Kedro?
- 🤖 Meet the team
- 👩‍🍳 What the team have been cooking
- 🗑 No context Kedro 
- 💅 Kedro Viz: Not just a pretty face
- 🔮 A look to the future 
- 👋 Community improvements 
- 📣 Q&A

<Socials />

---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/
---
<Overview />
<Socials />
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/02_get_started/06_starters.html
---
<Overview />
<Pointer class="absolute bottom-63"/>
<Speaker name="Joel"/>
---
layout: iframe-right
url: >-
  https://kedro.readthedocs.io/en/stable/05_data/01_data_catalog.html#using-the-data-catalog-with-the-yaml-api
---
<Overview />
<Speaker name="Joel"/>
<Pointer class="absolute bottom-55"/>
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/06_nodes_and_pipelines/01_nodes.html#nodes
---
<Overview />
<Speaker name="Joel"/>
<Pointer class="absolute bottom-47"/>
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/06_nodes_and_pipelines/02_pipeline_introduction.html#pipelines
---
<Overview />
<Speaker name="Joel"/>
<Pointer class="absolute bottom-40"/>
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/09_development/03_commands_reference.html
---
<Overview />
<Speaker name="Joel"/>
<Pointer class="absolute bottom-32"/>
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/10_deployment/01_deployment_guide.html#deployment-guide
---
<Overview />
<Speaker name="Joel"/>
<Pointer class="absolute bottom-24"/>
---
layout: iframe-right
url: https://quantumblacklabs.github.io/kedro-viz
---
<Overview />
<Pointer class="absolute bottom-16"/>
---

# Meet the team

### Framework team

<div class="grid grid-cols-8 p-2">
  <div><Profile name="Ivan" role="Tech lead" github="idanov"/></div>
  <div><Profile name="Lorena" role="SWE" github="lorenabalan"/></div>
  <div><Profile name="Merel" role="SWE" github="MerelTheisenQB"/></div>
  <div><Profile name="Antony" role="SWE" github="AntonyMilneQB"/></div>
  <div><Profile name="Ignacio" role="SWE" github="ignacioparicio"/></div>
  <div><Profile name="Jiri" role="SWE" github="jiriklein"/></div>
</div>

<div class="flex">

<div class="flex-auto">
  <h3>Viz team</h3>

  <div class="grid grid-cols-4 gap-1 p-2">
    <div><Profile name="Lim" role="Viz tech lead" github="limdauto"/></div>
    <div><Profile name="Liam" role="Front end" github="bru5"/></div>
    <div><Profile name="Susanna" role="Front end" github="studioswong"/></div>
    <div><Profile name="Rashida" role="Front end" github="rashidakanchwala"/></div> 
  </div>
</div>
<div class="flex-auto">
<h3>Product</h3>
<div class="grid grid-cols-4 gap-1 p-2">
<div><Profile name="Yetu" role="Product Lead" github="yetudada"/></div>
<div><Profile name="Joel" role="Product" github="datajoely"/></div>
<div><Profile name="Jo" role="Tech Writer" github="stichbury"/></div>
<div><Profile name="Gabriel" role="Designer" github="GabrielComymQB"/></div>
</div>
</div>
</div>
<Socials />

---

## What have been cooking recently 👩‍🍳?

 <Speaker name="Joel"/>

<h3> Recently, we have rewritten how Kedro works behind the scenes <ic-baseline-auto-fix-high class="inline"/><br>Since December 2020 🎄 we have released versions <kbd>0.17.0</kbd>, <kbd>0.17.1</kbd>, <kbd>0.17.2</kbd> and <kbd>0.17.3</kbd></h3>


<div v-click>

<p class="text-m"> Breaking changes</p>

- 📼 `KedroSession` is the new way we manage the lifecycle of a run.
- 🐍 `settings.py` and `pyproject.toml`  replace `.kedro.yml` for project configuration
- 📌 `__main__.py` is the new project entry-point
</div>

<div v-click>

<p class="text-m"> Other highlights</p>

- 🧘‍♂️ Lazy loading of registered `Pipeline` objects
- 🆕 `Jinja2` templating added to `TemplatedconfigLoader`
- 🏃‍♀️ Complete rewrite of the `Kedro Viz` back-end using `FastAPI`
- 🎁 Improved packaging
- 🙌 Custom starters, new hooks, customisable CLI, bug fixes 🐛 and more...
</div>

<Socials />
---

# No context Kedro ?

<Speaker name="Lorena"/>

<v-clicks>

- <carbon-clean class="inline text-yellow-500"/> In the beginning there was no context
- <carbon-crop class="inline text-yellow-500"/> Then the `KedroContext` helped us simplify Kedro
- <carbon-maximize class="inline text-yellow-500"/> Over time it has become too big and too bloated (esp. <kbd>IPython</kbd> / <vscode-icons-file-type-jupyter class="inline"/> sessions)
- 😭 It's now time to start divorce proceedings and move to a new approach...

</v-clicks>

<div class="grid grid-cols-3 p-1">
<div v-click class="border border-dark-400 rounded-lg py-2 content-between m-3">
<p class="text-center font-mono">KedroSession <carbon-logo-python class="inline" /></p>

<div class="text-sm">

- Introducing a <feather-database class="inline text-yellow-500"/>  store
- Deprecates the Journal <carbon-trash-can class="inline text-yellow-500"/>
- Time-travel superpowers <noto-superhero-medium-dark-skin-tone class="inline"/> 

</div>

</div>

<div v-click class="border border-dark-400 rounded-lg py-2 content-between m-3">
<p class="text-center font-mono">settings.py <file-icons-config-python class="inline" /></p>

<div class="text-sm">

- The recipe for a run <mdi-chef-hat class="inline text-yellow-500"/>
- <el-home-alt class="inline text-yellow-500"/> for `hooks` and `/conf/` loc
- <ri-caravan-fill class="inline text-yellow-500"/> `DataCatalog` is moving too...

</div>

</div>
<div v-click class="border border-dark-400 rounded-lg py-2 content-between m-3">
<p class="text-center font-mono">pyproject.toml <grommet-icons-document-config class="inline" /></p>

<div class="text-sm">

- <carbon-logo-python class="inline text-yellow-500"/> winds are changing...
- Kedro directory detection <carbon-terminal class="inline text-yellow-500"/>
- <el-home-alt class="inline text-yellow-500"/> for packaging spec in the future
</div>


</div>
</div>

<v-clicks after="5">

<div>

```ini
kedro.framework.session.store - INFO - 'read()' not implemented for 'BaseSessionStore'. Assuming empty store
```
<p class="text-sm"><span class="animate-pulse">☝️</span> This annoying message will soon dissapear!</p>

</div>

</v-clicks>

<Socials />

---

# 💅 Kedro Viz: Not just a pretty face
<Speaker name="Susanna"/>

<div grid="~ cols-3">
    <div class="p-3 text-purple-400">
        <mdi-pipe class="text-4em m-auto align-text" />
    </div>
    <div class="p-3 text-primary m-auto">
        <simple-icons-fastapi class="text-4em m-auto" />
    </div>
    <div class="p-3 text-blue-500">
        <simple-icons-plotly class="text-4em m-auto" />
    </div>
</div>

<div grid="~ cols-3">
    <div class="text-purple-400">
        <p class="text-l m-auto text-center">
            Modular pipelines become <br />
            1<sup>st</sup> class citizens
        </p>
    </div>
    <div class="text-primary m-auto">
        <p class="text-l m-auto text-center">
            FastAPI rewrite <br />
            of backend
        </p>
    </div>
    <div class="text-blue-500">
        <p class="text-l m-auto text-center">
            Native Plotly integration <br />
            within the DAG
        </p>
    </div>
</div>

<div grid="~ cols-3">
    <div class="relative max-w-60 overflow-hidden rounded-lg text-center m-auto ring ring-purple-400 ring-offset-5 ring-offset-dark-900">
        <img class="object-cover w-full h-50 m-auto" src="/modular.png" />
    </div>
    <div class="relative max-w-60 overflow-hidden rounded-lg text-center m-auto ring ring-primary ring-offset-5 ring-offset-dark-900">
        <img class="object-cover w-80 h-50 m-auto" src="/fastapi.png" />
    </div>
    <div class="relative max-w-60 overflow-hidden rounded-lg text-center m-auto ring ring-blue-500 ring-offset-5 ring-offset-dark-900">
        <img class="object-cover w-full h-50 m-auto" src="/plotly.gif" />
    </div>
</div>


<Socials />

---
layout: quote
---
# 🔮 A look to the future 

- Experiment tracking
- Packaging improvements
- Configuration overhaul
- Diffing with Dolt

<Speaker name="Joel"/>
<Socials />

---
<h1>🧪 Experiment tracking is coming to Kedro!</h1>

<div v-click>
<h3 class='p-2 m-3 opacity-100'><span class="p-1 bg-dark-500 rounded text-green-600 mr-2"><carbon-checkmark-filled class="inline text-green-600 mr-1"/>IN PROGRESS</span>User research phase</h3>

<div grid="~ cols-3 gap-4">
<div class="relative max-w-60 overflow-hidden rounded-lg shadow-lg">
  <img class="object-cover w-full h-22" src="/exp_a.png"/>
  <div class="absolute top-0 left-0 px-6 py-4">
  </div>
</div>

<div class="relative max-w-60 overflow-hidden rounded-lg shadow-lg">
  <img class="object-cover w-full h-22" src="/exp_b.png"/>
  <div class="absolute top-0 left-0 px-6 py-4">
  </div>
</div>

<div class="relative max-w-60 overflow-hidden rounded-lg shadow-lg">
  <img class="object-cover w-full h-22" src="/exp_c.png"/>
  <div class="absolute top-0 left-0 px- py-4">
  </div>
</div>
</div>

</div>

<div v-click>
<h3 class='p-2 m-3 opacity-100 animate-pulse'><span class="p-1 bg-dark-500 rounded text-yellow-500 mr-2"> <carbon-progress-bar-round class="inline text-yellow-500"/> IN PROGRESS</span>Design Phase</h3>

<div grid="~ cols-3 gap-4">
<div class="relative max-w-60 overflow-hidden rounded-lg shadow-lg">
  <img class="object-cover w-full h-22" src="/exp_d.png"/>
  <div class="absolute top-0 left-0 px-6 py-4">
  </div>
</div>

<div class="relative max-w-60 overflow-hidden rounded-lg shadow-lg">
  <img class="object-cover w-full h-22" src="/exp_e.png"/>
  <div class="absolute top-0 left-0 px-6 py-4">
  </div>
</div>

<div class="relative max-w-60 overflow-hidden rounded-lg shadow-lg">
  <img class="object-cover w-full h-22" src="/exp_f.png"/>
  <div class="absolute top-0 left-0 px-6 py-4">
  </div>
</div>

</div>
</div>

<div v-click>
<h3 class='p-2 m-3 opacity-100'><span class="p-1 bg-dark-500 rounded mr-2"><carbon-calendar class="inline"/>PENDING</span>Implementation Phase</h3>

<ul>
<li>Focus will be on <span class="text-yellow-500">the journey to production</span> <b>NOT</b> live model monitoring</li>
<li class="object-contain">Will integrate with <img src="/mlflow.png" class="object-contain h-10 inline border rounded m-2 p-2"/> model-registry</li>
</ul>
</div>
<Socials />
<Speaker name="Merel"/>

---

# Modular pipeline packaging

<v-click>

Our first iteration of our 'modular pipelines' feature (version 0.16.2). 

- Users can <kbd>package</kbd>, <kbd>share</kbd>, <kbd>reuse</kbd> and <kbd>consume</kbd> pipelines as discrete units across teams. 
- We now have a year's worth of user feedback on where to take this next
- Ever-growing central `requirements.txt` is a common pain point

</v-click>

<v-click>
<p class="text-gray-500">Inner-sourced knowledge</p>


<p class="text-s">We want it to becomes common practice to re-use entire pipelines across different use cases.</p>
<div grid="~ cols-3 ">
  <div class="flex flex-col border rounded m-1  border-dark-400">
    <div class="m-auto">
      <KedroIcon class="h-max vertical-center rounded-full bg-dark-500 m-3"/>
    </div>
  </div>
  <div class="flex flex-col border rounded m-1 border-dark-400">
    <div class="m-auto text-center">
      <Arrow x1=600 y1=470 x2=380 y2=470 class="text-yellow-500 text-xl animate-pulse"/>
      <p>Push pipelines</p>
      <p>Pull source code</p>
      <Arrow x1=380 y1=360 x2=600 y2=360 class="text-yellow-500 text-xl animate-pulse"/>
    </div>
  </div>
  <div class="flex flex-col border rounded m-1 border-dark-400">
    <div class="m-auto mt-2">    
      <span>
        <simple-icons-jfrog class="m-2 h-6 w-6 text-primary inline"/>
        <p class="inline text-xs">JFrog Artifactory</p>
      </span>
      <br>
      <span>
        <file-icons-pypi class="m-2  h-6 w-6 text-indigo-400 inline"/>
        <p class="inline text-xs">PyPI</p>
      </span>
      <br>
      <span>
        <mdi-azure-devops class="m-2  h-6 w-6 text-blue-500 inline"/>
        <p class="inline text-xs">Azure Artifacts</p>
      </span>
      <p class="text-xs text-gray-300 text-center">Any PyPI like endpoint</p>
    </div>
  </div>
</div>
</v-click>

<Speaker name="Ivan"/>
<Socials />


---

# Community improvements

<Speaker name="Yetu"/>


<div grid="~ cols-2 gap-4">
    <div>
        <div v-click class="mb-12">
        <div grid="~ cols-2">
        <div><p class="text-gray-500 text-sm">
            Slide into our DMs on 
        <p class="inline bg-indigo-400 text-black p-1 rounded font-mono text-xs">
            Discord 
            <carbon-logo-discord class="inline" />
        </p>
        </p>
        <p>
            Open forum to chat 
            <carbon-chat-bot class="inline" />
            with the dev team
            and for the community to assist support each other
            <carbon-help class="inline" />
        </p></div>
        <div class="ml-9"><img src="/discord_qr.svg" class="h-35 m-3 rounded"/></div>
        </div>
        <iframe
            src="https://discord.com/widget?id=778216384475693066&theme=dark"
            allowtransparency="true"
            width="400" height="220"
            sandbox="allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts"
            ></iframe>
        </div>
    </div>
    <v-clicks at=1 >
        <div class="object-centre">
        <div v-click class="">
            <p class="text-sm text-gray-500">
            <p class="inline bg-gray-300 text-black p-1 rounded font-mono text-xs">
                GitHub Discussions
                <carbon-logo-github class="inline m-1" />
            </p>
            will help codify knowledge 🙌
            </p>
            <p>
                Threaded conversations 
                <twemoji-thread class="inline" />
                , answers marked by
                the maintainer 
                <carbon-checkmark-filled  class="inline text-primary" />
                and pinned
                announcements 
                <carbon-pin-filled class="inline text-pink-500" />
            </p>
            <table class="tg">
                <thead>
                    <tr>
                    <td class="tg-0pky">🙌</td>
                    <td class="tg-0pky"><span style="font-style:normal">Show and tell</span></td>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                    <td class="tg-0lax">💡</td>
                    <td class="tg-0lax">Ideas</td>
                    </tr>
                    <tr>
                    <td class="tg-0lax">🙏</td>
                    <td class="tg-0lax">Q&amp;A</td>
                    </tr>
                    <tr>
                    <td class="tg-0lax">🆘</td>
                    <td class="tg-0lax">Help</td>
                    </tr>
                </tbody>
            </table>
        </div>
        <div v-click class="mt-10">
            <p class="text-sm text-red-400">
                Deprecation 😭 of 
            <p class="inline bg-red-400 text-black m-1 p-1 rounded font-mono text-xs">
                discourse.kedro.community 
                <fa-brands-discourse class="inline" />
            </p>
            </p>
            <p>
                We hope that the two avenues above will be better to this, StackOverflow
                <fa-brands-stack-overflow class="inline" />
                and other platforms
            </p>
        </div>
        </div>
    </v-clicks>
</div>


<Socials />

---
layout: quote
---
# 📣 Open Q&A Session



<Socials />
