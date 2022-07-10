# Podcast discovery (still) is broken – let’s improve it with NLP and Machine Learning

Project for Diploma of Advanced Studies at FHNW
Patrick Arnecke, April 2022
- [Related article from FHNW](https://www.fhnw.ch/de/weiterbildung/technik/data-science/projekte/warum-das-entdecken-von-podcasts-so-schwierig-ist-und-was-man-mit-machine-learning-dagegen-tun-kann) (in German)
- PDF of Diploma presentation

---

### Outline
During the last decade, **podcasts have become a hugely popular medium**. As of [April 2021, there are around 2 million podcasts and 48 million episodes available worldwide.](https://www.podcastinsights.com/podcast-statistics/) It is a booming market and a 1 billion+ USD industry with [year-on-year growth of ~10%](https://www.insiderintelligence.com/insights/the-podcast-industry-report-statistics/). 

Despite its enormous success story, podcasting still is a young and emerging medium. Creators try out and validate best practices day by day. They choose from a wide variety of concepts, formats, composition, and monetization schemes. Users on the other side face **the challenge of discovery: In this vast amount of content – how do I find the right piece** that fits my interest, time frame, and usage context, e.g., chilling, working out, commuting?

**Discovery of podcasts is still astonishingly cumbersome and simplistic.** The prevalent ways are rankings and charts, editorial curation, and simple search for topics or people. These are basic forms of content exploration that lack the sophistication of discovery available for video, textual, or music content – think YouTube, Spotify. 

Another main mode of discovery is [through social media posts and recommendations of friends and family](https://www.edisonresearch.com/the-podcast-consumer-2019/). 
 
### Challenges
What is so special about podcasts that makes discovery so hard?

Discovery of spoken audio content relies mainly not on the content itself but rather on metadata. Transcription is the first obvious step to make it more accessible. However, only very few creators seem to have the time, resources, or interest to provide these. Users mostly can only search in the metadata the creator provides in the RSS feed, e.g., for a title, a creator, or keywords in the podcast or episode description. 

Transcription helps but doesn't solve the problem. **Podcasts aren't just text files in audio form.** Podcasting rather is **multimodal medium.** The characters of the hosts and guests, their vocal tonality, the *feeling* of authentic interaction is an essential building block. The listening experience is immersive and intimate. Spoken text is fundamentally different from written (or transcribed) text. Conversations can emerge spontaneously, surprising and unscripted. In many cases spoken content lacks paragraphic and sometimes even sentential boundaries. It can be a continuous flow of thoughts. Verbal phenomena like disfluencies ("äh", "hmmm" etc.), interruptions, people speaking in parallel aren't just «noise» but rather do contribute to the listening experience and tonality. Music and audio effects too are a very influential facet that cannot be transcribed and processed with regular NLP techniques. 

While NLP research usually can focus on one domain (e.g., news, medicine, law) and optimize for that, we face a much broader variety of disparate genres, topics and formats. The 2 Mio.+ available podcasts basically entail every imaginable domain.

More challenges come from the fact that the [motivations to consume podcasts can be very different].(https://www.edisonresearch.com/the-podcast-consumer-2019/) These can be learning new things, entertainment, staying up-to-date or getting relaxed among many other use cases. Actual or desired search modes vary a lot: E.g. basic catalog search, «tip of the tongue» search (*«I have heard about or listened to a podcast but can't quite remember its title...»*), personalized search that implies varying user tastes for formats, audio quality, affinity for the hosts, voice tonality and contextual factors such as timeframe of consumption (e.g., commute, gym, at home).

To boil it down – **how can we possibly incorporate such hetergeneous, multimodal data und varying use cases into a search and recommendation application?**

### Research goal

> **My research goal is to improve the search and discovery of podcasts by finding news ways to generate or refine metadata with NLP and machine learning.** 

Besides standard NLP techniques like LDA and Doc2Vec I want to look at Transformer models as advanced NLP building blocks. Transformer models have become popular in the last years due to their power and effectiveness. One success factor too is that the use of these models has been made much easier by platforms like [Hugging Face](https://huggingface.co/) and open-source projects like [Spacy](https://spacy.io/).  

In particular I’d like to look at these methods:
- [X] **Topic modeling**
- [X] **Document embedding**
- [X] **Clustering**
- [X] **Named entity recognition**
- [X] **Zero shot classification for extracting entirely new labels**

### Data
Metadata and raw audio files are available through RSS feeds (which is the standard way of distributing podcasts). Gathering data is possible through platform APIs, e.g., iTunes’ search and Spotify’s podcast API.

### Relevant research and comparable projects
There are a couple of products and services that try to improve podcast discovery, mostly by transcribing episodes. Most of these address the US market and seem to only work for podcasts in English:
- [Apple](https://9to5mac.com/2019/06/04/podcasts-ios-13/), [Google](https://searchengineland.com/google-brings-search-to-podcasts-through-automatic-transcription-314798), [Spotify](https://www.theverge.com/2021/5/18/22441886/spotify-podcast-transcription-accessbility-app-update), [Amazon](https://podnews.net/press-release/amazon-music-transcripts), and Facebook have announced and/or launched transcriptions for (some of) the podcast content on their platforms – mostly their exclusive and original shows.
- Publishers like Omny Studio [started to look into transcriptions for their creators](https://blog.omnystudio.com/are-transcriptions-the-building-blocks-for-the-future-of-audio-distribution-464e653c2668).
- [Some podcasters have begun to transcribe their episodes](https://tim.blog/2018/09/20/all-transcripts-from-the-tim-ferriss-show/) with third-party services like [rev.com](https://www.rev.com/). One minute of transcription costs around 1.25 USD which seems affordable for any podcast with some revenue and average success. However, not many creators seem to invest in the form of accessibility.
- [Listen Notes](https://www.listennotes.com/) – The self-proclaimed «Best Podcast Search Engine» aims to provide a service to users, creators, and advertisers alike. From looking at the API documentation I assume that it mostly is used as a B2B service for [a lot of podcast apps](https://www.listennotes.com/api/apps/). Listen Notes enriches metadata mostly by named entity recognition for people, places, and topics.
-[Media companies have a vital interest in metadata enrichment for their content.](https://tech.ebu.ch/docs/events/mdn2021/MDN_2021_Programme_detailed.pdf) 
- Podcast search, discovery, and recommendation are actively researched, see e.g., [this examination  of challenges and future directions in podcast information access](https://arxiv.org/pdf/2106.09227) or [this research project that aims to model Non-textual Characteristics of Podcasts.](https://dl.acm.org/doi/10.1145/3289600.3290993)