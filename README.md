# Title: M.A.V.I.S My Average Very Intelligent System 

## Introduction
Artificial intelligence (AI) is rapidly evolving in today’s age. M.A.V.I.S (My Average Very Intelligent System) is an AI-powered voice assistant designed to provide an engaging and interactive user experience. It is inspired by the fictional AI J.A.R.V.I.S from the Iron Man comics and movies. J.A.R.V.I.S is similar to traditional AI assistants like Siri and Google Assistant, but offers a more conversational and witty personality. Through the integration of speech-to-text, a fine-tuned large language model, waveform audio visualizations and text-to-speech synthesis, M.A.V.I.S offers dynamic and fun interactions through both auditory and visual feedback In contrast to the majority of existing voice assistants that rely on rigid command-based systems, M.A.V.I.S is designed to take into account contextual awareness and user engagement. The model is offered as a mobile app on the IOS platform designed within the XCode editor. By leveraging open-source applications VOSK for speech recognition, RASA for natural language understanding, and Mozilla TTS for speech synthesis, the model balances performance, flexibility, and ethical AI principles. 

M.A.V.I.S is an AI system that not only understands user intent but also communicates in a human-like manner. Our approach to creating M.A.V.I.S uses a sophisticated pipeline that transforms voice input into engaging interactions. It is a complete redesign of the typical AI assistant, from recording audio waveforms to generating smart responses and rendering speech output. We emphasize user interaction, accessibility, and ethics, and have created an AI assistant that has made technology interactions more responsive and engaging. M.A.V.I.S extends its functionality beyond engaging conversations by integrating seamlessly with everyday apps. With direct access to your calendar, it can schedule, reschedule, or remind you of appointments, ensuring you never miss an important date. Additionally, by linking to weather applications, M.A.V.I.S provides real-time weather updates and forecasts, helping you plan your day better. These functionality features are planned as implementation within a minimum viable product.


## Related Works
When building M.A.V.I.S, we looked at a lot of other projects and research to understand what's already out there and where we could do something different. One of the biggest areas we focused on was the ethics of advanced AI assistants. A paper by Gabriel et al. (2024) brings up important questions about trust, misuse, and value alignment[^1]. That stuck with us, and it's why we’re putting a lot of emphasis on transparency, feedback loops, and diverse data from the start. We don’t want to just build something that works—we want it to be responsible and respectful of the people using it.

On the technical side, M.A.V.I.S uses a combination of VOSK for speech-to-text, RASA for natural language understanding, and Mozilla TTS for generating speech. This setup is pretty aligned with a few other projects, like My Assistant SRSTC[^6] and another voice assistant built using GPT-3.5 and the Web Speech API[^7]. Those projects show how to stitch together the components of a speech pipeline, and they’ve been helpful in figuring out how to structure ours. The difference is that we’re going beyond just making the assistant functional—we’re adding personality, visual waveform feedback, and a more dynamic way of responding to users.

There’s also some cool research like LLaSM (Large Language and Speech Model) that tries to merge speech and text into a single training process[^2]. We're not doing exactly that, but it definitely influenced how we think about context in speech. While LLaSM is more focused on large-scale, instruction-following models, we’re focused on real-time interaction and creating an assistant that feels alive—more like J.A.R.V.I.S than a basic Q&A bot.

We also took inspiration from projects that focus on specific user groups. One study looked at how older adults interact with voice assistants, and it pointed out how rule-based models don’t always understand different speech patterns, especially as people age[^3]. This made us think more about inclusivity and how we can make M.A.V.I.S flexible enough to work well for everyone—not just the tech-savvy.

Another interesting idea came from a paper about real-time emotion recognition in smart home assistants. They used things like MFCCs and CNNs to detect emotional tone in speech[^5]. We’re not fully there yet, but it got us thinking about how emotional awareness could be a future direction for M.A.V.I.S—making it not just smart, but empathetic and reactive in more human ways.

And finally, to help with some of the nuts and bolts of building this, we leaned on resources like Natural Language Processing: An Introduction[^4]. It’s more of a general guide, but it helped us troubleshoot and understand how to better structure our NLP models, especially when users go off-script or say something unexpected.

