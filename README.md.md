<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>README.md</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__left">
    <div class="stackedit__toc">
      
<ul>
<li><a href="#gateway">Gateway</a>
<ul>
<li><a href="#outline">Outline</a></li>
<li><a href="#legal-notice">Legal Notice</a></li>
<li><a href="#contact">Contact</a></li>
<li><a href="#table-of-contents">Table of Contents</a>
<ul>
<li></li>
</ul>
</li>
<li><a href="#installing">2.0 Installing</a></li>
</ul>
</li>
<li><a href="#definitionsglossary">[#Definitions](#Glossary</a></li>
<li><a href="#design-architecture-and-optimization">Design, Architecture and Optimization</a></li>
<li>
<ul>
<li></li>
<li><a href="#systems-based-approach">Systems Based approach</a></li>
<li><a href="#rulebook-v.0.8.32">RuleBook v.0.8.32</a></li>
<li><a href="#dispute-resolution">Dispute Resolution</a></li>
<li><a href="#freight-specifics">Freight Specifics</a></li>
<li><a href="#the-system-will-be-constructed-multiple-distinct-components">The system will be constructed multiple distinct components:</a></li>
<li><a href="#v.2.0.5">v.2.0.5</a></li>
<li><a href="#definitions-and-specifications">Definitions and Specifications</a>
<ul>
<li>
<ul>
<li></li>
<li><a href="#network-wide-settings">Network Wide Settings</a></li>
</ul>
</li>
<li><a href="#system-wide-settings--procedure">System wide settings & procedure</a>
<ul>
<li></li>
<li><a href="#binding-processes-to-cpus-using-the-taskset-utility">Binding Processes to CPUs using the taskset utility</a></li>
<li><a href="#determinstic-filesystem">Determinstic Filesystem</a></li>
<li><a href="#hardware-clock-system-timestamping-suprasynchron">Hardware clock system timestamping (suprasynchron)</a>
<ul>
<li></li>
<li><a href="#sgx-driver">SGX Driver</a></li>
<li><a href="#configure-libsecp256k">configure libsecp256k</a></li>
</ul>
</li>
<li><a href="#building-client">Building Client</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
<li><a href="#sources--datasets">Sources & Datasets</a></li>
</ul>

    </div>
  </div>
  <div class="stackedit__right">
    <div class="stackedit__html">
      <h1 id="gateway">Gateway</h1>
<p>0.8.2</p>
<p><a href="www.freighttrust.com">www.freighttrust.com</a></p>
<h2 id="outline">Outline</h2>
<ul>
<li>Base Client</li>
<li>Drag and drop a file to load it</li>
<li>Ctrl/Cmd + S to save the source file</li>
<li>Support Github Flavored Markdown syntax</li>
<li>Support many languages highlight in editor and preview mode</li>
</ul>
<h2 id="legal-notice">Legal Notice</h2>
<pre class=" language-markdown"><code class="prism  language-markdown"><span class="token list punctuation">*</span> BSD-3-Clause License 
We also re-distribute other licenses including GPLv2, packages are identified in their respective directory with flag, 'GPL2-,APACHE-,...` 

Please read our Contributers License Agreement for contributions consiting more than 5 commits, or are otherwise "substantive in material effort" i.e. patenable work.

This software may contain export restricted cryptographic work, and as such may not be available legally in your jurisidiction 


"FREIGHT TRUST &amp; CLEARING CORPORATION"

</code></pre>
<h2 id="contact">Contact</h2>
<p><a href="https://freighttrust.com">https://freighttrust.com</a></p>
<p><a href="https://t.me/freighttrust">https://t.me/freighttrust</a></p>
<p><a href="https://twitter.com/freighttrustnet">https://twitter.com/freighttrustnet</a></p>
<p><a href="mailto:admin@freighttrust.com">admin@freighttrust.com</a></p>
<h3 id="keys.openpgp.org"><a href="http://keys.openpgp.org">keys.openpgp.org</a></h3>
<p><a href="mailto:admin@freighttrust.com">admin@freighttrust.com</a>  8B9B067C295049CA784D68F1995F1C84DCED4D6A</p>
<h2 id="table-of-contents">Table of Contents</h2>
<ul>
<li>Network Summary</li>
<li>Network resources (soft &amp; hard)</li>
<li>Network interaction</li>
<li>Network scaling</li>
<li>Sources &amp; Appendix</li>
</ul>
<p>Network Topology &amp; Design</p>
<h4 id="defining-mechanics-and-principles-of-network">Defining Mechanics and Principles of Network</h4>
<blockquote>
<p>PRINCIPLE OF MAXIMAL AUTONOMY: The purpose of a planning<br>
network is to provide tools for local planning, rather than<br>
primarily to provide  centralized control of the planning at<br>
different nodes.</p>
</blockquote>
<blockquote>
<p>PRINCIPLE OF REDUNDANCY OF POTENTIAL COMMAND: Power resides<br>
where information resides.</p>
</blockquote>
<blockquote>
<p>PRINCIPLE OF EVENTS OF LOW PROBABILITY…the fundamental purpose<br>
of a system should not be jeopardized, nor its fundamental<br>
objectives significantly compromised, in order to accommodate<br>
events of extremely low probability</p>
</blockquote>
<blockquote>
<p>LAW OF REGULATORY MODELS…every good regulator of a system must<br>
be (contain) a model of that system.</p>
</blockquote>
<h4 id="geoproximity-routing-traffic-flow-only">Geoproximity Routing (Traffic Flow Only)</h4>
<p>Geoproximity routing lets Amazon Route 53 route traffic to your resources based on the geographic location of your users and your resources. You can also optionally choose to route more traffic or less to a given resource by specifying a value, known as a bias. A bias expands or shrinks the size of the geographic region from which traffic is routed to a resource.</p>
<p>To use geoproximity routing, you must use Route 53 traffic flow. You create geoproximity rules for your resources and specify one of the following values for each rule:</p>
<ul>
<li>
<p>If you’re using AWS resources, the AWS Region that you created the resource in</p>
</li>
<li>
<p>If you’re using non-AWS resources, the latitude and longitude of the resource</p>
</li>
</ul>
<p>To optionally change the size of the geographic region from which Route 53 routes traffic to a resource, specify the applicable value for the bias:</p>
<p>To expand the size of the geographic region from which Route 53 routes traffic to a resource, specify a positive integer from 1 to 99 for the bias. Route 53 shrinks the size of adjacent regions.</p>
<p>To shrink the size of the geographic region from which Route 53 routes traffic to a resource, specify a negative bias of -1 to -99. Route 53 expands the size of adjacent regions.</p>
<p>The following map shows four AWS Regions (numbered 1 through 4) and a location in Johannesburg, South Africa that is specified by latitude and longitude. <a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy.html#routing-policy-geo">docs.aws.amazon.com</a></p>
<p><a href="./dns-map-aws.png">image</a></p>
<p>DNS Records</p>
<p>NAPTR &amp; DDDS<br>
NAPTR Record Type<br>
A Name Authority Pointer (NAPTR) is a type of record that is used by Dynamic Delegation Discovery System (DDDS) applications to convert one value to another or to replace one value with another. For example, one common use is to convert phone numbers into SIP URIs.</p>
<p>The Value element for an NAPTR record consists of six space-separated values:</p>
<p>Order<br>
Preference<br>
Flags<br>
Service<br>
Regexp<br>
Replacement</p>
<p>DDDS: Enabling Barcode to Wallet Address<br>
<a href="https://tools.ietf.org/html/rfc3404#section-4.4">RFC 3404</a></p>
<p>Certificate Authority and CAA</p>
<h5 id="network-rewards-and-incentives">Network Rewards and Incentives</h5>
<p>formula:</p>
<p>The “base” (ie. uncle rate of a 0-gas block) is consistently ~6.7%</p>
<h2 id="installing">2.0 Installing</h2>
<h3 id="setting-up-client">Setting up client</h3>
<p>Step one:</p>
<p>SSH into AWS/GCP account</p>
<p>Downloads</p>
<pre><code>General availability client: RHEL/CentOS 7.4-7.7
disallowed: other distros (no ubuntu). 

Reference Build Vanilla 
http://linuxsoft.cern.ch/cern/centos/7/rt/CentOS-RT.repo

</code></pre>
<h4 id="section"></h4>
<ul>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> java</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> node.js</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> virtual box</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> docker</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> lxc</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> rust</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> mosh</li>
<li>[ ]</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> wget/curl/zsh</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> &amp;&amp;</li>
<li class="task-list-item"><input type="checkbox" class="task-list-item-checkbox" disabled=""> &amp;&amp;&amp;</li>
</ul>
<p>prep terminal<br>
ssh into instance on aws / gcp</p>
<h5 id="prep-terminal">1. prep terminal</h5>
<p>$ sudo dnf install mosh</p>
<pre><code>$ cd /etc/yum.repos.d
wget http://download.virtualbox.org/virtualbox/rpm/rhel/virtualbox.repo
</code></pre>
<h5 id="install-docker--docker-machine">2. Install docker &amp; docker-machine</h5>
<pre><code>$ install  docker-ce &amp; docker-machine
base=https://raw.githubusercontent.com/docker/machine/v0.16.0
for i in docker-machine-prompt.bash docker-machine-wrapper.bash docker-machine.bash
do
</code></pre>
<pre><code>$ sudo wget "$base/contrib/completion/bash/${i}" -P /etc/bash_completion.d
done 
</code></pre>
<br>
<p>⚠️  Issue with cgroup while installing docker? try:</p>
<pre><code>$ sudo yum install cgroup-lite
</code></pre>
<h5 id="install-nodenpm">3. Install node/npm</h5>
<pre><code>$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.1/install.sh | bash
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] &amp;&amp; \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] &amp;&amp; \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
</code></pre>
<h5 id="install--oracle-javavm-13.0.1">4. Install  oracle JavaVM 13.0.1</h5>
<p>This is a link to our S3 Bucket, if you can not access it please use Oracles Website to download it.</p>
<p><em>Please use at least 11.0.5 Oracle JVM/JDK for optimal performance</em></p>
<pre><code>$ yum install -y https://maidenlane.s3.amazonaws.com/jdk-13.0.1_linux-x64_bin.rpm(https://maidenlane.s3.amazonaws.com/jdk-13.0.1_linux-x64_bin.rpm)
</code></pre>
<h5 id="download-hyperledger-besu-client-base-image">6. Download Hyperledger Besu Client base image</h5>
<pre><code>$ docker pull hyperledger/besu:latest (1.3.5-SNAPSHOT)

