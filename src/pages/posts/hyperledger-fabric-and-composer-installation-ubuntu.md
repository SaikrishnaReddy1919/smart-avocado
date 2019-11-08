---
title: Hyperledger Fabric and Composer Installation - Ubuntu
date: 2019-11-08T10:22:26.484Z
thumb_img_path: /images/2.jpg
excerpt: >-
  Yes, composer deprecated but it makes your understanding easy. So, have a look
  <img src="https://img.icons8.com/plasticine/100/000000/fat-emoji.png">
template: post
---
<h1>Installing pre-requisites</h1>

<p>The Hyperledger Composer pre-requisites can be installed on Ubuntu or MacOS. Choose your operating system to jump to the appropriate section, or scroll down to find the instructions:</p>

<h1 data-breakpage>Ubuntu</h1>

<p>To run Hyperledger Composer and Hyperledger Fabric, we recommend you have at least 4Gb of memory.</p>

<p>The following are prerequisites for installing the required development tools:</p>

<ul>

<li>Operating Systems: Ubuntu Linux 14.04 / 16.04 LTS (both 64-bit), or Mac OS 10.12</li>

<li>Docker Engine: Version 17.03 or higher</li>

<li>Docker-Compose: Version 1.8 or higher</li>

<li>Node: 8.9 or higher (note version 9 and higher is not supported)</li>

<li>npm: v5.x</li>

<li>git: 2.9.x or higher</li>

<li>Python: 2.7.x</li>

<li>A code editor of your choice, we recommend VSCode.</li>



</ul>

<p>-&gt;If you are installing Hyperledger Composer using Linux, be aware of the following advice:</p>

<ul>

<li>Login as a normal user, rather than root.</li>

<li>Do not <code>su</code> to root.</li>

<li>When installing prerequisites, use curl, then unzip using sudo.</li>

<li>Run prereqs-ubuntu.sh as a normal user. It may prompt for root password as some of it&#39;s actions are required to be run as root.</li>

<li>Do not use npm with <code>sudo</code> or <code>su</code> to root to use it.</li>

<li>Avoid installing node globally as root.\*\*</li>



</ul>

<p>If you&#39;re running on Ubuntu, you can download the prerequisites using the following commands:</p>

<pre><code class='language-shell' lang='shell'>curl -O https://hyperledger.github.io/composer/latest/prereqs-ubuntu.sh



chmod u+x prereqs-ubuntu.sh

</code></pre>

<p>Next run the script - as this briefly uses sudo during its execution, you will be prompted for your password.</p>

<pre><code>./prereqs-ubuntu.sh

</code></pre>

<h2>What next?</h2>

<blockquote><p>Congratulations, the installation of the pre-requisites for Hyperledger Composer is complete! ....</p>

</blockquote>

<h1 data-breakpage>Installing the development environment</h1>

<p>Follow these instructions to obtain the Hyperledger Composer development tools (primarily used to <em>create</em> Business Networks) and stand up a Hyperledger Fabric (primarily used to <em>run/deploy</em> your Business Networks locally). Note that the Business Networks you create can also be deployed to Hyperledger Fabric runtimes in other environments e.g. on a cloud platform.</p>

<h2>Before you begin</h2>

<p>Make sure you have installed the required pre-requisites, following the instructions in <a href='https://hyperledger.github.io/composer/latest/installing/installing-prereqs.html'><strong>Installing pre-requisites</strong></a>.</p>

<p>These instructions assume that you&#39;ve not installed the tools and used them before. If this is not the case, you might want to check that your previous setup is completely destroyed before you start following this guide. To learn how to do this, skip to the <a href='https://hyperledger.github.io/composer/latest/installing/development-tools.html#appendix'>Appendix</a>.</p>

<blockquote><p>To provide flexibility and enable the maximum number of dev, test and deployment scenarios, Composer is delivered as a set of components you can install with <code>npm</code> and control from the CLI. These instructions will tell you how to install everything first, then how to control your development environment.</p>

</blockquote>

<h1 data-breakpage>Installing components</h1>

<h3>Step 1: Install the CLI tools</h3>

<p>There are a few useful CLI tools for Composer developers. The most important one is <code>composer<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>cli</code>, which contains all the essential operations, so we&#39;ll install that first. Next, we&#39;ll also pick up <code>generator<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>hyperledger<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>composer</code>, <code>composer<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>rest<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>server</code> and <code>Yeoman</code>. Those last 3 are not core parts of the development environment, but they&#39;ll be useful if you&#39;re following the tutorials or developing applications that interact with your Business Network, so we&#39;ll get them installed now.</p>

<p>Note that you <strong>should not</strong> use <code>su</code> or <code>sudo</code> for the following npm commands.</p>

<ol>

<li><p>Essential CLI tools:</p>

<pre><code>npm install -g composer-cli@0.20

</code></pre>

</li>

<li><p>Utility for running a REST Server on your machine to expose your business networks as RESTful APIs:</p>

<pre><code>npm install -g composer-rest-server@0.20

</code></pre>

</li>

<li><p>Useful utility for generating application assets:</p>

<pre><code>npm install -g generator-hyperledger-composer@0.20

</code></pre>

</li>

<li><p>Yeoman is a tool for generating applications, which utilises <code>generator<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>hyperledger<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>composer</code>:</p>

<pre><code>npm install -g yo

</code></pre>

</li>



</ol>

<h3>Step 2: Install Playground</h3>

<p>If you&#39;ve already tried Composer online, you&#39;ll have seen the browser app &quot;Playground&quot;. You can run this locally on your development machine too, giving you a UI for viewing and demonstrating your business networks.</p>

<ol>

<li><p>Browser app for simple editing and testing Business Networks:</p>

