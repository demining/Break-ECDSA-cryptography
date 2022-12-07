# The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file

<p>In this article, we will talk about extracting signature values&nbsp;&nbsp;<code>ECDSA R, S, Z</code>&nbsp;​​from the Bitcoin blockchain, but first, let’s remember the very first serious vulnerability in the blockchain transaction that was discovered by&nbsp;&nbsp;Niels&nbsp;<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener">Schneider</a>&nbsp;&nbsp;(&nbsp;<code>Nils Schneider</code>&nbsp;<em>aka</em>&nbsp;&nbsp;tcatm&nbsp;&nbsp;<a href="https://github.com/tcatm" target="_blank" rel="noreferrer noopener"><strong>)</strong></a></p>
<p>Bitcoin developer and owner&nbsp;&nbsp;<em>of «BitcoinWatch»</em>&nbsp;&nbsp;&amp;&nbsp;&nbsp;<em>«BitcoinCharts».</em></p>
<figure class="wp-block-image"><img title="4.1 History of dangerous random attacks on Bitcoin" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/20d6748c4bdd5e28ada4e9d06b9e8d35.png" alt="4.1 History of dangerous random attacks on Bitcoin"><figcaption>4.1 History of dangerous random attacks on Bitcoin</figcaption></figure>
<blockquote class="wp-block-quote"><p>Document&nbsp;&nbsp;<code>[PDF]</code>:&nbsp;<a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener"><em>Private Key Recovery Combination Attacks: On Extreme Fragility of Popular Bitcoin Key Management, Wallet and Cold Storage Solutions in Presence of Poor RNG Events</em></a><a href="https://eprint.iacr.org/2014/848.pdf" target="_blank" rel="noreferrer noopener">&nbsp;</a></p></blockquote>
<p><em>On December 25, 2012,</em>&nbsp;&nbsp;Nils discovered a potential weakness in some Bitcoin blockchain transactions.</p>
<p><strong>Look at this transaction:</strong></p>
<p><code>transaction:</code>&nbsp;<a href="https://www.blockchain.com/btc/tx/9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1" target="_blank" rel="noreferrer noopener">9ec4bc49e828d924af1d1029cacf709431abbde46d59554b62bc270e3b29c4b1</a></p>
<hr class="wp-block-separator has-alpha-channel-opacity">
<figure class="wp-block-image"><img src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/cc32e294aa0e77019d1581ce61893349.png" alt="The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file"></figure>
<hr class="wp-block-separator has-alpha-channel-opacity">
<pre class="wp-block-code"><code>input script 1:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1022044e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff

input script 2:
30440220d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad102209a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab0104dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></pre>
<p>This transaction has two inputs and one output.<br>
If you look closely at the two input scripts, you will notice that there are quite a few identical bytes at the beginning and at the end.<br>
Those bytes at the end are the hex encoded public key of the address the coins are being spent on, so there’s nothing wrong with that.<br>
However, the first half of the script is the actual signature&nbsp;&nbsp;<code>(r, s)</code>:</p>
<pre class="wp-block-code"><code>r1: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1
r2: d47ce4c025c35ec440bc81d99834a624875161a26bf56ef7fdc0f5d52f843ad1