</code></pre>
<h5 id="start-client">5. Start Client</h5>
<pre><code>$ bin/besu
</code></pre>
<h5 id="import-private-key-from-initial-validator-genesis">6. Import private key from initial validator genesis</h5>
<p>Your Private Key is tied to your Ethereum Foundation (Ethereum Main Network) Wallet Address.</p>
<pre><code>$ mv 0x1234ABCD.key /user/install-dir/besu/config
</code></pre>
<h5 id="import-private-key-from-initial-validator-genesis-1">7. Import private key from initial validator genesis</h5>
<pre><code>$ ./inspect.sh // self-check to make sure configured properly
$ ./gateway.sh // connect to network
</code></pre>
<p>…</p>
<p>(Placeholder)</p>
<p>.</p>
<p>####Footnotes;</p>
<p>recommended fusion/baseimage</p>
<p><a href="https://hub.docker.com/r/phusion/baseimage/">https://hub.docker.com/r/phusion/baseimage/</a></p>
<p>🚧 Construction Zone 🚧<br>
<br> Network Users Section</p>
<h3 id="freight-trust-protocol---bol-protocol">Freight Trust Protocol - BOL Protocol</h3>
<p>This document describes the architecture and system design of a decentralized multi-cast protocol to enable legal (both contractual and property) transfer of instrumitized documentation, i.e. documents of title. BOL is designed to enable users to create, agree to, and manage documents pertaining to the supply chain industry,<br>
without needing to rely on a physical paper document trail while still retaining all the legal qualities of a physical bearer instrument. It is in that respect to physicality, legality and extensiability that the protocol offers a robust and provable use case to industry participants versues other existing/developing solutions.</p>
<p>BOL Protocol is licsneded under the BSD 3-Clause Open Source Software license. A more permissive Apache 2.0 License is available upon request. BOL does not require any other open source licenses for it to work, that is to say it does not contain any other software that utilizes a different licesnesing regime, such as GPLv2.</p>
<h1 id="definitionsglossary">[#Definitions](#Glossary</h1>
<ul>
<li>x509</li>
<li>EIP-211 (not for publishing yet)</li>
</ul>
<h1 id="design-architecture-and-optimization">Design, Architecture and Optimization</h1>
<h1 id="section-1"></h1>
<p>To a lawyer, a legal contract has a distinct meaning:</p>
<pre><code>A contract is an agreement giving rise to obligations which are enforced or recognised by law. The
factor which distinguishes contractual from other legal obligations is that they are based on the
agreement of the contracting parties7.
For a contract to be valid, legal systems will impose certain requirements. Under English law, there
are four key elements that must (usually) be satisfied: 


(i) one of the contracting parties must make an offer to contract and the other(s)must accept that offer;
(ii) there must be ‘consideration’ for the
offer, this being some form of value that must be exchanged; 
(iii) the parties must have an intention
to form legal relations; and 
(iv) there must be certainty as to terms of the contract. 


*source* ISDA - "Smart Contracts and Distributed Ledger: A Legal Perspective"
</code></pre>
<p>Other systems of law may have other requirements – for example, under New York law, many legal contracts must be in writing and signed to become binding. Or in China where the color of the ink must be black: red or blue ink makes the signature inadmissiable. For our purposes, we will only consider the <em>de facto</em>, that is to say British Common Law for Maritime and the United States Unified Commerical Code (UCC).</p>
<p><strong>Architectural Design</strong></p>
<h3 id="functional-and-legal-equiviliance-provisions-for-dematerilizing-shipping-documents-or-any-other-bearer-instrument-with-negotiable-optionaliy">Functional and legal equiviliance provisions for dematerilizing shipping documents or any other bearer instrument with negotiable optionaliy</h3>
<p>Visually replicate paper bills, preserving the often industry / custom specific layout;</p>
<blockquote>
<p>a. Replicate the function of paper bills, including a party’s ability to issue, indorse, recut or surrender the e-bill;</p>
<p>b. Replicate the physical transfer of paper bills and, whilst all parties can view an e-bill (in copy form), the trading platform restricts access and indorsement to the current lawful holder (by way of fob and access code) as the e-bills securely move from one party to the next; and</p>
<p>c. Can be converted into paper bills, allowing them to be finally traded with parties which have not signed up to the ETS platform. However, it is notable that paper bills cannot be converted into e-bills since none of the ETS would be prepared to investigate and effectively warrant the provenance of paper bills and the physical cargo they represent.</p>
</blockquote>
<p>In designing a comprehesnvie <em>organism</em> (in the biological sense: a self regulating autonomous network is what we are striving to achieve) certain realities of business must be acknowledged. Wheres these  four principles appear to be desirable and should insofar as it is possible be pursued together in achieving our goals and more broadly the “user experience”:</p>
<ol>
<li>the promotion of certainty and predictability;</li>
<li>the promotion of uniformity of application;</li>
<li>the protection of democratic ideals andensuring of jurisprudential deliberation,</li>
<li>the retention of efficiency.</li>
</ol>
<h2 id="systems-based-approach">Systems Based approach</h2>
<p>Often when two companies deal with each other in the course of business, they will use standard form contracts. Often these standard forms contain terms which conflict (e.g. both parties include a liability waiver in their form). The ‘battle of the forms’ refers to the resulting legal dispute arising where both parties accept that a legally binding contract exists, but disagree about whose standard terms apply. Such disputes may be resolved by reference to the ‘last document rule’, i.e. whichever business sent the last document, or ‘fired the last shot’ (often the seller’s delivery note) is held to have issued the final offer and the buyer’s organisation is held to have accepted the offer by signing the delivery note or simply accepting and using the delivered goods.</p>
<p>&lt;!&gt; Two Modes: National and International</p>

<table>
<thead>
<tr>
<th align="left">Contract Function</th>
<th align="left">Parties</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">Master Covenant</td>
<td align="left">Mandatory, All Network Participants</td>
</tr>
<tr>
<td align="left">RuleBook Agreement</td>
<td align="left">Mandatory, All Commerical Orgs.</td>
</tr>
<tr>
<td align="left">Master Participation Agreement</td>
<td align="left">Mandatory for B2B</td>
</tr>
<tr>
<td align="left">Network Operator Agreement</td>
<td align="left">Mandatory for Node Operators</td>
</tr>
<tr>
<td align="left">Transactional Clauses</td>
<td align="left">Specific to Transaction Type</td>
</tr>
<tr>
<td align="left">Amendment Clauses</td>
<td align="left">Specific to Jurisdictional Area</td>
</tr>
<tr>
<td align="left">Business Terms and Conditions</td>
<td align="left">Unique to specific Business Entity</td>
</tr>
<tr>
<td align="left">Intergration Clause</td>
<td align="left">Mandatory, All Agreements</td>
</tr>
</tbody>
</table><h3 id="national-excludes-lex-mercatoria">National excludes lex mercatoria</h3>
<pre><code>Clause &lt;#&gt;  – Choice of law: lex mercatoria and Unidroit Principles

This contract is governed by general principles of law generally recognized in
international trade (lex mercatoria) together with the Unidroit Principles of
International Commercial Contracts (except for Articles 2.20, 3.2.7 and 6.2.1).
</code></pre>
<pre><code>Clause &lt;#&gt; – Network Model Clause

This contract shall be governed by the law of [State X] interpreted and supplemented
by the Freight Trust "RuleBook version v0.8.23" 

</code></pre>
<pre><code>Clause 6.1
“Any questions relating to this Agreement which are not expressly or implicitly settled
by the provisions contained in this Agreement shall be governed, in the following
order:
1) by the principles of law generally recognized in international trade as applicable to
international [type of contract: e.g., distributorship, licence] contracts,
2) by the relevant trade usages, and
3) by the Unidroit Principles of International Commercial Contracts,
with the exclusion of national laws.”
This clause, which is the most frequently used clause within the ICC model contracts,
states that the contract shall be governed by the lex mercatoria and the Unidroit
Principles and provides at the same time the following hierarchical order:
1. Contract provisions,
2. general principles of law applicable to the particular type of contract in question,
3. trade usages,
4. Unidroit Principles.
</code></pre>
<h3 id="replacement-of-a-transferable-document-or-instrument-with-an-electronic-transferable-record">Replacement of a transferable document or instrument with an electronic transferable record</h3>
<ol>
<li>
<p>An electronic transferable record may replace a transferable document or instrument if a reliable method for the change of medium is used.</p>
</li>
<li>
<p>For the change of medium to take effect, a statement indicating a change of medium shall be inserted in the electronic transferable record.</p>
</li>
<li>
<p>Upon issuance of the electronic transferable record in accordance with paragraphs 1 and 2, the transferable document or instrument shall be made inoperative and ceases to have any effect or validity.</p>
</li>
<li>
<p>A change of medium in accordance with paragraphs 1 and 2 shall not affect the rights and obligations of the parties.</p>
</li>
</ol>
<h4 id="meeting-mletr-requirements">Meeting MLETR Requirements</h4>
<blockquote>
<p>• 10(1)(a): equivalence in terms of content (but see also Article 6 – additional  content not precluded – potential to increase functionality).</p>
<p>• 10(1)(b)(i) Mechanism for precluding “double pending”: performance obligation must &gt;be singular.</p>
<p>• 10(1)(b)(ii) Person to whom performance is due must be identifiable.</p>
<p>• 10(1)(b)(iii) and 10(2): techniques to maintain integrity (any changes to the &gt;record must be identifiable).</p>
</blockquote>
<p>(i)<strong>Operational Rules</strong>: framework governing operation of the electronic system should be geared towards the achievement of desired outcomes.</p>
<p>(ii)<strong>Data Integrity</strong>: system must incorporate techniques to protect data from tampering and external attacks.</p>
<p>(iii) <strong>Unauthorised access and use:</strong> Who is permitted to enter data and method for becoming a system user are relevant considerations, as well as vulnerabilities to internal attacks.</p>
<p>(iv) <strong>Security of hardware and software:</strong> may bring into play worker complacency.</p>
<p>(v) **Audit: system **may need to be audited prior to going live, and regularly thereafter, to check for vulnerabilities.</p>
<p>(vi)<strong>External Assessment and (vii) Industry standards</strong>: International Organisation for Standardisation (ISO) provides benchmarks against which system may be assessed: Technology-specific standards, as well as general Quality, Risk Management, Business Continuity and Security Management Standards developed by ISO may apply.</p>
<h4 id="regulatory-environment-in-the-u.s.a">Regulatory Environment in the U.S.A</h4>
<h2 id="rulebook-v.0.8.32">RuleBook v.0.8.32</h2>