Overall, our approach to M.A.V.I.S blends what’s been done before with some fresh takes—like giving it a real personality, making it visually and auditorily engaging, and thinking through the ethical side from the beginning. It’s not just about building a tool, it’s about reimagining what interacting with AI could feel like.

## Ethical Sweep
General Questions: 
Should we even be doing this? Yes—if built responsibly, M.A.V.I.S can enhance user interaction and accessibility, but it requires careful oversight to ensure ethical use. 
What might be the accuracy of a simple non-ML alternative?  A non-ML approach would likely have lower accuracy and flexibility in understanding natural language compared to ML models. 
What processes will we use to handle appeals/mistakes? We plan to implement user feedback systems, clear error reporting channels, and regular reviews to correct issues and update the system. 
How diverse is our team? Our team includes members from various technical and creative backgrounds. 
How will we maintain transparency for the model?
We will document model decisions, communicate its limitations, and provide explanations for its generated responses when possible

Data Questions:
Is our data valid for its intended use? The data will require ongoing validation and updates to maintain its relevance and accuracy.
What bias could be in our data? The data may contain language, cultural, or demographic biases favoring certain perspectives over others which you must identify and address.
How could we minimize bias in our data and model? We can minimize bias by sourcing diverse and balanced datasets and applying bias detection techniques during training. This requires implementing comprehensive sampling strategies across different demographics, languages, and cultural contexts. Regular testing against known bias benchmarks and establishing feedback loops from diverse user groups will help identify and mitigate biases as they emerge. Additionally, maintaining transparent documentation about known limitations and potential bias areas will allow for ongoing improvement of the system.
How should we "audit" our code and data? You could implement automated testing, clear documentation, and human auditing of the system.
How can we ensure data security? If M.A.V.I.S was to be released at large scale, encryption for stored and transmitted data will be of utmost importance to ensure user privacy. We will also limit data retention and anonymize sensitive information.

## Methods
Our project is developed entirely in Python, which serves as the coding language which we wil integrate various open-source tools and libraries. We will begin by using VOSK for speech recognition, which efficiently converts spoken input into text, forming the initial output of our data processing pipeline with a text file[^8]. This transcribed text is then fed into our AI assistant built on the RASA open-source framework, where natural language understanding and conversational response generation take place utilizing a deep neural network[^9]. The system further processes these responses by converting the output text back into speech using Mozilla Common Voice TTS to create an audio file[^10]. Finally, when displayed back through the phone application, the UI will use a waveform generator to create a unique visual[^11]. Our data pipeline also leverages publicly available data sets to train these tools. Mozilla Common Voice TTS is trained with a consistent voice modeled off the LJ Speech dataset[^12], while VOSK benefits from pre-trained models that require no additional fine-tuning. For the RASA framework, we incorporate a dual-dataset approach using RASA’s sample dataset[^13] for intent recognition and the MultiWOZ dataset[^14] for generating realistic dialogue responses on existing examples. Potential pitfalls include challenges such as ambient noise affecting VOSK's accuracy in transcribing user input, latency in processing real-time interactions, and ensuring robust data security and privacy measures throughout the system.

### Speech Recognition and NLP
The Large Language and Speech Model (LLaSM) presented by Shu et al.[^2] posits that speech is context-rich and underscores the need for a versatile AI technology that integrates speech and language prompts. It describes the methodology behind LLaSM and its dataset addressing the shortage of open-source speech–text cross-modal instruction-following data. Although tangential to our project, we may diverge in execution by implementing a futuristic user interface or giving our model a specific persona[^2]. “My-Assistant,” developed by Gupta et al.[^6] focuses on speech recognition and natural language understanding techniques. It details methods for pre-processing, speech signal processing, intent identification, and response generation, discussing system integrations and performance metrics that emphasize enhancing recognition accuracy and intent identification.