<pre><code>npm install -g composer-playground@0.20

</code></pre>

</li>



</ol>

<h3>Step 3: Set up your IDE</h3>

<p>Whilst the browser app <em>can</em> be used to work on your Business Network code, most users will prefer to work in an IDE. Our favourite is <code>VSCode</code>, because a Composer extension is available.</p>

<ol>

<li>Install VSCode from this URL: <a href='https://code.visualstudio.com/download' target='_blank' class='url'>https://code.visualstudio.com/download</a></li>

<li>Open VSCode, go to Extensions, then search for and install the <code>Hyperledger Composer</code> extension from the Marketplace.</li>



</ol>

<h3>Step 4: Install Hyperledger Fabric</h3>

<p>This step gives you a local Hyperledger Fabric runtime to deploy your business networks to.</p>

<ol>

<li><p>In a directory of your choice (we will assume <code>~/fabric<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>dev<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>servers</code>), get the <code>.tar.gz</code> file that contains the tools to install Hyperledger Fabric:</p>

<pre><code>mkdir \~/fabric-dev-servers &amp;&amp; cd \~/fabric-dev-servers



curl -O https://raw.githubusercontent.com/hyperledger/composer-tools/master/packages/fabric-dev-servers/fabric-dev-servers.tar.gz

tar -xvf fabric-dev-servers.tar.gz

</code></pre>

<p>A <code>zip</code> is also available if you prefer: just replace the <code>.tar.gz</code> file with <code>fabric<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>dev<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>servers.zip</code> and the <code>tar <span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>xvf</code> command with a <code>unzip</code> command in the preceding snippet.</p>

</li>

<li><p>Use the scripts you just downloaded and extracted to download a local Hyperledger Fabric v1.2 runtime:</p>

<pre><code>cd ~/fabric-dev-servers

export FABRIC_VERSION=hlfv12

./downloadFabric.sh

</code></pre>

</li>



</ol>

<blockquote><p>Congratulations, you&#39;ve now installed everything required for the typical Developer Environment. Read on to learn some of the most common things you&#39;ll do with this environment to develop and test your Blockchain Business Networks.</p>

</blockquote>

<h1 data-breakpage>Controlling your dev environment</h1>

<h2>Starting and stopping Hyperledger Fabric</h2>

<p>You control your runtime using a set of scripts which you&#39;ll find in <code>~/fabric<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>dev<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>servers</code> if you followed the suggested defaults.</p>

<p>The first time you start up a new runtime, you&#39;ll need to run the start script, then generate a PeerAdmin card:</p>

<pre><code>    cd ~/fabric-dev-servers

\    export FABRIC_VERSION=hlfv12

\    ./startFabric.sh

\    ./createPeerAdminCard.sh

</code></pre>

<p>You can start and stop your runtime using <code>~/fabric<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>dev<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>servers/stopFabric.sh</code>, and start it again with <code>~/fabric<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>dev<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>servers/startFabric.sh</code>.</p>

<p>At the end of your development session, you run <code>~/fabric<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>dev<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>servers/stopFabric.sh</code> and then <code>~/fabric<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>dev<span style='font-family:"Open Sans", "Clear Sans", "Helvetica Neue", Helvetica, Arial, sans-serif'>-</span>servers/teardownFabric.sh</code>. Note that if you&#39;ve run the teardown script, the next time you start the runtime, you&#39;ll need to create a new PeerAdmin card just like you did on first time startup.</p>

<blockquote><p>The local runtime is intended to be frequently started, stopped and torn down, for development use. If you&#39;re looking for a runtime with more persistent state, you&#39;ll want to run one outside of the dev environment, and deploy Business Networks to it. Examples of this include running it via Kubernetes, or on a managed platform such as IBM Cloud.</p>

</blockquote>

<h2>Start the web app (&quot;Playground&quot;)</h2>

<p>To start the web app, run:</p>

<pre><code>    composer-playground

</code></pre>

<p>It will typically open your browser automatically, at the following address: <a href='http://localhost:8080/login' target='_blank' class='url'>http://localhost:8080/login</a></p>

<p>You should see the <code>PeerAdmin@hlfv1</code> Card you created with the <code>createPeerAdminCard</code> script on your &quot;My Business Networks&quot; screen in the web app: if you don&#39;t see this, you may not have correctly started up your runtime!</p>

<blockquote><p>Congratulations, you&#39;ve got all the components running, and you also know how to stop and tear them down when you&#39;re done with your dev session.</p>

</blockquote>

<h2>What Next?</h2>

<ul>

<li>Learn how to use the web app UI with the <a href='https://hyperledger.github.io/composer/latest/tutorials/playground-tutorial.html'>Playground Tutorial</a></li>

<li>Learn how to use the CLI and VSCode tools with the <a href='https://hyperledger.github.io/composer/latest/tutorials/developer-tutorial.html'>Developer Tutorial</a></li>



</ul>

<p>&nbsp;</p>

<h1 data-breakpage>Appendix: destroy a previous setup</h1>

<p>If you&#39;ve previously used an older version of <strong>Hyperledger Composer</strong> and are now setting up a new install, you may want to kill and remove all previous Docker containers, which you can do with these commands:</p>

<pre>

<code> $ docker kill $(docker ps -q)

 $ docker rm $(docker ps -aq)

 $ docker rmi $(docker images dev-* -q)

</code></pre>

<p>&nbsp;</p>



<h5>Mac user?</h5>

<h6>Follow instructions from here:</h6>

<p><a href='https://hyperledger.github.io/composer/latest/installing/installing-prereqs.html#macos' target='_blank' class='url'>https://hyperledger.github.io/composer/latest/installing/installing-prereqs.html#macos</a></p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>&nbsp;</p>
