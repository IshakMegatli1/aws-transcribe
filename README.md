<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Transcribe Audio Files with AI

**Project Link:** [View Project](http://nextwork.ai/projects/aws-ai-transcribe)

**Author:** ElHalouf  
**Email:** shakyleboss@gmail.com

---

![Image](http://nextwork.ai/lively_blue_beautiful_jellyfish/uploads/aws-ai-transcribe_o2p3q4r1)

---

## Introducing Today's Project!

In this project, I will use AI tools like Transcribe to develop app features or to improve accessibility.

### Tools and concepts

Services I used were Amazon Transcribe (for baseline transcription jobs, real-time transcription, and applying custom vocabularies) and Amazon S3 (for storing the audio/video input files and output transcripts).

Key concepts I learnt include generating a baseline transcription job to establish default accuracy, using real-time transcription to convert live speech to text on the fly, applying custom vocabularies and vocabulary filtering to boost recognition of domain-specific terms, using speaker partitioning to identify and separate different speakers in the audio, and generating subtitles for ready-to-use video captions.

### Project reflection

...

...

---

## S3 and Transcribe

To set up for this project, I'm using an S3 bucket to store the video. Amazon Transcribe is a service that converts audio and video into text, but it doesn't store the files. So I need to store the files somewhere (an S3 bucket). The finished transcription will also need to be stored in an S3 bucket.

![Image](http://nextwork.ai/lively_blue_beautiful_jellyfish/uploads/aws-ai-transcribe_k1l4m7n0)

---

## Run A Transcription Job

The steps to run a transcription job include uploading my media file to an Amazon S3 bucket, navigating to Transcription jobs in the console, selecting Create job, specifying job details (input/output S3 locations, language), and configuring optional settings like custom vocabularies before submitting. Overall, this process took me a few minutes to set up, though the actual transcription itself typically finishes within minutes depending on file length.

Amazon Transcribe uses model types, custom vocabularies and custom language models to improve transcription accuracy for domain-specific speech. Vocabularies provide pronunciation hints for individual specialized terms, while language models learn contextual word relationships. Use cases include transcribing scientific conference proceedings with technical jargon, medical documentation via Transcribe Medical for clinical conversations into EHR systems, call center analytics extracting customer insights, and generating subtitles for videos and meetings, boosting accessibility across industries

You can customize a transcription further with subtitling, which adds time-coded caption files (like SRT or VTT) synced to the audio, making content accessible for viewers who are deaf or hard of hearing, or watching without sound. Speaker partitioning, also called speaker diarization, helps to identify and label distinct speakers in the audio, separating who said what, useful for multi-person meetings, interviews, or calls.

![Image](http://nextwork.ai/lively_blue_beautiful_jellyfish/uploads/aws-ai-transcribe_g0h1i2j3)

---

## Baseline Transcript Review

To start using Amazon Transcribe, I first ran a baseline transcription job, which means I submitted an audio file using default settings with no custom vocabulary applied. This is because a baseline establishes reference accuracy, letting me later measure improvements after applying domain-specific customization.

While reviewing the baseline transcript, I noticed small innacuracies. These happened because of background noise, the nature of the language or because of terms that could be excluded for a better experience.

![Image](http://nextwork.ai/lively_blue_beautiful_jellyfish/uploads/aws-ai-transcribe_s3t6u9v2)

---

## Custom Vocabulary

I can resolve transcription inaccuracies using a custom vocabulary. A custom vocabulary is a list of specific words or phrases you supply to Amazon Transcribe for terms it wouldn't otherwise recognize correctly, like brand names or acronyms. I can resolve transcription inaccuracies using a custom vocabulary, which is a text file with phrases and optional pronunciation hints uploaded before a job runs. It improves accuracy by boosting recognition of those specific terms throughout your audio.

To create an item in a custom vocabulary, you need to define two values. They are the Phrase column (where you enter the specific words or phrases you want Transcribe to recognize).

And The DisplayAs column, where you tell Transcribe how these phrases should appear in the transcription, so they're displayed in a standardized or preferred format.

,,,

![Image](http://nextwork.ai/lively_blue_beautiful_jellyfish/uploads/aws-ai-transcribe_e3f4g5h6)

---

## Vocabulary Filters

Another feature in Transcribe is vocabulary filtering, which blocks out words you don’t want to appear in your transcripts. It's different from custom vocabularies because instead of replacing the words, it just removes them completely from the transcript.

My vocabulary filter removes filler words like : uh, um, actually, basically ...

![Image](http://nextwork.ai/lively_blue_beautiful_jellyfish/uploads/aws-ai-transcribe_u7v8w9x0)

---

## Enhanced Transcription

### I ran a new transcription with my custom vocabulary and filtering settings

The enhanced transcription is better than the baseline because it corrects certain words and it also removes filler words from the transcript.

![Image](http://nextwork.ai/lively_blue_beautiful_jellyfish/uploads/aws-ai-transcribe_k1l2m3n4)

---

## Real Time Transcription

For my project extension, I experimented with real-time transcription, which converts speech to text instantly as the speaker is still talking.

Even during real-time transcription, I could use features like custom vocabulary and vocabulary filtering. Overall, compared to a transcription job, real-time transcription was slightly less accurate than batch transcription jobs since it processes audio incrementally rather than analyzing the full context at once.

![Image](http://nextwork.ai/lively_blue_beautiful_jellyfish/uploads/aws-ai-transcribe_a5b6c7d8)

---

---
