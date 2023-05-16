---
layout: blast
---

## an open-source workflow to generate live automatic subtitling

bla.st is an open-source workflow which operates on the media-cloud.ai platform. It can create subtitles for files and live streams. The delivered output depends on the targeted use-case: subtitle file or subtitle stream, either for broadcast and web streaming.
bla.st has been developed and strongly experimented by DaIA, the Artificial Intelligence team of France Televisions, on both French and English languages, using the [Speechmatics](https://www.speechmatics.com/) transcription engine. The workflow stays open to any other engine.

### Architecture

bla.st is using at least 3 <b>workers</b> to produce subtitles:
1/ the <b>transcript worker</b>, which generates raw text from audio
2/ the <b>subtitle factory worker</b>, responsible for creating subtitles blocks from raw text
3/ the delivery worker, either the <b>HLS playlist worker</b> for a HLS web player or the <b>newforerver worker</b> to address a broadcast inserter with a teletext live stream.

Other workers could be added, i.e. if an automatic translation or a better speaker change detector are needed.
All these workers are open to collaborative improvements under the AGPL license.

{% include mermaid_schemas/main_architecture.html %}
