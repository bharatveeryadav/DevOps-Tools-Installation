<pre class="highlight"><code><span class="gp">$</span><span class="w"> </span>modprobe kvm
</code></pre>



<div class="language-console highlighter-rouge"><button class="copy" aria-label="Copy code to clipboard"><svg aria-hidden="true" data-testid="geist-icon" fill="none" height="18" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="18" style="color: currentcolor;"><path d="M8 17.929H6c-1.105 0-2-.912-2-2.036V5.036C4 3.91 4.895 3 6 3h8c1.105 0 2 .911 2 2.036v1.866m-6 .17h8c1.105 0 2 .91 2 2.035v10.857C20 21.09 19.105 22 18 22h-8c-1.105 0-2-.911-2-2.036V9.107c0-1.124.895-2.036 2-2.036z"></path></svg></button><div class="highlight"><pre class="highlight"><code><span class="gp">$</span><span class="w"> </span>modprobe kvm_intel  <span class="c"># Intel processors</span>
<span class="go">
</span><span class="gp">$</span><span class="w"> </span>modprobe kvm_amd    <span class="c"># AMD processors</span>
</code></pre></div></div>


<div class="language-console highlighter-rouge"><button class="copy" aria-label="Copy code to clipboard"><svg aria-hidden="true" data-testid="geist-icon" fill="none" height="18" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="18" style="color: currentcolor;"><path d="M8 17.929H6c-1.105 0-2-.912-2-2.036V5.036C4 3.91 4.895 3 6 3h8c1.105 0 2 .911 2 2.036v1.866m-6 .17h8c1.105 0 2 .91 2 2.035v10.857C20 21.09 19.105 22 18 22h-8c-1.105 0-2-.911-2-2.036V9.107c0-1.124.895-2.036 2-2.036z"></path></svg></button><div class="highlight"><pre class="highlight"><code><span class="gp">$</span><span class="w"> </span>kvm-ok
</code></pre></div></div>


<div class="language-console highlighter-rouge"><button class="copy" aria-label="Copy code to clipboard"><svg aria-hidden="true" data-testid="geist-icon" fill="none" height="18" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="18" style="color: currentcolor;"><path d="M8 17.929H6c-1.105 0-2-.912-2-2.036V5.036C4 3.91 4.895 3 6 3h8c1.105 0 2 .911 2 2.036v1.866m-6 .17h8c1.105 0 2 .91 2 2.035v10.857C20 21.09 19.105 22 18 22h-8c-1.105 0-2-.911-2-2.036V9.107c0-1.124.895-2.036 2-2.036z"></path></svg></button><div class="highlight"><pre class="highlight"><code><span class="gp">$</span><span class="w"> </span>lsmod | <span class="nb">grep </span>kvm
<span class="go">kvm_amd               167936  0
ccp                   126976  1 kvm_amd
kvm                  1089536  1 kvm_amd
irqbypass              16384  1 kvm
</span></code></pre></div></div>

<p>To check ownership of <code class="language-plaintext highlighter-rouge">/dev/kvm</code>, run :</p>


<div class="language-console highlighter-rouge"><button class="copy" aria-label="Copy code to clipboard"><svg aria-hidden="true" data-testid="geist-icon" fill="none" height="18" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="18" style="color: currentcolor;"><path d="M8 17.929H6c-1.105 0-2-.912-2-2.036V5.036C4 3.91 4.895 3 6 3h8c1.105 0 2 .911 2 2.036v1.866m-6 .17h8c1.105 0 2 .91 2 2.035v10.857C20 21.09 19.105 22 18 22h-8c-1.105 0-2-.911-2-2.036V9.107c0-1.124.895-2.036 2-2.036z"></path></svg></button><div class="highlight"><pre class="highlight"><code><span class="gp">$</span><span class="w"> </span><span class="nb">ls</span> <span class="nt">-al</span> /dev/kvm
</code></pre></div></div>

<p>Add your user to the kvm group in order to access the kvm device:</p>

<div class="language-console highlighter-rouge"><button class="copy" aria-label="Copy code to clipboard"><svg aria-hidden="true" data-testid="geist-icon" fill="none" height="18" shape-rendering="geometricPrecision" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" viewBox="0 0 24 24" width="18" style="color: currentcolor;"><path d="M8 17.929H6c-1.105 0-2-.912-2-2.036V5.036C4 3.91 4.895 3 6 3h8c1.105 0 2 .911 2 2.036v1.866m-6 .17h8c1.105 0 2 .91 2 2.035v10.857C20 21.09 19.105 22 18 22h-8c-1.105 0-2-.911-2-2.036V9.107c0-1.124.895-2.036 2-2.036z"></path></svg></button><div class="highlight"><pre class="highlight"><code><span class="gp">$</span><span class="w"> </span><span class="nb">sudo </span>usermod <span class="nt">-aG</span> kvm <span class="nv">$USER</span>
</code></pre></div></div>


<h1 id="title">Install on Ubuntu</h1>
