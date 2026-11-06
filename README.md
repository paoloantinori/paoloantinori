### Ciao, I'm Paolo Antinori 👋

Engineering manager at IBM, based in Italy. I grew up in the JVM and distributed-systems world and never really left; I just kept expanding the definition of "system" until it included Zigbee bulbs, travel routers, patent portals, and one robot with a Discord account. Managing engineers pays the bills; the patches below keep my hands honest.

I hold a growing pile of patents across cloud, security, automotive, developer tooling and, apparently, **quantum** ([receipts on Google Scholar](https://scholar.google.com/citations?user=5z4ffFEAAAAJ&hl=en)), which is the paperwork you get for writing down every *"wait, that's broken"* you trip over.

There is more paper behind that: Java certifications from the Sun Microsystems era, Red Hat certifications, a MongoDB course, and one about the weird parts of JavaScript. [LinkedIn](https://www.linkedin.com/in/paoloantinori/) keeps the details.

The rest of this page is **receipts**.

## Shipped, not just pushed

The work that means the most to me is software strangers run on their own devices:

- **Anti-Vocale** ([repo](https://github.com/RisorseArtificiali/anti-vocale), [F-Droid](https://f-droid.org/packages/com.antivocale.app/), [Google Play](https://play.google.com/store/apps/details?id=com.antivocale.app)): an Android app that transcribes voice messages **entirely on-device**; no internet, no subscription, any language the installed models cover. It exists because WhatsApp, Telegram and Signal each refuse this in their own way. The multilingual model zoo behind it (24 quantized ONNX ASR models, from Italian whisper to streaming Nemotron) lives on [my Hugging Face](https://huggingface.co/pantinor), and **reproducible builds** ship via my [fdroiddata mirror](https://github.com/paoloantinori/fdroid-data-mirror).
- [hhighlighter](https://github.com/paoloantinori/hhighlighter): a tiny shell tool to highlight terms on the command line. Still my most-starred repo, which proves the universe has strong opinions about effort versus impact.
- [jellyfin-alexa-plugin](https://github.com/paoloantinori/jellyfin-alexa-plugin): **self-hosted Alexa voice control** for my Jellyfin media server (upstream by [infinityofspace](https://github.com/infinityofspace/jellyfin-alexa-plugin); mine is the patched fork, next to a patched [trakt plugin](https://github.com/paoloantinori/jellyfin-plugin-trakt)).

## Paying the upstream tax

Honestly, the work I'm proudest of often lives in somebody else's repository. A repo of my own is a weekend; a **correct two-line patch in a compiler I depend on** is a covenant. In the last two years alone that added up to hundreds of pull requests across dozens of projects that aren't mine ([see them all](https://github.com/search?q=author%3Apaoloantinori+type%3Apr+-user%3Apaoloantinori&type=pullrequests)), up and down the whole stack I stand on:

- **Compilers and compute**: fixes to the OpenCL-on-Vulkan compiler [google/clspv](https://github.com/google/clspv/pull/1660) ([and friends](https://github.com/google/clspv/pull/1663)) and to the [kpet/clvk](https://github.com/kpet/clvk) loader, because my hashcat rig refused to run at full speed without them.
- **The agent stack**: [Hermes](https://github.com/NousResearch/hermes-agent), the **agent framework** my personal fleet runs on ([my patches](https://github.com/search?q=repo%3ANousResearch%2Fhermes-agent+author%3Apaoloantinori&type=pullrequests)); [ccgram](https://github.com/alexei-led/ccgram), the **Telegram bridge** those agents answer through; **fail-loud** contracts in [mnemosyne](https://github.com/mnemosyne-oss/mnemosyne/pull/521), their memory layer; [Lince](https://github.com/RisorseArtificiali/lince), the coding environment this very workstation runs in; [Backlog.md](https://github.com/MrLesk/Backlog.md); and [pqc-analyzer](https://github.com/oscerd/pqc-analyzer), a coding-agent skill that audits code for **post-quantum readiness**.
- **Voice**: [VoiceStudio](https://github.com/debpalash/VoiceStudio), the open source **local answer to ElevenLabs** ([my patches](https://github.com/search?q=repo%3Adebpalash%2FVoiceStudio+author%3Apaoloantinori&type=pullrequests)), fed by my [OmniVoice-Studio](https://github.com/paoloantinori/OmniVoice-Studio) fork; ASR fixes in [k2-fsa/sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx/pull/3965); a patch to kyutai's [pocket-tts](https://github.com/kyutai-labs/pocket-tts).
- **Fault injection and the JVM**: [pyteman](https://github.com/RisorseArtificiali/pyteman), **rule-based runtime fault injection** for Python and my biggest upstream destination outside the day job ([the evidence](https://github.com/search?q=repo%3ARisorseArtificiali%2Fpyteman+author%3Apaoloantinori&type=pullrequests)); its spiritual ancestor [Byteman](https://github.com/bytemanproject/byteman); [scalpel](https://github.com/maveniverse/scalpel) and [modernizer](https://github.com/gaul/modernizer-maven-plugin) on the build side.
- **WiFi drivers and firmware**: monitor-mode fixes for MediaTek radios in [openwrt/mt76](https://github.com/openwrt/mt76/pull/1162) and null-safety in [openwrt/openwrt](https://github.com/openwrt/openwrt/pull/26004) wifi-scripts; the LEDVANCE Smart+ bulb revision I had reverse engineered added to [OpenBeken](https://github.com/OpenBekenIOT/webapp/pull/312), plus behavior docs for [OpenBK7231T_App](https://github.com/openshwprojects/OpenBK7231T_App).
- **Home and hardware stack**: [Home Assistant's Thread border router](https://github.com/home-assistant/app-openthread-border-router), [ha-smartthinq-sensors](https://github.com/ollo69/ha-smartthinq-sensors), [zigbee2mqtt docs](https://github.com/Koenkk/zigbee2mqtt.io), [SmartIR](https://github.com/smartHomeHub/SmartIR), [custom-components/places](https://github.com/custom-components/places), a [bluetooth-audio watchdog](https://github.com/rrecio/bluetooth-audio-watchdog), [jellyfin](https://github.com/jellyfin/jellyfin) itself, and [zmk](https://github.com/zmkfirmware/zmk) keyboard firmware.
- **Email plumbing**: opt-in IMAP FROM/TO/CC search in [mguessan/davmail](https://github.com/mguessan/davmail/pull/555), so local search of an Exchange mailbox stops being a lie.
- **Day job**: most of the volume lands in [Apicurio Registry](https://github.com/Apicurio/apicurio-registry), the open source **API and schema registry** I work on ([my patches](https://github.com/search?q=repo%3AApicurio%2Fapicurio-registry+author%3Apaoloantinori&type=pullrequests)).

The long tail is the point: buildah, litellm, llama-bro, voxtype, places, a GNOME timezone extension, a bluetooth-audio watchdog, and more. If I use your software weekly, you have probably seen my name in your inbox. I consider that a feature, not a bug.

## The hacker

I'm at my happiest inside something that was never meant to be opened.

- [osram-lightify-fw-re](https://github.com/paoloantinori/osram-lightify-fw-re): OSRAM Lightify bulbs read in **assembly** until they gave up their power-on logic and their proprietary `0xFC0F` cluster.
- [ts0505a-ota-investigation](https://github.com/paoloantinori/ts0505a-ota-investigation): custom OTA firmware for a budget Lidl light. Two verified candidates, both rejected with `INVALID_IMAGE`; the repo is the **byte-level autopsy**. **Negative results are results**.
- [opencl-apple-silicon](https://github.com/paoloantinori/opencl-apple-silicon): hashcat at **95% of native Metal**, inside Linux containers on Apple Silicon, via libkrun, clvk and the clspv fixes above.
- [cookies-extractor](https://github.com/paoloantinori/cookies-extractor): a minimal Android WebView app. Log in by hand, hand me the session cookies.

## The fiddler

My house runs on a slow compromise between me and the cloud, and I keep winning a little more each year. A **fablab membership** feeds the hardware habit.

- [local_smarthinq1](https://github.com/paoloantinori/local_smarthinq1) (+ the [HAOS addon](https://github.com/paoloantinori/ha-addon-lg-thinq1)): a **fake cloud** for LG ThinQ1 appliances, so they stop reporting to a datacenter.
- [ha_alexa_proactive](https://github.com/paoloantinori/ha_alexa_proactive), [ha-alexa-actions-smapi](https://github.com/paoloantinori/ha-alexa-actions-smapi) and [alexa-proactive-events](https://github.com/paoloantinori/alexa-proactive-events): three takes on making the Echo's **yellow ring** mean something.
- [ha-google-travel-time-enhanced](https://github.com/paoloantinori/ha-google-travel-time-enhanced): Google Maps travel time with waypoint support.
- [udp-broadcast-relay-redux-openwrt](https://github.com/paoloantinori/udp-broadcast-relay-redux-openwrt): an OpenWrt package relaying UDP broadcast and multicast across VLANs without lying about the source address.
- [school-timetable-timefold-case-study](https://github.com/paoloantinori/school-timetable-timefold-case-study): a real school timetable solved with Timefold constraint optimization on Quarkus, written up as a case study in agent-assisted development, with two solver fixes sent upstream to [Timefold](https://github.com/TimefoldAI/timefold-solver) along the way.
- [cyberwave-trim-deployment](https://github.com/paoloantinori/cyberwave-trim-deployment): Ansible that keeps my patrol robot's steering trim persistent. The robot itself has a personality module and a Discord channel; one day it will also have a public repo.
- More Home Assistant where that came from: [the ha-filtered list of my repos](https://github.com/paoloantinori?tab=repositories&q=ha).

## The dev

Distributed systems, build tooling, API infrastructure: the unglamorous layers are where I live.

- [maven-dependency-history](https://github.com/paoloantinori/maven-dependency-history): *why is this dependency in the output?* Point it at a local checkout, get a cited-evidence answer.
- [quarkus-extension-analyzer](https://github.com/paoloantinori/quarkus-extension-analyzer): dependency-usage analysis that understands Quarkus build-time extension wiring.
- [maven-ci-playbook](https://github.com/paoloantinori/maven-ci-playbook): assess before you optimize; a field-tested playbook for Maven CI with measurement tools.
- [apicurio-browser-extension](https://github.com/paoloantinori/apicurio-browser-extension): detects and renders OpenAPI specs with the Apicurio editor, straight on GitHub and GitLab.
- [gh-issue-landscape](https://github.com/paoloantinori/gh-issue-landscape): point it at any repo's issues, get a semantic 2D topic map back.

## How all of this gets built

I don't just use coding agents; I run them like an ops problem. They live on two machines bridged by a VPN as a Hermes fleet, answer to me from a terminal multiplexer and from Telegram, and take every request through a local model router whose fallback chain ends on hardware I own. When a provider starts returning empty 200s, a watchdog of mine reclassifies them as the outage they are. [backlog-workbench](https://github.com/paoloantinori/backlog-workbench) is the public corner of that rig.

They also live under house rules, enforced by **hooks rather than vibes**:

- **Evidence before assertion**: nothing is done until the proving command ran and somebody read the output.
- **Check the real artifact, not a proxy**: the signature, the file, the tool. Version strings lie.
- **An adjacent probe proves nothing**; test the exact path that failed.
- **Two failed fixes of the same kind** means stop patching and go read the source.

Anti-Vocale, up top, is built this way end to end: **agent-assisted, human-owned**.

---

<p align="center"><a href="https://www.linkedin.com/in/paoloantinori/">LinkedIn</a> · <a href="https://huggingface.co/pantinor">Hugging Face</a> · <a href="https://scholar.google.com/citations?user=5z4ffFEAAAAJ&hl=en">Google Scholar</a> · <a href="http://giallone.blogspot.co.uk/">Blog</a></p>