<table>
<thead>
<tr>
<th align="left">Requirement</th>
<th align="left">FreightTrust</th>
<th align="left">DCOs</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">RuleBook</td>
<td align="left">Yes</td>
<td align="left">Yes</td>
</tr>
<tr>
<td align="left">Conflicts of Interest</td>
<td align="left">Yes</td>
<td align="left">Yes</td>
</tr>
<tr>
<td align="left">Novation</td>
<td align="left">Yes</td>
<td align="left">Yes</td>
</tr>
<tr>
<td align="left">Collateral (inc. margin)</td>
<td align="left">No</td>
<td align="left">Yes</td>
</tr>
<tr>
<td align="left">Netting Arrangements</td>
<td align="left">No</td>
<td align="left">Yes</td>
</tr>
<tr>
<td align="left">Dispute Resolution</td>
<td align="left">Yes</td>
<td align="left">Yes</td>
</tr>
<tr>
<td align="left">Emergency Rules</td>
<td align="left">Yes</td>
<td align="left">Yes</td>
</tr>
<tr>
<td align="left">Collateralized</td>
<td align="left">Always 100%</td>
<td align="left">up to 100%</td>
</tr>
</tbody>
</table><h3 id="authorized-representative"><strong>Authorized Representative</strong></h3>
<p>(a) Each Network Participant shall designate one or more Authorized Representatives to sign all instruments, correct errors, perform such other duties as may be required under the Rules and transact all business in connection with the operations of FreightTrust. Each Network Participant must provide FreightTrust with current contact and other requested information for each of its Authorized Representatives.</p>
<p>(b) To designate an Authorized Representative, a Network Participant must provide the information requested and conform to the procedures and requirements established by Freight Trust. By agreeing to become an Authorized Representative, an individual agrees to be bound by the duties and responsibilities of an Authorized Representative and to be subject to, and comply with, the Rules and Obligations to the extent applicable.</p>
<p>(c) Freight Trust will promptly notify a Network Participant of the approval of nominated Authorized Representatives and will maintain a list of all approved Authorized Representatives for each Network Participant. Freight Trust shall promptly notif the parties involved  if Freight Trust  (i) declines to approve the designation, (ii) revokes the designation, or (iii) suspends the designation of an Authorized Representative or/and Network Participant.</p>
<p>(d) An Authorized Representative who is suspended remains subject to the Rules and jurisdiction throughout the period of suspension.</p>
<p>(e) To request the termination of the designation of an Authorized Representative, the Network Participant or the Authorized Representative must notify Freight Trust providing the information and complying with the procedures and requirements established by Freight Trust.</p>
<p>(f) An Authorized Representative remains subject to the Rules and the jurisdiction of Freight Trust for acts done and omissions made while registered as such, and a proceeding relating to an individual whose designation as an Authorized Representative or Network Participant and has been terminated or suspended shall occur as if the Authorized Representative were still registered as such.</p>
<h2 id="dispute-resolution">Dispute Resolution</h2>
<p>All Network Participants shall be required to arbitrate all disputes between or among themselves that relate to or arise out of any transaction submitted for <em>instrumentailization</em> in accordance with this Rule Book. For these purposes, each Network Participant shall be deemed a “Participant” for purposes of the rules set forth. Disputes involving Customers may be arbitrated in accordance to policy setforth in this Rule Book.</p>
<h2 id="freight-specifics">Freight Specifics</h2>
<h3 id="brokerfreight-forwader">Broker/Freight Forwader</h3>
<pre><code>Property broker surety bond or trust fund.

