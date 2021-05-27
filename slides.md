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
<div class="w-90 h-150"><Icon /></div>
</div>

---
theme: apple-basic
class: text-left
highlighter: shiki
layout: iframe-right
url: https://quantumblacklabs.github.io/kedro-viz
---

# Today's agenda

<Speaker name="Joel"/>

We’re excited to show you some of the cool stuff we’re currently cooking up and our vision for the future and Kedro's place within the ML ecosystem.

- 🤔 What actually is Kedro?
- 🤖 Meet the team
- 👩‍🍳 What the team have been cooking
- 🗑 No context Kedro 
- 💅 Kedro Viz: Not just a pretty face
- 🔮 A look to the future 

<div class='text-xs ml-6'>

- Experiment tracking 🧪 
- Packaging 🎁
- Configuration ⚙️

</div>

- 👋 Community improvements 
- 📣 Q&A

<Socials />

---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/
---
<Overview />

---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/02_get_started/06_starters.html
---
<Overview />
<Pointer class="absolute bottom-63"/>
---
layout: iframe-right
url: >-
  https://kedro.readthedocs.io/en/stable/05_data/01_data_catalog.html#using-the-data-catalog-with-the-yaml-api
---
<Overview />

<Pointer class="absolute bottom-55"/>
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/06_nodes_and_pipelines/01_nodes.html#nodes
---
<Overview />
<Pointer class="absolute bottom-47"/>
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/06_nodes_and_pipelines/02_pipeline_introduction.html#pipelines
---
<Overview />
<Pointer class="absolute bottom-40"/>
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/09_development/03_commands_reference.html
---
<Overview />
<Pointer class="absolute bottom-32"/>
---
layout: iframe-right
url: https://kedro.readthedocs.io/en/stable/10_deployment/01_deployment_guide.html#deployment-guide
---
<Overview />
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
- <carbon-maximize class="inline text-yellow-500"/> Over time it has become too big and too bloated (esp. <kbd>IPython</kbd> sessions)
- 😭 It's now time to start divorce proceedings and move to a new approach...

</v-clicks>

<div class="grid grid-cols-3 p-1">
<div v-click class="border border-yellow-500 rounded-lg py-2 content-between m-3">
<p class="text-center font-mono">KedroSession</p>

<div class="text-sm">

- Introducing a <feather-database class="inline text-yellow-500"/>  store
- Deprecates the Journal <carbon-trash-can class="inline text-yellow-500"/>
- Time-travel superpowers <noto-superhero-medium-dark-skin-tone class="inline"/> 

</div>

</div>

<div v-click class="border border-yellow-500 rounded-lg py-2 content-between m-3">
<p class="text-center font-mono">settings.py</p>

<div class="text-sm">

- The recipe for a run <mdi-chef-hat class="inline text-yellow-500"/>
- <el-home-alt class="inline text-yellow-500"/> for `hooks` and `/conf/` loc
- <ri-caravan-fill class="inline text-yellow-500"/> `DataCatalog` is moving too...

</div>

</div>
<div v-click class="border border-yellow-500 rounded-lg py-2 content-between m-3">
<p class="text-center font-mono text-xl">pyproject.toml</p>

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
<p class="text-xs"><span class="animate-pulse">☝️</span> This annoying message will soon dissapear!</p>

</div>

</v-clicks>

<Socials />

---

# 💅 Kedro Viz: Not just a pretty face
<Speaker name="Susanna"/>

- FastAPI rewrite
- Plotly
- Modular pipelines

<Socials />

---
layout: quote
---
# 🔮 A look to the future 
  
- Packaging
- Config
- GE?

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
<li class="object-contain">Integration with <img src="https://mlflow.org/docs/latest/_static/MLflow-logo-final-black.png" class="object-contain h-10 inline bg-gray-200 rounded p-2"/> model-registry</li>
</ul>
</div>
<Socials />
<Speaker name="Merel"/>

---
---

# Community improvements

<Speaker name="Yetu"/>
<div grid="~ cols-2 gap-4">
  <div>
    <div v-click class="mb-7">
      <p class="text-gray-500 text-sm">
        Slide into our DMs on Discord <carbon-logo-discord class="inline text-purple-300" />
      </p>
      <p>
        Open forum to chat <carbon-chat-bot class="inline" /> with the dev team
        and for the community to assist support each other
        <carbon-help class="inline" />
      </p>
    </div>
    <div v-click class="mb-7">
      <p class="text-sm text-gray-500">
        GitHub Discussions will help codify knowledge
        <carbon-logo-github class="inline text-purple-300" />
      </p>
      <p>
        Threaded conversations <carbon-chat class="inline" />, answers marked by
        the maintainer <carbon-checkmark-filled class="inline" /> and pinned
        announcements <carbon-pin class="inline" />
      </p>
    </div>
    <div v-click>
      <p class="text-sm text-red-400">
        Deprecation of <strong>discourse.kedro.community </strong>
        <fa-brands-discourse class="inline" />
      </p>
      <p>We hope that the two avenues above will be better to this, StackOverflow
      <fa-brands-stack-overflow class="inline" /> and other platforms</p>
    </div>
  </div>
  <v-clicks at=1 >
    <div class="object-centre">
    <span
        class="
          icon-btn
          bg-dark-500
          rounded
          shadow-lg
          m-2
          -ml-0.3
          text-sm 
          text-purple-300
          animate-pulse
        "
        ><a href="https://discord.com/invite/sNR3R2M6"
          ><code>discord.com/invite/sNR3R2M6</code></a
        ></span
      >
    <iframe
      src="https://discord.com/widget?id=778216384475693066&theme=dark"
      allowtransparency="true"
      width="400" height="300"
      sandbox="allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts"
    ></iframe>
    </div>
  </v-clicks>
</div>

<Socials />

---
layout: quote
---
# 📣 Open Q&A Session
<Socials />