s1: 44e1ff2dfd8102cf7a47c21d5c9fd5701610d04953c6836596b4fe9dd2f53e3e
s2: 9a5f1c75e461d7ceb1cf3cab9013eb2dc85b6d0da8c3c6e27e3a5a5b3faa5bab</code></pre>
<blockquote class="wp-block-quote"><p>As you can see,&nbsp; it’s&nbsp;<code>r1</code>&nbsp;the same&nbsp;&nbsp;<code>r2</code>.&nbsp;<em>This is&nbsp;&nbsp;</em><strong><em><u>a huge problem</u></em></strong><em>&nbsp;.</em></p></blockquote>
<blockquote class="wp-block-quote"><p>We can restore the&nbsp;&nbsp;<strong><u>private key</u></strong>&nbsp;&nbsp;to this public key:</p>
<p><code>04dbd0c61532279cf72981c3584fc32216e0127699635c2789f549e0730c059b81ae133016a69c21e23f1859a95f06d52b7bf149a8f2fe4e8535c8a829b449c5ff</code></p></blockquote>
<p>To do this, we can use a simple formula from school algebra 😉</p>
<pre class="wp-block-code"><code>private key = (<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>))</code></pre>
<p>We just need to find&nbsp;&nbsp;<code>z1</code>&nbsp;and&nbsp;<code>z2</code></p>
<p>These are&nbsp;&nbsp;<code>хэши</code>&nbsp;the outputs that need to be signed.&nbsp;Let’s get the output transactions and count them (computed by&nbsp;&nbsp;<code>OP_CHECKSIG</code>):</p>
<pre class="wp-block-code"><code>z1: c0e2d0a89a348de88fda08211c70d1d7e52ccef2eb9459911bf977d587784c6e
z2: 17b0f41c8c337ac1e18c98759e83a8cccbc368dd9d89e5f03cb633c265fd0ddc</code></pre>
<p>Next, we pack all these values ​​​​in one&nbsp;&nbsp;<em>Python</em>&nbsp;—&nbsp;<em>script:&nbsp;</em>&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">vulnerabilityR.py</a></p>
<figure class="wp-block-image"><img title="Python script: vulnerabilityR.py" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/c5f301358b79c833d7701b7c883235a7.png" alt="Python script: vulnerabilityR.py"><figcaption>Python script: vulnerabilityR.py</figcaption></figure>
<p><code>p</code>&nbsp;is just an order&nbsp; of magnitude&nbsp;<code>G</code>, a parameter of the curve&nbsp;&nbsp;<code>secp256k1</code>used by Bitcoin.</p>
<p>Let’s create a field for our calculations:</p>
<pre class="wp-block-code"><code>K = GF(<strong>p</strong>)</code></pre>
<pre class="wp-block-code"><code>K((<strong>z1*s2</strong> - z2*s1)/(<strong>r*</strong>(<strong>s1-s2</strong>)))</code></pre>
<p>Let’s run the script:&nbsp;<code>python3 vulnerabilityR.py</code></p>
<p>Next, our script:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/vulnerabilityR.py" target="_blank" rel="noreferrer noopener">vulnerabilityR.py</a>&nbsp;will &nbsp;calculate&nbsp;&nbsp;<strong><u>the private key</u></strong>&nbsp;&nbsp;in this field:</p>
<pre class="wp-block-code"><code>ADDR: 1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm
WIF:  5KJp7KEffR7HHFWSFYjiCUAntRSTY69LAQEX1AUzaSBHHFdKEpQ
hex:  c477f9f65c22cce20657faa5b2d1d8122336f851a508a1ed04e479c34985bf96</code></pre>
<figure class="wp-block-image"><img title="Checking the private key on the bitaddress website" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/a69992dcf93bacd0324c9a06722be9b5.png" alt="Checking the private key on the bitaddress website"><figcaption>Checking the private key on the bitaddress website</figcaption></figure>
<p><em><u>Private key found!</u></em></p>
<p><a href="https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/1BFhrfTTZP3Nw4BNy4eX4KFLsn9ZeijcMm</a></p>
<figure class="wp-block-image"><img title="
0.1638109 BTC" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/049126899d0dc2b84a30b18fc496c258.png" alt="
0.1638109 BTC"><figcaption>0.1638109 BTC</figcaption></figure>
<blockquote class="wp-block-quote"><p>Of course, the developers of Bitcoin fixed this vulnerability by introducing deterministic functions.</p>
<p>This feature&nbsp;&nbsp;<code>RFC 6979</code>&nbsp;introduces an element of randomness into the Bitcoin signature, which enhances the cryptographic strength of the transaction.&nbsp;<code>ECDSA</code></p></blockquote>
<p>Document&nbsp;&nbsp;<code>[PDF]</code>:&nbsp;<a href="https://datatracker.ietf.org/doc/html/rfc6979" target="_blank" rel="noreferrer noopener"><em>RFC 6979: Deterministic Usage of the Digital Signature Algorithm (DSA) and Elliptic Curve Digital Signature Algorithm (ECDSA)</em></a><a href="https://eprint.iacr.org/2014/848.pdf">&nbsp;</a></p>
<hr class="wp-block-separator has-alpha-channel-opacity">
<h2>As we know in practice, there are completely different vulnerable transactions in the Bitcoin blockchain.</h2>
<blockquote class="wp-block-quote"><p>We previously posted&nbsp;&nbsp;<code>статью</code>:&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><em>“One weak transaction in ECDSA on the Bitcoin blockchain and with the help of Lattice Attack we received a Private Key to BTC coins”</em></a></p></blockquote>
<div class="wp-block-image">
<figure class="aligncenter is-resized"><a href="https://cryptodeeptech.ru/lattice-attack/" target="_blank" rel="noreferrer noopener"><img loading="lazy" title="https://cryptodeeptech.ru/lattice-attack" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/6b872307d4a4dc3a74386c2b83d133a2.png" alt="https://cryptodeeptech.ru/lattice-attack" width="562" height="77"></a></figure>
</div>
<p>Now let’s get the public key&nbsp;&nbsp;<code>Bitcoin</code>&nbsp;<code>ECDSA</code>&nbsp;and value&nbsp; ourselves&nbsp;<code>R, S, Z</code>from the&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/RawTX.json" target="_blank" rel="noreferrer noopener">«RawTX.json»</a>&nbsp;file &nbsp;(which we got in&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/01BlockchainGoogleDrive" target="_blank" rel="noreferrer noopener"><strong>01BlockchainGoogleDrive</strong></a>&nbsp;&nbsp;)</p>
<ul>
<li>To do this, use the Terminal for Google Colab&nbsp;&nbsp;<a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[&nbsp;<strong>TerminalGoogleColab]</strong></a></li>
<li>Earlier I recorded a video:&nbsp;&nbsp;<a href="https://www.youtube.com/watch?v=S2D7PI6dK08" target="_blank" rel="noreferrer noopener"><strong>«TERMINAL in Google Colab creating all the conveniences for working in GITHUB»</strong></a></li>
<li>Let’s go through the&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener"><strong>«CryptoDeepTools»</strong></a>&nbsp;repository &nbsp;for a detailed cryptanalysis and take a closer look at how the&nbsp;&nbsp;<em>Bash script</em>&nbsp;works :&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></li>
</ul>
<figure class="wp-block-image"><img title="Teams" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/7d1bdc190149e6da8505d21155f14bbd.png" alt="Teams"><figcaption>Teams</figcaption></figure>
<figure class="wp-block-image"><img title="Files" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/9bfc350c715272db79f6bd5c6039e924.png" alt="Files"><figcaption>Files</figcaption></figure>
<figure class="wp-block-image"><img title="Our Bash script code: getsign.sh" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/5f0cf56f00c897f69fab24e8a3073588.png" alt="Our Bash script code: getsign.sh"><figcaption>Our Bash script code: getsign.sh</figcaption></figure>
<blockquote class="wp-block-quote"><p>And so let’s take a look at the whole work&nbsp; of the&nbsp;<em>Bash script</em>&nbsp;in detail :&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a></p></blockquote>
<pre class="wp-block-code"><code>cat RawTX.json &gt; index.json</code></pre>
<p>Making a copy of a file&nbsp;&nbsp;<code>RawTX.json</code>&nbsp;into a new file&nbsp;<code>index.json</code></p>
<pre class="wp-block-code"><code><strong>for</strong> run <strong>in</strong> {1..4}; <strong>do</strong></code></pre>
<p>We open&nbsp; it because&nbsp;&nbsp;we take&nbsp;&nbsp;<em>4 lines</em><code>ЦИКЛ</code>&nbsp;&nbsp;in the file&nbsp;<code>index.json</code>&nbsp;<code>{1..4}</code></p>
<pre class="wp-block-code"><code>export LINE=1 ; sed -n "${LINE}p" index.json &gt; index2.json</code></pre>
<p>The utility&nbsp;&nbsp;<code>export</code>&nbsp;takes&nbsp;&nbsp;<em>line #1</em>&nbsp;&nbsp;and saves it in a new file&nbsp;<code>index2.json</code></p>
<pre class="wp-block-code"><code>sed -i '1d' index.json</code></pre>
<p>The utility&nbsp;&nbsp;<code>sed</code>&nbsp;removes&nbsp;&nbsp;<em>line #1&nbsp;</em>&nbsp;from the file&nbsp;<code>index.json</code></p>
<figure class="wp-block-image"><img title="The echo utility creates a Python script for us fileopen.py" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/972d1b5554e84191da57b16415061198.png" alt="The echo utility creates a Python script for us fileopen.py"><figcaption>The echo utility creates a Python script for us fileopen.py</figcaption></figure>
<pre class="wp-block-code"><code>python3 fileopen.py</code></pre>
<p>We run&nbsp;&nbsp;<em>the Python script</em>&nbsp;<code>fileopen.py</code>&nbsp;&nbsp;and successfully creates a new&nbsp;&nbsp;<em>Bash script</em>&nbsp;:&nbsp;<code>signscript.sh</code></p>
<pre class="wp-block-code"><code>chmod +x signscript.sh
./signscript.sh</code></pre>
<p>We get the rights to the&nbsp;&nbsp;<em>Bash script</em>&nbsp;: signscript.sh</p>
<blockquote class="wp-block-quote"><p>As a result,&nbsp; the&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/breakECDSA.py" target="_blank" rel="noreferrer noopener">breakECDSA.py&nbsp;</a><em>Python script</em>&nbsp;&nbsp;is launched, &nbsp;which eventually extracts the&nbsp;&nbsp;value&nbsp;&nbsp;&nbsp;and public key of Bitcoin from<code>RawTX</code><code>R, S, Z</code></p>
<p>All this is saved to a file:&nbsp;<code>"signatures.json"</code></p></blockquote>
<figure class="wp-block-image"><img title="file: &quot;signatures.json&quot; Bitcoin public key and R, S, Z value" src="./The very first serious vulnerability in Blockchain and how to get the public key Bitcoin ECDSA RSZ value from the RawTX file - «CRYPTO DEEP TECH»_files/2e19dfc270a6f0bc6bd2ea9123215442.png" alt="file: &quot;signatures.json&quot; Bitcoin public key and R, S, Z value"><figcaption>file: «signatures.json» Bitcoin public key and R, S, Z value</figcaption></figure>
<pre class="wp-block-code"><code><strong>rm</strong> <strong>signscript</strong>.sh
<strong>rm</strong> <strong>fileopen</strong>.py</code></pre>
<p>The utility&nbsp;&nbsp;<code>rm</code>&nbsp;removes&nbsp;&nbsp;<em>the Python script</em>&nbsp;<code>fileopen.py</code>&nbsp;&nbsp;and successfully creates a new&nbsp;&nbsp;<em>Bash script</em>&nbsp;:&nbsp;<code>signscript.sh</code></p>
<pre class="wp-block-code"><code><strong>done</strong></code></pre>
<p>As a result, everything will end after&nbsp;<em>&nbsp;4 cycles</em></p>
<pre class="wp-block-code"><code>rm <strong>index</strong>.json</code></pre>
<p>The cycle closes and the utility&nbsp;&nbsp;<code>rm</code>&nbsp;deletes&nbsp;<code>index.json</code></p>
<p><em>Bash script</em>&nbsp;:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography/getsign.sh" target="_blank" rel="noreferrer noopener">getsign.sh</a>&nbsp;<code>Завершает работу!</code></p>
<h2>Now we have learned:</h2>
<ul>
<li>Get public key&nbsp;&nbsp;<code>Bitcoin&nbsp;</code>from<code>&nbsp;ECDSA</code></li>
<li>Get value&nbsp;&nbsp;<code>R, S, Z</code>&nbsp;from<code>&nbsp;ECDSA</code></li>
<li>Apply it for&nbsp;<code>криптоанализа</code></li>
</ul>
<p class="has-vivid-cyan-blue-color has-text-color"><strong>Source code:&nbsp;&nbsp;<a href="https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography" target="_blank" rel="noreferrer noopener">https://github.com/demining/CryptoDeepTools/blob/main/02BreakECDSAcryptography</a></strong></p>
<p class="has-vivid-cyan-blue-color has-text-color"><strong>Telegram:&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">https://t.me/cryptodeeptech</a></strong></p>
<p class="has-vivid-cyan-blue-color has-text-color"><strong>Video:&nbsp;&nbsp;<a href="https://youtu.be/BYd-cuFRZmM" target="_blank" rel="noreferrer noopener">https://youtu.be/BYd-cuFRZmM</a></strong></p>
<p><strong><a href="https://cryptodeeptech.ru/break-ecdsa-cryptography">Source: https://cryptodeeptech.ru/break-ecdsa-cryptography</a></strong></p>

---


|  | Donation Address |
| --- | --- |
| ♥ __BTC__ | 1Lw2gTnMpxRUNBU85Hg4ruTwnpUPKdf3nV |
| ♥ __ETH__ | 0xaBd66CF90898517573f19184b3297d651f7b90bf |