(a) Security. A broker must have a surety bond or trust fund in effect for $75,000. The FMCSA will not issue a broker license until a surety bond or trust fund for the full limits of liability prescribed herein is in effect. The broker license shall remain valid or effective only as long as a surety bond or trust fund remains in effect and shall ensure the financial responsibility of the broker.

(b) Evidence of security. Evidence of a surety bond must be filed using the FMCSA's prescribed Form BMC 84. Evidence of a trust fund with a financial institution must be filed using the FMCSA's prescribed Form BMC 85. The surety bond or the trust fund shall ensure the financial responsibility of the broker by providing for payments to shippers or motor carriers if the broker fails to carry out its contracts, agreements, or arrangements for the supplying of transportation by authorized motor carriers.

(c) Financial institution—when used in this section and in forms prescribed under this section, where not otherwise distinctly expressed or manifestly incompatible with the intent thereof, shall mean—Each agent, agency, branch or office within the United States of any person, as defined by the ICC Termination Act, doing business in one or more of the capacities listed below:
</code></pre>
<p>(1) An insured bank (as defined in section 3(h) of the Federal Deposit Insurance Act (12 U.S.C. 1813(h));<br><br>
(2) A commercial bank or trust company;<br><br>
(3) An agency or branch of a foreign bank in the United States;<br><br>
(4) An insured institution (as defined in section 401(a) of the National Housing Act (12 U.S.C. 1724(a));<br><br>
(5) A thrift institution (savings bank, building and loan association, credit union, industrial bank or other);<br><br>
(6) An insurance company;<br><br>
(7) A loan or finance company; or<br><br>
(8) A person subject to supervision by any State or Federal bank supervisory authority.<br><br>
(9) Forms and Procedures<br><br>
<br><br>
(10) Forms for broker surety bonds and trust agreements. <br><br>
<br><br>
Form BMC-84 broker surety bond will be filed with the FMCSA for the full security limits under paragraph (a) of this section; or Form BMC-85 broker trust fund agreement will be filed with the FMCSA for the full security limits under paragraph (a) of this section.<br>
<br><br>
(2) Broker surety bonds and trust fund agreements in effect continuously. Surety bonds and trust fund agreements shall specify that coverage thereunder will remain in effect continuously until terminated as herein provided.<br>
<br><br>
<br> (i) Cancellation notice. The surety bond and the trust fund agreement may be cancelled as only upon 30 days’ written notice to the FMCSA, on prescribed Form BMC 36, by the principal or surety for the surety bond, and on prescribed Form BMC 85, by the trustor/broker or trustee for the trust fund agreement. The notice period commences upon the actual receipt of the notice at the FMCSA’s Washington, DC office.<br>
<br><br>
<br>(ii) Termination by replacement. Broker surety bonds or trust fund agreements which have been accepted by the FMCSA under these rules may be replaced by other surety bonds or trust fund agreements, and the liability of the retiring surety or trustee under such surety bond or trust fund agreements shall be considered as having terminated as of the effective date of the replacement surety bond or trust fund agreement. However, such termination shall not affect the liability of the surety or the trustee hereunder for the payment of any damages arising as the result of contracts, agreements or arrangements made by the broker for the supplying of transportation prior to the date such termination becomes effective.<br>
<br><br>
(3) Filing and copies. Broker surety bonds and trust fund agreements must be filed with the FMCSA in duplicate.</p>
<pre><code>
[53 FR 10396, Mar. 31, 1988, as amended at 75 FR 72998, Nov. 29, 2010; 78 FR 58482, Sept. 24, 2013; 78 FR 60233, Oct. 1, 2013]
</code></pre>
<h2 id="the-system-will-be-constructed-multiple-distinct-components">The system will be constructed multiple distinct components:</h2>
<h3 id="smart-contract">Smart Contract</h3>
<p>A BoL is in this context is an electronic document of title, meaning that a system<br>
employed for evidencing the transfer of interests in the document must also reliably<br>
establish the current owner of the document. In order to accomplish this, a smart<br>
contract on an EVM-compatible network will be utilized to implement both a reference<br>
to the document’s current owner, as well as the protocol in case of the transfer of<br>
ownership of the document.</p>
<p>This shall be accomplished through the widely-used ERC721 standard and ERC721-<br>
metadata extension. This standard shall allow parties to create, transfer, and view their<br>
existing BoLs as tokenized assets by interacting with the BoL dapp smart contracts.<br>
The ERC721 standard also provides simple transfer mechanisms that satisfy the<br>
“transfer of interests” function of an electronic document of title, as well as simple<br>
asset lookups that will establish the current owner of the BoL. The smart contracts shall<br>
provide, among other things, the entire ERC721-compliant interface to its users.<br>
The BOL smart contracts shall implement ownership transfer through a<br>
function with enables transfer through the use of ECDSA signatures. This function shall<br>
use the EVM opcode ecrecover to determine the signer of messages sent to it,<br>
determining the intent of the current owner to transfer rights and responsibility to some<br>
recipient. This ownership transfer mechanism is in addition to the ownership transfer<br>
mechanism described in the ERC721 standard. </p>
<p>Additional considerations are fully considered in devloping and designing the solution set for the protocol. Specifically in the ways that the software will interact and respond when performing out-of-scope (“crashing/failing”):</p>
<pre><code>• Smart contracts may depend on other systems to fulfill contract terms. These other systems may
have vulnerabilities that could prevent the smart contract from functioning as intended.

• Some smart contract platforms may be missing critical system safeguards and customer
protections.

• Where smart contracts are linked to a blockchain, forks in the chain could create operational
problems.

• In case of an operational failure, recourse may be limited or non-existent – complete loss of a
virtual asset is possible.

• Poor governance. Smart contracts may require attention, action, and possible revision subject to
appropriate governance and liability mechanisms.
</code></pre>
<p>The  BOL Protocol shall implement a token creation function, named a designated trading facility, which allows token creation by providing an ECDSA signature, IPFS file hash/Other Distributed File Systems and intended recipient to the contracts. The ECDSA signature will sign the IPFS or other file hash and intended recipient, as well as a nonce to guarantee uniqueness. Constructs of the contract, called <strong>optionality</strong> enables additional functionality to be integrated programtically into the protocol at an ‘atomic’ level. It should be noted that for cross-border transactions there is a second component involved, a Instutionally offerd ‘Lex as a Service’, i.e. a legal regime for arbitration and adjuidication in which a designated couterparty is also party to transactions to ensure a reliable and deterministic business logic to transaction disputes.</p>
<p>Additionally, the smart contracts shall implement upgradability mechanisms adhering to<br>
the widely-used proxy library contract abstraction. This abstraction shall expose the<br>
entirety of the ERC721 interface through a smaller proxy contract, as well as several<br>
administrative functions. The proxy contract shall act as a simple call forwarder, and<br>
will delegate all execution to the appropriate implementing contract. The administrative<br>
functions included shall allow a privileged user (in this case, a party chosen by Block</p>
<p>The BoL shall be created as a digital document of title, and should include the fields and<br>
properties typically associated with bills of lading. This specification is out of the scope<br>
of this document, but typically includes (among other things): a cargo manifest, a<br>
unique ID, identifying information on the shipper and carrier, information on the origin<br>
and destination of the cargo, and more. The BoL shall be represented as a PDF, XML, or<br>
other widely-used document format.</p>
<p>The BOL shall be created by the carrier through some web interface, and presented to<br>
the shipper. The shipper will provide an ECDSA signature of the document, carrier’s<br>
identity, and shipper’s nonce to the carrier, signifying their intent to transfer ownership<br>
and responsibility of the BoL and associated cargo to the carrier for the purpose of the<br>
shipment of the cargo. The document shall be stored in fault-tolerant storage, and a hash of the document provided to the shipper as a receipt, along with any other contractual obligations required. Both the shipper and carrier should be<br>
able to use this hash to query the IPFS network and receive the BoL in return.<br>
The hash of the document along with the aforementioned ECDSA signature shall be<br>
submitted to the BoL dapp smart contracts in order to mint a unique BoL token to the<br>
carrier. This token will serve as a record of the ownership of the BoL.</p>
<blockquote>
<p>Note: In the United States of America the Federal Bills of Lading Act provides that a common<br>
carrier issuing a nonnegotiable bill of lading must put “nonnegotiable” or “not negotiable” on the bill, although this requirement does not apply to an informal memorandum or acknowledgmentA bill of lading as ordinarily issued is signed by the carrier only and it need not be signed by the shipper. Its terms and conditions are binding even though the bill is unsigned by the shipper, the signing of the bill only making it easier to prove the shipper was fully informed of its terms and assented thereto. In the case of goods received for transportation by rail or other land carriage, the bill of lading may be signed by the agent of the carrier who has authority to receipt for freight and to contract for its transportation</p>
</blockquote>
<p>.</p>
<h4 id="assigning-a-bol-to-a-driver">Assigning a BOL to a Driver</h4>
<p>The BoL shall be assigned by the carrier to a driver for the purpose of the shipment of<br>
the cargo. The ownership transfer shall occur either through the standard ERC721<br>
ownership transfer function, or through a specialized transfer function which, like the<br>
token creation function, requires the carrier to provide an ECDSA signature of the IPFS<br>
file hash, driver identity, and carrier nonce.</p>
<blockquote>
<p>Since a bill of lading acknowledges the receipt of goods for carriage, the delivery of the goods to the carrier should precede the execution of the bill, and the agent of a transportation company does not have the right to sign bills of lading until the goods have been actually delivered into the possession of the company. In practice, however, the delivery of the goods to be shipped and the delivery of a bill of lading for such goods are regarded as simultaneous acts. With respect to a private contract of carriage, the bills of lading are not required to describe the condition of the goods.</p>
</blockquote>
<p>Delivering a BoL and Associated Cargo<br>
The BoL shall be transferred to the recipient by the driver along with the delivered cargo.<br>
The ownership transfer shall occur either through the standard ERC721 ownership<br>
transfer function, or through a specialized transfer function which, like the token<br>
creation function, requires the driver to provide an ECDSA signature of the IPFS file<br>
hash, shipper identity, and driver nonce.</p>
<h3 id="design-rationale">Design Rationale</h3>
<p><strong>Efficiency</strong><br><br>
The considerations made when designing the system’s architecture were primarily<br>
efficiency-based, sacrificing having the entire implementation in EVM smart contracts<br>
for a more resilient system based on IPFS. The architecture allows parties involved in<br>
the creation of, use of, and management of BoL documents to access them through the<br>
worldwide IPFS network, as well as ensure that the documents they received are valid<br>
through the EVM-compatible network.</p>
<p><strong>Flexibility</strong><br><br>
The system is additionally designed with flexibility in mind. By allowing Block Array to<br>
manage implementations on-chain, the system is able to ensure it is well-defined, but<br>
malleable. Technical standards change often, especially in a growing industry: this<br>
architecture keeps on-chain information to a minimum, choosing instead to implement<br>
a protocol on-chain and keep important information in IPFS.</p>
<p><strong>Ease of Use</strong><br><br>
The system can easily be designed to maximize simplicity of use for interested parties.<br>
The signature and submission mechanisms can be implemented simply and safely<br>
using MetaMask and a web interface. By ensuring BoLs use widely-used document<br>
formats, the BoL can also be presented as a print document (or viewed in digital form).<br>
By implementing the ECDSA-signature ownership transfer mechanism, the interested<br>
parties do not need to interact with the EVM-compatible network. Instead, a third party<br>
can submit these requests for them, eliminating the requirement for all parties involved<br>
to own Ether (or a similar cryptocurrency). Together, these elements can create a<br>
system that is secure, reliable, and transparent: without the involved parties being aware<br>
of its existence.</p>
<h2 id="v.2.0.5">v.2.0.5</h2>
<p>Contract Instrument Semi-NFT</p>

<table>
<thead>
<tr>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">ERC1400</td>
<td align="left">v2</td>
</tr>
<tr>
<td align="left">ERC1643 Document Managment</td>
<td align="left">v2</td>
</tr>
<tr>
<td align="left">ERC1154</td>
<td align="left">v1</td>
</tr>
<tr>
<td align="left">EIP 1077: Executable Signed Messages</td>
<td align="left">v1</td>
</tr>
<tr>
<td align="left">EIP 1775</td>
<td align="left">v2</td>
</tr>
<tr>
<td align="left">“Atlas” Kernel</td>
<td align="left">v2</td>
</tr>
<tr>
<td align="left">ECANS</td>
<td align="left">Yes</td>
</tr>
</tbody>
</table><p><strong>ERC777 implementation - Advanced token standard for asset transfers</strong></p>
<ul>
<li>Empowerment of operators with the ability to send tokens on behalf of other addresses.</li>
<li>Setup of send/receive hooks to offer token holders more control over their tokens.</li>
<li>Use of ER820(<a href="http://eips.ethereum.org/EIPS/eip-820">eips.ethereum.org/EIPS/eip-820</a>) to notify contracts and regular addresses when they receive tokens.</li>
<li>Backwards compatible with ERC20.</li>
</ul>
<p><strong>ERC1400 implementation - Partially fungible token standard</strong></p>
<ul>
<li>Differentiated ownership / transparent restrictions.</li>
<li>Controller operations (force transfer).</li>
<li>On-chain restriction checking with error signalling, off-chain data injection for transfer restrictions and issuance / redemption semantics.</li>
<li>Document management.</li>
<li>Backwards compatible with ERC20 and ERC777.</li>
</ul>
<p><strong>Ethereum Registration Authority / Trusted Certificate Authority</strong></p>
<pre><code>Data Field for Signature Injection &lt;Triggering_Event&gt;

function transferWithData(address recipient, uint256 value, bytes data)
</code></pre>
<p><strong>ERC1643 implementation</strong></p>
<p>AddressID specifices which package is used for that operation/interogatives and subordinate clauses</p>
<p>Enables Agreement to be as homogonized or unique as needed, thereby extending possiblity of liquidity for layer 2+ applications.<br>
<br></p>
<h2 id="definitions-and-specifications">Definitions and Specifications</h2>
<br>
a **registry** is a deployed contract which manages a collection of packages.
<p>a <strong>package</strong> is a collection of releases</p>
<p>a <strong>package</strong> is identified by a unique string name and unique bytes32 packageId within a given registry</p>
<p>a** release** is identified by a bytes32 releaseId which must be unique for a given package name and release version string pair.</p>
<p>a** releaseId **maps to a set of data that includes a manifestURI string which describes the location of an EIP 1123 package manifest. This manifest contains data about the release including the location of its component code assets.</p>
<p>a <strong>manifestURI</strong> is a URI as defined by RFC3986 which can be used to retrieve the contents of the package manifest. In addition to validation against RFC3986, each manifestURI must also contain a hash of the content as specified in the EIP 1123.</p>
<p>a l<strong>ibrary</strong> is a staticc set of standard contracts like SafeMath. **libsol **is the authoratative library.</p>
<p>the <strong>Kernel</strong> compromises interlocking contracts that execute operations by invocation or trigger</p>
<pre><code>Registry -&gt; Package [libsol, kernel...] -&gt; Release [specific contract updates] -&gt; latest release
</code></pre>
<p><strong>Stand Alone:</strong>    Package has no external dependencies (i.e. no build_dependencies), contains all contract data needed without reaching into another package.</p>
<p>**Dependent:   ** Package does not contain all necessary contract data (i.e. has build_dependencies), must reach into a package dependency to retrieve data.</p>
<p><strong>Inheritable</strong>:    Contract doesn’t provide useful functionality on it’s own and is meant to serve as a base contract for others to inherit from.</p>
<p>**Reusable: **   Contract is useful on it’s own, meant to be used as-is. This applies only to kernel level contracts.</p>
<p><strong>Deployed Contract/Library:</strong></p>
<pre><code> Refers to an instance of a contract/library that has already been deployed to a specific address on a chain.
</code></pre>
<p><strong>Package Dependency:</strong></p>
<pre><code> External dependency directly referenced via the build\_dependencies of the package.
</code></pre>
<p><strong>Deep Dependency:</strong></p>
<pre><code> External dependency referenced via the build\_dependencies of a package dependency 
 (or by reaching down dependency tree as far as necessary\).
</code></pre>

<table>
<thead>
<tr>
<th align="left">&lt;/&gt;</th>
<th align="left">Action</th>
</tr>
</thead>
<tbody>
<tr>
<td align="left">defaultOperator</td>
<td align="left">Freight Trust, _Network Operations _</td>
</tr>
<tr>
<td align="left">AuthorizedOperator</td>
<td align="left">3rd Party (e.g. Invoice Factoring, Insurance, etc)</td>
</tr>
<tr>
<td align="left">RevokedOperator</td>
<td align="left">Default: 0</td>
</tr>
<tr>
<td align="left">setManager</td>
<td align="left">Deployed On-Contracts, <em>Network Operations</em></td>
</tr>
<tr>
<td align="left">getAttributeTypeID</td>
<td align="left">interger</td>
</tr>
<tr>
<td align="left">hasAttribute</td>
<td align="left">string</td>
</tr>
<tr>
<td align="left">symbol</td>
<td align="left">Self Describing Contract Parameters</td>
</tr>
<tr>
<td align="left">documentationIdentification</td>
<td align="left">&lt;string_prefix]little einden</td>
</tr>
</tbody>
</table><p>| legalAgreement | … |<br>
| masterAgreement | … |<br>
| tradeAgreement | . |<br>
| uniqueAgreement | . |<br>
| effectiveDate | . |<br>
| eventDate | . |<br>
| eventQualifier | . |<br>
| eventIdentifier | . |<br>
| lineage | . |<br>
| contractKeyUID | . |<br>
|  |  |</p>
<p>Object	Description<br>
event_time	The exact time (UNIX time stamp) the event occurred.<br>
event_type	The type of event that occurred.<br>
event_hash	The unique hash of the event that occurred.<br>
meta.related_document_hash	The unique document hash this event is associated with.<br>
meta.related_user_id	The user identification this event is associated with. (Sender User ID)<br>
meta.related_business_id	The business ID this event is associated with. (Sender Business ID)<br>
meta.related_app_id	If this event is sent as part of a webhook notification for a specific app, this will contain the associated App ID.<br>
<a href="http://signer.id">signer.id</a>	The signer ID this event is associated with.<br>
<a href="http://signer.name">signer.name</a>	The name of the signer this event is associated with.<br>
signer.email	The email address of the signer this event is associated with.<br>
signer.role	The role of the signer this event is associated with. (Templates only)<br>
signer.order	The signer order sequence number of the signer this event is associated with.</p>
<br>
<p>======================</p>
<pre><code>No Claim to Orig. U.S. Govt. Works. &lt;br&gt;
Caselaw provided by Thomson Reuters. 33-34B © 2019 All rights reserved.

No Claim to Orig. Ethereum Improvement Proposals &lt;br&gt;
Ethereum.org 
</code></pre>
<pre><code>Protocol Contracts and Platform Applications audited and secured by Authio.
Alexander Wade, Authio.org 
&lt;br&gt;
Specifications, Design and Legal implemented by FreightTrust.
Sam Bacha, Freight Trust &amp; Clearing Corporation.
</code></pre>
<br>
Clients
<p>Extentions</p>
<p>Resources</p>
<p>Links</p>
<p>API for Applications</p>
<p>WebSocket</p>
<p>JSON-RPC</p>
<p>ABI for Contract Library</p>
<p>ABI for In-Protocol Library</p>
<p>Metatransactions</p>
<p>OPCODES</p>
<p>Additional OPCODES</p>
<pre><code>(c) 2019 - Freight Trust &amp; Clearing Corp. (CC-3)
</code></pre>
<br>
<br>
## teeDai 
*Trusted Execution Environment (inter)side (change)chain*
<h5 id="creating-the-sterlingos">Creating the SterlingOS</h5>
<p><em>a performant &amp; scalable bare metal configuration for Intel x86 SGX1 clustering</em></p>
<p>Hardware working on:</p>
<p>PowerEdge R230 BiOS 2.4+ 1270 R230 Xeon</p>
<p>Currently SGX1 coverage, as no cloud provider has SGX2 out-of-the-box + bios support.</p>
<p>Base Distro<br>
RHEL/CentOS 7.5</p>
<p>requires <a href="https://github.com/mesalock-linux">https://github.com/mesalock-linux</a></p>
<br>
####  ⛔️ End User Notice ⛔️ 
<p>Adjusting these settings can result in an unstable system.</p>
<h6 id="these-are-root-only-and-assumes-root-knows-what-they-are-doing."><strong>These are root only and assumes root knows what they are doing.</strong></h6>
<p>⚠️ very small values in sched_rt_period_us can result in an unstable<br>
system when the period is smaller than either the available hrtimer<br>
resolution, or the time it takes to handle the budget refresh itself.</p>
<p>⚠️ very small values in sched_rt_runtime_us can result in an unstable<br>
system when the runtime is so small the system has difficulty making<br>
forward progress (NOTE: the migration thread and kstopmachine both<br>
are real-time processes).</p>
<p>Realtime scheduling is all about determinism, a group has to be able to rely on<br>
the amount of bandwidth (eg. CPU time) being constant. In order to schedule<br>
multiple groups of realtime tasks, each group must be assigned a fixed portion<br>
of the CPU time available.</p>
<h4 id="network-wide-settings">Network Wide Settings</h4>
<h3 id="system-wide-settings--procedure">System wide settings &amp; procedure</h3>
<hr>
<p>Make sure you have</p>
<p><a href="https://github.com/ayeks/SGX-hardware">SGX Hardware Support</a></p>
<p><a href="https://ark.intel.com/content/www/us/en/ark.html">Intel Product Specifications check to see if your specific make supports</a></p>
<p><code>&gt; Intel SGX driver installed and /dev/isgx works</code></p>
<p><code>&gt; gdb 7.11.1</code></p>
<h5 id="development-libraries-needed">Development libraries needed:</h5>
<pre><code>$ yum install 
		libcgroup 
        libcgroup-tools 
        libcurl4-openssl-dev 
    	libssl-dev`
</code></pre>
<pre><code>[baiduxlabs/sgx-rust](https://hub.docker.com/r/baiduxlab/sgx-rust) 

</code></pre>
<pre><code>#!/bin/sh

# Error out on undefined variables to catch typos or other errors such as env
# vars not being defined when you expected it (not enough systems do this!)
set -u

# exec replaces the process; prevents needless /bin/sh from dangling around.
exec prog \
    -a "$A"          `# Always include A from environment, error out if unset`  \
    -b "${B:-d}"     `# Include B from environment, use "d" if unset` \
    "${C:+-c "$C"}"  `# Only pass -c $C if $C is set, pass nothing at all if unset` \
    "$@"             `# Include all argument passed to the shell script`

</code></pre>
<p>⛔️ <strong>rustup</strong> for install, <strong>MUST NOT</strong> use package managers, i.e. yum, rpm, apt</p>
<br>
<p>The system wide settings are configured under the /proc virtual file system:</p>
<p>/proc/sys/kernel/sched_rt_period_us:<br>
The scheduling period that is equivalent to 100% CPU bandwidth</p>
<p>/proc/sys/kernel/sched_rt_runtime_us:<br>
A global limit on how much time realtime scheduling may use.  Even without<br>
CONFIG_RT_GROUP_SCHED enabled, this will limit time reserved to realtime<br>
processes. With CONFIG_RT_GROUP_SCHED it signifies the total bandwidth<br>
available to all realtime groups.</p>
<ul>
<li>Time is specified in us because the interface is s32. This gives an<br>
operating range from 1us to about 35 minutes.</li>
<li>sched_rt_period_us takes values from 1 to INT_MAX.</li>
<li>sched_rt_runtime_us takes values from -1 to (INT_MAX - 1).</li>
<li>A run time of -1 specifies runtime == period, ie. no limit.</li>
</ul>
<h5 id="disable-irqbalance-daemon">Disable “irqbalance daemon”</h5>
<p>procedure<br>
<br></p>
<pre><code>$ service irqbalance status
&gt; irqbalance (pid PID) is running...
</code></pre>
<p><strong>if irqbalance daemon is running, disable…</strong></p>
<pre><code>$ service irqbalance stop
&gt; Stopping irqbalance: [ OK ]
</code></pre>
<p>Use chkconfig to ensure that irqbalance does not restart on boot.</p>
<pre><code>$ chkconfig irqbalance off
</code></pre>
<h4 id="binding-processes-to-cpus-using-the-taskset-utility">Binding Processes to CPUs using the taskset utility</h4>
<p>&lt; backlog &gt;</p>
<h4 id="determinstic-filesystem">Determinstic Filesystem</h4>

<p>Disabling atime,<br>
Configuring tmpwatch [tmpwatch controls how often /tmp is cleaned out]</p>
<pre><code>**wio needs further verification**
</code></pre>
<p>🚧 Construction Zone 🚧</p>
<h4 id="hardware-clock-system-timestamping-suprasynchron">Hardware clock system timestamping (suprasynchron)</h4>
<blockquote>
<p>Procedure Verified</p>
</blockquote>
<p>Multiprocessor systems such as NUMA or SMP have multiple instances of hardware clocks. During boot<br>
time the kernel discovers the available clock sources and selects one to use. For the list of the available<br>
clock sources in your system, view the</p>
<blockquote>
<p>/sys/devices/system/clocksource/clocksource0/available_clocksource file:</p>
</blockquote>
<pre><code># cat /sys/devices/system/clocksource/clocksource0/available_clocksource
tsc hpet acpi_pm

</code></pre>
<ul>
<li>The clock source currently in use can be inspected by reading the</li>
</ul>
<blockquote>
<p>/sys/devices/system/clocksource/clocksource0/current_clocksource file:</p>
</blockquote>
<pre><code># cat /sys/devices/system/clocksource/clocksource0/current_clocksource
tsc

</code></pre>
<h6 id="suprasynchron---defining-hardware-clocksource-for-consistantcy-of-block-time-and-real-time">“suprasynchron” - defining hardware clocksource for consistantcy of block-time and real-time</h6>
<p>Select clock source from list given by:</p>
<blockquote>
<p>/sys/devices/system/clocksource/clocksource0/available_clocksource file</p>
</blockquote>
<p>Must choose <strong>HPET</strong></p>
<pre><code>$ echo hpet &gt; /sys/devices/system/clocksource/clocksource0/current_clocksource


</code></pre>
<h5 id="sgx-driver">SGX Driver</h5>
<pre><code>$ curl --output /tmp/driver.bin https://download.01.org/intel-sgx/linux-2.3.1/ubuntu18.04/sgx_linux_x64_driver_4d69b9c.bin
/usr/bin/env bash /tmp/driver.bin
depmod
modprobe isgx
</code></pre>
<p>verify install: <code>dmesg</code> should show <code>Intel SGX Driver v0.11</code> install was successful</p>
<h5 id="configure-libsecp256k">configure libsecp256k</h5>
<p>configure the libsecp256k1 library by going into</p>
<pre><code>$ cd src/trusted/libs/


</code></pre>
<ul>
<li>aesmd daemon</li>
</ul>
<pre><code>$ docker run --rm -it -v /run/aesmd:/run/aesmd --device /dev/isgx &lt;AWS ECR LINK&gt;
</code></pre>
<h4 id="building-client">Building Client</h4>
<p>(I)   Protocol<br>
(II)  Servlet<br>
(III) Enclavelet</p>

<p>Notes:<br>
Maven pom.xml config</p>
<p>define JVM configuration via ${maven.projectBasedir}/.mvn/jvm.config</p>
<p>-Xmx2048m -Xms1024m -XX:MaxPermSize=512m -Djava.awt.headless=true</p>
<p>Maven pom.xml</p>
<p>MAVEN_OPTS=-XX:MaxRAM=3572m -Xmx1g<br>
-XX:MaxRAM=3572m -Xmx8g</p>
<h1 id="sources--datasets">Sources &amp; Datasets</h1>
<br>
Sources:
	Section, Topic, Author 
Tools:
<p>Tiago P. Peixoto, <strong>“The graph-tool python library”</strong>, figshare. (2014) DOI: 10.6084/m9.figshare.1164194 [sci-hub, @tor]</p>
<p>**High Throughput Byzantine Fault Tolerance. DSN’04.<br>
**<br>
Ramakrishna Kotla and Mike Dahlin.</p>
<p><strong>Monoxide: Scale out Blockchains with Asynchronous Consensus Zones. NSDI’19</strong><br>
Wang, Jiaping, and Hao Wang.</p>
<p><strong>Untangling blockchain: A data processing view of blockchain systems. TKDE’17</strong><br>
Dinh, Tien Tuan Anh, et al.</p>
<p><strong>Blockchains from a distributed computing perspective. Communications of the ACM</strong><br>
Maurice Herlihy</p>
<p><strong>Tan: BlockBench: A Framework for Analyzing Private Blockchains. SIGMOD’17</strong><br>
T. Dinh, J. Wang, G. Chen, R. Liu, B. Chin Ooi, K.-L.</p>
<p><strong>Achieving One Billion Key-Value Requests per Second on a Single Server. IEEE Micro’16</strong><br>
Sheng Li, Hyeontaek Lim, Victor W. Lee, Jung Ho Ahn, Anuj Kalia, Michael Kaminsky, David G. Andersen, Seongil O, Sukhan Lee, Pradeep Dubey.</p>
<p>**DARE: High-Performance State Machine Replication on RDMA Networks HPDC’15<br>
**<br>
Marius Poke, Torsten Hoefler.</p>
<p><strong>Fast and general distributed transactions using RDMA and HTM. EuroSys’16</strong><br>
Yanzhe Chen, Xingda Wei, Jiaxin Shi, Rong Chen, Haibo Chen.</p>
<p><strong>Research for practice: distributed consensus and implications of NVM on database management systems. Commun. ACM’16</strong><br>
Peter Bailis, Joy Arulraj, and Andrew Pavlo.</p>
<p><strong>Consensus in a Box: Inexpensive Coordination in Hardware  NSDI’16</strong><br>
Zsolt István, David Sidler, and Gustavo Alonso, Marko Vukolić.</p>
<p>Special Thanks:<br>
I. Barinov <strong>BlockNotary</strong> , <strong>POA: Proof of Authority &amp; Aura Concensus</strong><br>
B. Mcelrarth <strong>BRaided Blockchains: Braidcoin</strong><br>
G. Wood. <strong>Ethereum: A secure decentralised generalised transaction ledger</strong><br>
S. Nakamoto. <strong>Bitcoin: A peer-to-peer electronic cash system. 2008</strong></p>
<hr>
<p>Glossary</p>
<hr>
<p><strong>Ammendment</strong> means a change to a document/smart contract. <em>see Endorsement</em></p>
<ul>
<li>
<p>Bill of Lading (“BoL”)<br>
A bill of lading is, in this context, an electronic document of title presented to a shipper<br>
by a carrier as a receipt for some agreement to carry cargo from one location to<br>
another.</p>
</li>
<li>
<p>Carrier<br>
A carrier is a party approached by a shipper to transfer some cargo on their behalf. The<br>
carrier presents the shipper with a BoL as a digital agreement under which the<br>
transaction will be carried out. The carrier assigns some driver to deliver the cargo.</p>
</li>
<li>
<p>Decentralized Application (“dapp”)<br>
A decentralized application is an application which runs primarily (or solely) on a<br>
network comprised of many computers, none of which have ultimate permissions over<br>
the entirety of the system.</p>
</li>
<li>
<p>Driver<br>
A driver operates under some carrier, and delivers cargo as per the terms of the BoL<br>
agreed upon by the carrier and shipper. The driver is responsible for the safe delivery of<br>
the cargo, and receives the BoL prior to delivery of the cargo. Upon delivery of the cargo,<br>
the driver receives the signature of the shipper as proof of successful delivery</p>
</li>
<li>
<p>Elliptic Curve Digital Signature Algorithm (“ECDSA”)<br>
ECDSA is an elliptic curve signature algorithm which allows parties to generate digital<br>
signatures which can be verified to be unique, to consist of some data, and to belong to<br>
the identity used to sign the data.</p>
</li>
<li>
<p>Ethereum Virtual Machine (“EVM”)<br>
The Ethereum Virtual Machine is a general-purpose virtual machine which runs on<br>
distributed blockchain networks. The EVM supports many simple instructions which<br>
operate on 256-bit values.</p>
</li>
<li>
<p>Electronic Document of Title<br>
An electronic document of title is issued by an individual who has custody of some<br>
goods (in this case, cargo to be shipped) to an individual who has entrusted the<br>
previous party with the goods.</p>
</li>
</ul>
<p><strong>Endorsement</strong> (a) means an amendment to an insurance policy. (b) a change to end user, cosignee or receiving party for a negotible instrument.</p>
<p><strong>Environmental restoration</strong> means restitution for the loss, damage, or destruction of natural resources arising out of the accidental discharge, dispersal, release or escape into or upon the land, atmosphere, watercourse, or body of water of any commodity transported by a motor carrier. This shall include the cost of removal and the cost of necessary measure taken to minimize or mitigate damage to human health, the natural environment, fish, shellfish, and wildlife.</p>
<ul>
<li>ERC721 Standard<br>
The ERC721 standard is a standard interface used by EVM smart contracts to define a<br>
general implementation and interface for tokenization of unique digital assets. In this<br>
case, the ERC721 standard acts as the method by which BoL ownership is recorded and<br>
transferred from party to party.</li>
</ul>
<p><strong>Evidence of security</strong> means a surety bond or a policy of insurance with the appropriate endorsement attached.</p>
<p>**Financial responsibility **means the financial reserves (e.g., insurance policies or surety bonds) sufficient to satisfy liability amounts set forth in this subpart covering public liability.</p>
<p>**For-hire carriage **means the business of transporting, for compensation, the goods or property of another.<br>
In bulk means the transportation, as cargo, of property, except Division 1.1, 1.2, or 1.3 materials, and Division 2.3, Hazard Zone A gases, in containment systems with capacities in excess of 3500 water gallons.<br>
In bulk (Division 1.1, 1.2, and 1.3 explosives) means the transportation, as cargo, of any Division 1.1, 1.2, or 1.3 materials in any quantity.<br>
In bulk (Division 2.3, Hazard Zone A or Division 6.1, Packing Group I, Hazard Zone A materials) means the transportation, as cargo, of any Division 2.3, Hazard Zone A, or Division 6.1, packing Group I, Hazard Zone A material, in any quantity.<br>
Insured and principal means the motor carrier named in the policy of insurance, surety bond, endorsement, or notice of cancellation, and also the fiduciary of such motor carrier.</p>
<p>**Insurance premium **means the monetary sum an insured pays an insurer for acceptance of liability for public liability claims made against the insured.</p>
<p><strong>Motor carrier</strong> means a for-hire motor carrier or a private motor carrier. The term includes, but is not limited to, a motor carrier’s agent, officer, or representative; an employee responsible for hiring, supervising, training, assigning, or dispatching a driver; or an employee concerned with the installation, inspection, and maintenance of motor vehicle equipment and/or accessories.</p>
<ul>
<li>
<p>Nonce<br>
A nonce is a simple data structure used to ensure transactions and signatures which<br>
may be of the same (or similar data) are unique. In the system described below, each<br>
party (shipper, carrier, driver) has unique nonces, which ensure their signatures are<br>
unique to the BoL in question.</p>
</li>
<li>
<p>Proxy Library Abstraction<br>
A proxy library abstraction is a design pattern for EVM-based smart contracts which<br>
enables the maximum flexibility for implementing applications. The abstraction<br>
presents an interface to the user through which functions in the application are<br>
executed. This interface is a proxy, meaning that it delegates execution to some other<br>
smart contract, ensuring implementation can be changed if needed.</p>
</li>
</ul>

<table>
<thead>
<tr>
<th align="left"><strong>Payment instrument</strong> means any electronic or written check, draft, money order, traveler’s check or other electronic or written instrument or order for transmitting or paying money, sold or issued to one or more persons, whether or not the instrument is negotiable. Payment instrument does not include any credit card voucher, any letter of credit or any instrument that is redeemable by the issuer in goods or services.</th>
</tr>
</thead>
<tbody></tbody>
</table><p>**Property damage **means damage to or loss of use of tangible property.<br>
Public liability means liability for bodily injury or property damage and includes liability for environmental restoration.<br>
State means a State of the United States, the District of Columbia, Puerto Rico, the Virgin Islands, American Samoa, Guam, and the Northern Mariana Islands.Cancellation of insurance means the withdrawal of insurance coverage by either the insurer or the insured.</p>

<table>
<thead>
<tr>
<th align="left"><strong>Stored value.</strong>–Monetary value representing a claim against the issuer that is stored on an electronic or digital medium and is evidenced by an electronic or digital record, and that is intended and accepted for use as a means of redemption for money or monetary value or payment for goods or services. The term does not include stored value that is redeemable by the issuer exclusively in goods or services; stored value that is redeemable exclusively in goods or services limited to transactions involving a defined merchant or location or set of locations, such as a specific retailer or retail chain, college campus, or subway system; or program points, miles, or other units issued in connection with a customer affinity or rewards program, even if there</th>
</tr>
</thead>
<tbody></tbody>
</table><ul>
<li>Shipper<br>
A shipper is a party with some cargo approaches a carrier to deliver the cargo from one<br>
location to another. The shipper and the carrier reach an agreement about the details of<br>
the delivered cargo, and produce a BoL as a receipt to the shipper.</li>
</ul>
<hr>
<blockquote>
<p>© <a href="https://freighttrust.com/">freight trust &amp; clearing corporation</a><br>
licensed under bsd-3 clause &amp; other open source licenses.</p>
</blockquote>
<hr>

    </div>
  </div>
</body>

</html>
