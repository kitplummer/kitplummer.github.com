---
layout: post
title: Searching for a Mephisto Theme...
---

…that can embed code examples well. Plus, I’m tired of the blackness. I
mean is a blackhole really black?<br><br>

So, I think this one blocks the code well…just need highlighting.
Probably need to start with getting HostingRails.com to install the
ultraviolet gem.  
<br><br>  
\[Update: Solving the problem the other way with this spiffy
<a href="http://antoniocangiano.com/2008/10/28/pygments-textmate-bundle/#comment-4457">Textmate
bundle</a>\]

\[Update2: Ok this sucks. I want this: http://www.punneng.net/jazzy/\]  
<br><br>  
Testing:  
<br><br>

<div class="highlight">

    <span class="c">/**</span>
    <span class="c">* Resource holds the main unit of operation for the Data Discovery Service.  </span>
    <span class="c">* The value is either a URL, or input data to be processed.  A resource hasMany</span>
    <span class="c">* View(s) objects, which are populated by interpreter bundles.</span>
    <span class="c">* @author Kit Plummer</span>
    <span class="c">*/</span>
    <span class="kd">class</span> <span class="nc">Resource</span> <span class="o">{</span>
        <span class="n">String</span> <span class="n">url</span>
        <span class="n">String</span> <span class="n">data</span>

        <span class="kd">static</span> <span class="n">hasMany</span> <span class="o">=</span> <span class="o">[</span><span class="nl">views:</span><span class="n">View</span><span class="o">]</span>

        <span class="kd">static</span> <span class="n">constraints</span> <span class="o">=</span> <span class="o">{</span>
            <span class="n">url</span><span class="o">(</span><span class="nl">nullable:</span> <span class="kc">true</span><span class="o">,</span> <span class="nl">url:</span> <span class="kc">true</span><span class="o">,</span> <span class="nl">validator:</span> <span class="o">{</span> <span class="n">val</span><span class="o">,</span> <span class="n">obj</span> <span class="o">-&gt;</span>
                <span class="k">if</span> <span class="o">(</span><span class="n">obj</span><span class="o">.</span><span class="na">url</span> <span class="o">==</span> <span class="kc">null</span> <span class="o">&amp;&amp;</span> <span class="n">obj</span><span class="o">.</span><span class="na">data</span> <span class="o">==</span> <span class="kc">null</span><span class="o">)</span> <span class="k">return</span> <span class="o">[</span><span class="err">&#39;</span><span class="n">url</span> <span class="n">OR</span> <span class="n">data</span> <span class="n">required</span><span class="o">.</span><span class="err">&#39;</span><span class="o">]</span>
            <span class="o">})</span>
            <span class="n">data</span><span class="o">(</span><span class="nl">nullable:</span> <span class="kc">true</span><span class="o">,</span> <span class="nl">maxSize:</span><span class="mi">5000</span><span class="o">,</span> <span class="nl">validator:</span> <span class="o">{</span> <span class="n">val</span><span class="o">,</span> <span class="n">obj</span> <span class="o">-&gt;</span>
                <span class="k">if</span> <span class="o">(</span><span class="n">obj</span><span class="o">.</span><span class="na">data</span> <span class="o">==</span> <span class="kc">null</span> <span class="o">&amp;&amp;</span> <span class="n">obj</span><span class="o">.</span><span class="na">url</span> <span class="o">==</span> <span class="kc">null</span><span class="o">)</span> <span class="k">return</span> <span class="o">[</span><span class="err">&#39;</span><span class="n">url</span> <span class="n">OR</span> <span class="n">data</span> <span class="n">required</span><span class="o">.</span><span class="err">&#39;</span><span class="o">]</span>
            <span class="o">})</span>

        <span class="o">}</span>

        <span class="n">String</span> <span class="nf">toString</span><span class="o">()</span> <span class="o">{</span>
            <span class="k">this</span><span class="o">.</span><span class="na">id</span>
        <span class="o">}</span>
    <span class="o">}</span>

</div>