### User Interaction and Accessibility
The study done by Yan et al.[^3] examines how older people interact with voice assistants, which can differ drastically from interactions by younger users. It proposes modifications to rule-based NLP models with human input to better accommodate the changes in speech patterns that occur with age, aiming to create a more accurate and effective voice assistant for all users. Chatterjee et al.[^5] explores an AI-driven system for detecting emotions in speech using techniques such as Mel Frequency Cepstral Coefficients (MFCCs) and convolutional neural networks (CNNs). It also integrates Hidden Markov Models (HMMs) and covariance matrices to refine real-time emotion recognition, which could inspire enhancements in our system’s responsiveness and user engagement.

### AI Chatbots and Voice Interfaces
AI chatbots using GPT-based models and speech-to-text technology enhance voice interactions. The study done by Balamurugan et al.[^7] details the design of a speech-controlled AI assistant built with a React-based web application. Using the Web Speech API for speech-to-text conversion and OpenAI’s GPT-3.5 for NLP, the system is evaluated for usability and real-time performance. Insights regarding system constraints and optimization are valuable for refining our own voice assistant implementation.

Unlike existing assistants that rely on predefined commands, M.A.V.I.S combines existing tools to create a more dynamic and context-aware system. By focusing on engagement, personalization, and ethical considerations it aims to make AI interactions more natural and enjoyable.

## Discussion/Results
We will evaluate M.A.V.I.S based on its responsiveness, conversational accuracy, and user engagement in various testing scenarios. Initial results will focus on system latency, speech recognition quality, and how naturally the assistant interacts with users.

## Conclusion/Future Work
Our goal is to create a voice assistant that feels more human and less robotic. Future work includes improving emotional intelligence, expanding accessibility for diverse user groups, and optimizing performance for mobile deployment.

## Impact Questions
Do we expect different error rates for different sub-groups in the data? Yes, variations in demographics can lead to different errors and subgroup testing could help.
What are likely misinterpretations of the results and what can be done to prevent those misinterpretations? Users may interpret the answers of the AI as definitive answers which can be mitigated with clear disclaimers.
How might we impinge individuals' privacy and/or anonymity? Handling the voice-to-text data is important and can be more secure with encryption.
What is the environmental impact of training and running M.A.V.I.S? All AI models require tons of computational power, which in turn has an energy cost. We will consider optimizing efficiency and minimizing energy use where possible.

## References

[^1]: The Ethics of Advanced AI Assistants. https://arxiv.org/abs/2404.16244 ↩

[^2]: LLASM: Large Language and Speech Model. https://arxiv.org/pdf/2308.15930 ↩

[^3]: Understanding Older People’s Voice Interactions with Smart Voice Assistants: A New Modified Rule-Based Natural Language Processing Model with Human Input. https://pmc.ncbi.nlm.nih.gov/articles/PMC11135128/ ↩

[^4]: Natural Language Processing: An Introduction. https://www.researchgate.net/publication/51576224_Natural_language_processing_An_introduction ↩

[^5]: Real-Time Speech Emotion Analysis for Smart Home Assistants. https://ieeexplore.ieee.org/abstract/document/9352018 ↩

[^6]: My Assistant SRSTC: Speech Recognition and Speech to Text Conversion. https://ieeexplore.ieee.org/abstract/document/10593324 ↩

[^7]: Artificial Intelligence-Based Chatbot with Voice Assistance. https://ieeexplore.ieee.org/abstract/document/10545197 ↩

[^8]: VOSK Speech Recognition. https://alphacephei.com/vosk/ ↩

[^9]: RASA Documentation. https://rasa.com/docs/rasa/ ↩

[^10]: Mozilla Common Voice. https://commonvoice.mozilla.org/en ↩

[^11]: AudioViz by larryleeyu. https://github.com/larryleeyu/AudioViz ↩

[^12]: LJ Speech Dataset. https://keithito.com/LJ-Speech-Dataset/ ↩

[^13]: RASA Formbot Example Data. https://github.com/RasaHQ/rasa/blob/main/examples/formbot/data/nlu.yml ↩

[^14]: MultiWOZ Dataset. https://github.com/budzianowski/multiwoz ↩
