# Bud Runtime Lite
Bud Runtime is an opinionated platform that simplifies the setup, experimentation, management, and scaling of compound AI systems. It is intended to be the foundational layer that provides all the tools necessary for the deployment of GenAI applications and their lifecycle management, with a focus on optimizing cost-efficiency and scalability. 



> [!NOTE]  
> Highlights information that users should take into account, even when skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]  
> Crucial information necessary for users to succeed.

> [!WARNING]  
> Critical content demanding immediate user attention due to potential risks.

> [!CAUTION]
> Negative potential consequences of an action.




| Feature  | Description |
| ------------- | ------------- |
| Heterogenous GenAI Clusters  |  Bud Runtime provides a layer of abstraction over different hardware types like CPU, GPU, HPUs, TPU etc. This enable you to configurebuild heterogenous cluster with the hardware you already have, to meet your SLOs. Start with a CPU and scale up with any other hardware.  |
| SLO-based Heterogenous Parallelism  | Bud Runtime is currently the only platform that supports SLO based heterogenous parallelism. It can perform pipeline parallelism across a variety of hardware, including CPUs, GPUs, and HPUs from different vendors such as Nvidia, AMD, Intel, and others. This enables you to combine hardware with different architectures and capabilities to meet specific SLOs. It automatically determines the most optimal parallelism settings—such as data parallelism, tensor parallelism, pipeline parallelism, expert parallelism, and sequence parallelism. This allows you to scale your GenAI clusters up or down while optimizing hardware usage and minimizing costs, without having to worry about hardware availability.  |
| Disaggregated Prefill & Decoding  | Bud Runtime supports SLO-aware automated disaggregated decoding & Prefill across multiple nodes/cards/cores. |
| Multi-Modality Support  | The Bud Inference stack provides one-click inference across clusters of any size and hardware, supporting various types of LLMs (such as MoEs, Mamba, etc.), MLLMs, Text-to-Audio, Audio-to-Text, and embeddings (including Multi-Modal, Multi-Architecture like LLM2Vec, and Encoder-based embeddings)  |
| Multi-Hardware Support  | Supports over 38 hardware types from 6 different vendors, including popular models like Nvidia A100, H100, B200, AMD MI300X, and Intel Gaudi 2/3. Additionally, it supports CPU-based inferencing for Intel Xeon (4th Gen and later) and AMD EPYC processors. |
| End-to-end Cluster Management  | Bud runtime supports Kubernetes and OpenShift-based clusters, with additional integration for cloud-managed services such as AWS EKS, Azure AKS, and GCP GKE (more integrations coming soon). It also provides a dashboard to manage, add, edit, and monitor clusters, workers, and events. |
| Supports 200+ Cloud-based Models & Providers  | with support for OpenAI, Anthropic, Azure, Google Vertex AI, AWS Bedrock, Together.ai, OpenRouter, Grok AI, X.ai, Deepseek etc. |
|  One Universal LLM Gateway  | One unified, universal LLM API gateway for your multi-cloud, local, on-prem, and proprietary models through an OpenAI supported endpoint. Built on top of LiteLLM, with support for all its features like Fallbacks, Load balancing, Retries, Rate limits etc.  |
| Zero Config Auto-Quantization | 9. The platform supports zero-config auto-quantization, evaluation, calibration, and post-quantization training. It is compatible with multi-hardware quantization, supporting Nvidia, AMD, Intel GPUs, HPUs, and CPUs. Quantization can be performed on a single GPU or a capable CPU server (e.g., EPYC or Xeons – 4th/5th/6th Gen). Additionally, the platform offers automated PPL evaluation and calibration with datasets such as WikiText2, Pile, C4, or any custom dataset (currently not available via the UI). |
| Multi-Lora Support  | The platform supports both dynamic and static LoRA adapter loading. With dynamic LoRA, you can load any number of LoRAs without the need to create multiple model replicas. Additionally, there is an auto-routing system that automatically selects the appropriate LoRA adapter based on several factors, including Prompt complexity/reasoning, Task type (e.g., Q&A, RAG, summarization, coding), Domain (e.g., Finance, Healthcare), Languages and more  |
| Prompt Compression & Caching  | The platform enables prompt compression for both cloud and local LLMs, reducing overall costs by up to 60% without impacting accuracy and with minimal impact on response time (<5-20ms). For more details, check out LLMLingua. Additionally, we offer out-of-the-box prompt caching and provide cache and metrics management through the dashboard.  |
| Simulate Everything  | GPUs and accelerators are expensive, leaving little room for costly trial and error. To address this challenge, we’ve developed a multi-layered simulator (Heuristics based & uses a more accurate model ) that helps to identify the optimal configurations for deployment, autoscaling, and quantization. The simulator also supports traffic packing simulations and enables performance comparisons between different hardware, models, and use cases. |
| Heterogenous Clusters + Optimised Cloud & Resource selection  | Bud is integrated with the Skypilot cost optimizer, which allows you to select the most cost-effective hardware that meets the SLOs across multiple clouds, locations, hardware types, and pricing models (on-demand, reserved, spot, etc.), ensuring that you can scale up and down while adhering to hardware availability constraints at the lowest possible cost.  |
| User, Projects & Deployment management  | We support multi-level user management, with projects & deployment and observability through an easy to use GUI.  |
| Single Sign-on, Social Login  | Bud is integrated with Keycloak allowing its enterprise users with single sign-on, social login, user federation & support for standard protocols.  |
| Zero config Distributed Inference & KV Caching with KV Cache/Load/SLO aware routing  | Run your Inference workloads at scale with the most optimal parallelism, worker, replica, batching configs to avoid suboptimal hardware utilization without any trial & error or technical knowledge.  |
| An internet scale runtime for tools, Agents & Services  | If we want to build an end-to-end singular system for GenAI models and agents, it requires a scalable, resilient, and stable runtime that supports microservices. We have built our agent/tools runtime on top of Dapr with custom protocols, MCP support, and additional tool support, such as web search. The runtime is primarily built for intelligent systems rather than humans, with dynamic JSON/graph-based orchestration, etc.  |
| Performance Benchmarking  | Run hardware performance benchmarking with custom datasets & LLM Perf compatible settings to evaluate hardware performance, while the Bud AI automatically create insights and recommend feasible SLOs & use cases.  |
| Playground  | The most gorgeous LLM playground in the planet, Period. You can test, compare, share deployments, routes & models with anyone easily.  |
| LLM Observability  | Analyze every LLM/Agent response for harmfulness, factuality, toxicity etc. (More real time & batched features coming soon)  |
| Reliable structured Outputs even for <1B models  | Inbuilt integration with LLM-Enforcer & Outlines with support for automated JSON repair to ensure that even for the smallest of SLMs you get a valid structured response back. SLM based JSONification (Coming soon)  |
| Best in class voice, video & text streaming  | Bud is integrated with LiveKit, the same stack that OpenAI uses for their real time audio streaming. Our platform ensures that you are able to easily integrate real time voice, video or text models and agents to your apps with minimal effort. We have also selected and optimized a few text to speech, speech to text models that you can easily get started with (Bud verified models). |
| Intelligent Routing  | Dynamically route requests to deployments/models/pipelines/agents/adapters based on sequence length, TTFT, Load, Geography (Where the request is coming from), Prompt complexity, language, tasks, domains, Simple shuffle, Token cost etc. Accuracy, Eval & Planner based routing coming soon.  |
| Inbuilt Distributed S3 Compatible object storage  | Inbuilt distributed object storage for models, cache, prompts, data etc, built on top of Minio.  |
| Enterprise level security  | Security scans for everything from model files, configs etc, before adding them to the cluster, with standard security protocols and tools integrated for OS hardening, cluster security, container security etc.  |
| API Key Management  | Secure API key creation, management and tracking for endpoints, clouds, agents etc.  |
| Automated Use case, Model, Hardware finder  | Our simulator allows you to easily find the best cluster, hardware config, use cases, and SLOs.  |
| Self healing Clusters  | Bud supports self healing clusters at scale in real time, while also using hardware pre-diagnosis to predict hardware failure, and automatically take adequate steps to ensure that SLOs are met.  |


### ***One Platform For Everything GenAI***

A GenAI deployment involves many moving parts—such as the operating system, runtime, inference stack, performance analysis stack, evaluation stack, red-teaming system, data source integrations, prompt layer, agent layer, and more. Relying on a multitude of different tools to manage these components adds complexity and creates technical debt. ***Our goal is to create a unified GenAI stack that incorporates all of these components, with optimized workflows focused on performance, usability, and security.***
A GenAI deployment involves many moving parts—such as the operating system, runtime, inference stack, performance analysis stack, evaluation stack, red-teaming system, data source integrations, prompt layer, agent layer, and more. Relying on a multitude of different tools to manage these components adds complexity and creates technical debt. ***Our goal is to create a unified GenAI stack that incorporates all of these components, with optimized workflows focused on performance, usability, and security.***

### ***Who Can Use It?***

- GenAI developers
- Application developers integrating GenAI capabilities to their projects
- Organizations adopting GenAI, whether in research, PoC, pilot, production, or scaling stages.
- Solution architects

Bud Runtime is built upon five core principles.

- ***Optimize for humans as well as AI :*** The platform offers an intuitive UI for humans and an easy-to-consume, structured, decoupled, and automatically orchestrated layer for AI systems. The upcoming *Ask Bud* feature is an AI agent that can automatically create, manage, and scale GenAI systems and agents on its own with a simple prompt. Bud Runtime’s microservices, built on top of Dapr, natively support MCP (Model Context Protocol) so that every component and service can be used by an AI agent in the future.
  
- ***Be as frugal as possible:*** Enable cost reduction for GenAI deployments through all possible methods, including caching, compression, simulators, auto-quantizers, heterogeneous clusters, and multi-cloud deployments. The platform also enables cost-aware deployments with cost estimates and forecasts.
  
- ***Build for scalability :***  Bud runtime is designed to be the foundational GenAI layer for any organization, and we believe it is crucial for this layer to be highly performant, stable, and scalable. Every component of the Bud stack is selected, benchmarked, and analyzed based on these criteria.
  
- ***Expect no expertise:*** Make every component as non-technical or guided as possible, with zero jargon or technical expectations. The platform's objective is to make the deployment, management, and scaling of GenAI as simple as managing a basic website.
  
- ***Have an opinion:***  The platform should have its opinion on best practices, optimizations, workflows, and systems. There are many moving parts in a GenAI system, and one poor design decision can cost millions. Therefore, we must focus on best practices, system components, and workflows rather than arbitrary flexibility.


### ***Features***

1. **Heterogenous GenAI Clusters:** Bud Runtime provides a layer of abstraction over different hardware types like CPU, GPU, HPUs, TPU etc. This enable you to configurebuild heterogenous cluster with the hardware you already have, to meet your SLOs. Start with a CPU and scale up with any other hardware.

2. **SLO-based Heterogenous Parallelism:** Bud Runtime is currently the only platform that supports SLO based heterogenous parallelism. It can perform pipeline parallelism across a variety of hardware, including CPUs, GPUs, and HPUs from different vendors such as Nvidia, AMD, Intel, and others. This enables you to combine hardware with different architectures and capabilities to meet specific SLOs. It automatically determines the most optimal parallelism settings—such as data parallelism, tensor parallelism, pipeline parallelism, expert parallelism, and sequence parallelism. This allows you to scale your GenAI clusters up or down while optimizing hardware usage and minimizing costs, without having to worry about hardware availability.

3. **Disaggregated Prefill & Decoding:** DoBud Runtime supports SLO-aware automated disaggregated decoding & Prefill across multiple nodes/cards/cores.
4. **Multi-Modality Support:** The Bud Inference stack provides one-click inference across clusters of any size and hardware, supporting various types of LLMs (such as MoEs, Mamba, etc.), MLLMs, Text-to-Audio, Audio-to-Text, and embeddings (including Multi-Modal, Multi-Architecture like LLM2Vec, and Encoder-based embeddings)
5. **Multi-Hardware Support:** Supports over 38 hardware types from 6 different vendors, including popular models like Nvidia A100, H100, B200, AMD MI300X, and Intel Gaudi 2/3. Additionally, it supports CPU-based inferencing for Intel Xeon (4th Gen and later) and AMD EPYC processors.
6. **End-to-end Cluster Management:** Bud runtime supports Kubernetes and OpenShift-based clusters, with additional integration for cloud-managed services such as AWS EKS, Azure AKS, and GCP GKE (more integrations coming soon). It also provides a dashboard to manage, add, edit, and monitor clusters, workers, and events.
7. **Supports 200+ Cloud-based Models & Providers:** with support for OpenAI, Anthropic, Azure, Google Vertex AI, AWS Bedrock, [Together.ai](http://Together.ai), OpenRouter, Grok AI, X.ai, Deepseek etc.
8. **One Universal LLM Gateway:** One unified, universal LLM API gateway for your multi-cloud, local, on-prem, and proprietary models through an OpenAI supported endpoint. Built on top of LiteLLM, with support for all its features like Fallbacks, Load balancing, Retries, Rate limits etc.
9. **Zero Config Auto-Quantization:** The platform supports zero-config auto-quantization, evaluation, calibration, and post-quantization training. It is compatible with multi-hardware quantization, supporting Nvidia, AMD, Intel GPUs, HPUs, and CPUs. Quantization can be performed on a single GPU or a capable CPU server (e.g., EPYC or Xeons – 4th/5th/6th Gen). Additionally, the platform offers automated PPL evaluation and calibration with datasets such as WikiText2, Pile, C4, or any custom dataset (currently not available via the UI).
10. **Multi-Lora Support:** The platform supports both dynamic and static LoRA adapter loading. With dynamic LoRA, you can load any number of LoRAs without the need to create multiple model replicas. Additionally, there is an auto-routing system that automatically selects the appropriate LoRA adapter based on several factors, including Prompt complexity/reasoning, Task type (e.g., Q&A, RAG, summarization, coding), Domain (e.g., Finance, Healthcare), Languages and more
11. **Prompt Compression & Caching:** The platform enables prompt compression for both cloud and local LLMs, reducing overall costs by up to 60% without impacting accuracy and with minimal impact on response time (<5-20ms). For more details, check out LLMLingua. Additionally, we offer out-of-the-box prompt caching and provide cache and metrics management through the dashboard.
12. **Simulate Everything :** GPUs and accelerators are expensive, leaving little room for costly trial and error. To address this challenge, we’ve developed a multi-layered simulator (Heuristics based & uses a more accurate model ) that helps to identify the optimal configurations for deployment, autoscaling, and quantization. The simulator also supports traffic packing simulations and enables performance comparisons between different hardware, models, and use cases.
13. **Heterogenous Clusters + Optimised Cloud & Resource selection:** Bud is integrated with the Skypilot cost optimizer, which allows you to select the most cost-effective hardware that meets the SLOs across multiple clouds, locations, hardware types, and pricing models (on-demand, reserved, spot, etc.), ensuring that you can scale up and down while adhering to hardware availability constraints at the lowest possible cost.
14. **User, Projects & Deployment management:** We support multi-level user management, with projects & deployment and observability through an easy to use GUI.
15. **Single Sign-on, Social Login:** Bud is integrated with Keycloak allowing its enterprise users with single sign-on, social login, user federation & support for standard protocols.
16. **Zero config Distributed Inference & KV Caching with KV Cache/Load/SLO aware routing:** Run your Inference workloads at scale with the most optimal parallelism, worker, replica, batching configs to avoid suboptimal hardware utilization without any trial & error or technical knowledge. 
17. **An internet scale runtime for tools, Agents & Services:** If we want to build an end-to-end singular system for GenAI models and agents, it requires a scalable, resilient, and stable runtime that supports microservices. We have built our agent/tools runtime on top of Dapr with custom protocols, MCP support, and additional tool support, such as web search. The runtime is primarily built for intelligent systems rather than humans, with dynamic JSON/graph-based orchestration, etc.
18. **Performance Benchmarking**: Run hardware performance benchmarking with custom datasets & LLM Perf compatible settings to evaluate hardware performance, while the Bud AI automatically create insights and recommend feasible SLOs & use cases. 
19. **Playground:** The most gorgeous LLM playground in the planet, Period. You can test, compare, share deployments, routes & models with anyone easily.
20. **LLM Observability:** Analyze every LLM/Agent response for harmfulness, factuality, toxicity etc. (More real time & batched features coming soon)
21. **Reliable structured Outputs even for <1B models:** Inbuilt integration with LLM-Enforcer & Outlines with support for automated JSON repair to ensure that even for the smallest of SLMs you get a valid structured response back. SLM based JSONification (Coming soon)
22. **Best in class voice, video & text streaming:** Bud is integrated with LiveKit, the same stack that OpenAI uses for their real time audio streaming. Our platform ensures that you are able to easily integrate real time voice, video or text models and agents to your apps with minimal effort. We have also selected and optimized a few text to speech, speech to text models that you can easily get started with (Bud verified models). 
23. **Intelligent Routing:** Dynamically route requests to deployments/models/pipelines/agents/adapters based on sequence length, TTFT, Load, Geography (Where the request is coming from), Prompt complexity, language, tasks, domains, Simple shuffle, Token cost etc. Accuracy, Eval & Planner based routing coming soon.
24. **Inbuilt Distributed S3 Compatible object storage:** Inbuilt distributed object storage for models, cache, prompts, data etc, built on top of Minio.
25. **Enterprise level security:** Security scans for everything from model files, configs etc, before adding them to the cluster, with standard security protocols and tools integrated for OS hardening, cluster security, container security etc.
26. **API Key Management:** Secure API key creation, management and tracking for endpoints, clouds, agents etc.
27. **Automated Use case, Model, Hardware finder:** Our simulator allows you to easily find the best cluster, hardware config, use cases, and SLOs.
28. **Self healing Clusters:** Bud supports self healing clusters at scale in real time, while also using hardware pre-diagnosis to predict hardware failure, and automatically take adequate steps to ensure that SLOs are met.

### ***Why should you care?***

<details>

<summary>AI hardware/Chip Companies</summary>

Currently, the leader in AI Chips is 5x in value and revenue compared to all the competitors put together. That means its a single point of control & failure for AI, which is quite bad for semi conductor and AI industry. While competition GA hardware have superior specs in terms of TFlops, Memory bandwidth, HBW Memory, & Power consumption, with real world GenAI workloads the leader outperforms the competition by 1-2x. This clearly means that software layer is the MOAT. Some open source initiatives like Triton Lang (From OpenAI), Tile Lang tries to create an abstraction layer over the current famous runtimes, but unavailability of performant kernels, optimisation techniques specific to the hardware, Inference stack, other features required for the adoption of hardware for production ready GenAI workloads. 
 
Our objective is to make a universal inference stack that is performant & optimally utilises hardware without any wastage. Along with this, we ensure that every users can get started with that hardware in production with all the adequate features that an enterprise, startups or developers. With heterogenous clustering & Parallelism, any enterprise or user can adopt a new hardware for their existing GenAI workload without having to spend any time in porting, writing kernels, addressing edge case scenarios, making it scalable etc (Which means for end users, they can go to market faster with any new hardware with a consistent set of features across all the hardware platforms and architectures). This plugged in with Skypilot like hardware finder & provisioning system allows any new AI chip manufacturer go to market on day one with out the support of large CSPs just by putting up their own cloud service and by integrating bud. 

**Key Benefits for AI Chip manufactures**

---

1. Be feature rich & ready for GenAI Inferencing/Agent workloads from day one.
2. Optimised kernels and other Transformer specific optimisations to allow their customers to optimally use the hardware without any extra code changes or development.
3. End users can adopt the new hardware on their existing deployments.
4. Go to market on day one without relying on any external CSPs.
5. Allowing external end users to discover and adopt new hardware based on pre-set rules based on SLOs, ROI, or performance. 

**How Bud Runtime Helps You Grow Against Larger Competitors**

Facing giants of the industry can be daunting, but Bud Runtime levels the playing field and fuels your growth:

- Close the Performance Gap: Bud’s optimized software stack ensures your chip performs competitively, even if you don’t have the R&D budget of the big players. In AI, software often makes the difference, and Bud delivers.
- Ease Adoption: Bud’s seamless integration and enterprise-grade features lower the barriers for customers switching from established brands. They won’t need to overhaul their systems to try your chip.
- Compete on Cost: With cost-optimized deployment options, your chip can offer high performance at a lower total cost of ownership. This appeals to startups, developers, and enterprises looking for value.

**Work with us:**

If you are the leading AI Chip manufacturer or brand new startup with an amazing new AI chips that gives great tokens/$,  Watts/$  or Tokens/Watts/$, then we would love to work with you. What can we offer:

1. Our engineers & researcher can work with your  team ensuring that bud Inference stack provides optimal performance on your hardware, without any cost.
2. Bud Lite is opensource allowing all your customers to adopt your hardware with all our features from day one.
3. Allow customers to find you through our hardware, use case, model finder and sizing system, which is free for everyone to use.
4. If your hardware is already listed with any tier 1, or tier 2 CSP, we will integrate you to our SAAS platform so that our automated ROI based heterogenous autoscaler can find your hardware and automatically consume it, if user’s rules (SLO, ROI, Performance or Power based metrics) matches your hardware specs

**Why Bud?**

Case study: We have built the first production ready inference engine & stack for Intel Server side CPUs with custom kernels leveraging AMX & AVX, implementation of paged Attention for CPU etc. [Provide Research paper, and Intel Whitepaper] [Contact form]

</details>

<details>

<summary>Accelerator cloud provider </summary>

Currently, every users are used to feature rich, easy to use, managed cloud services that does not require them to understand what happens under the hood, and they do not want to know. New cloud providers cannot provide bare metal GPUs or accelerators anymore as customers are expected to understand the lower level hardware optimisations and build up the entire stack on their own further delaying their Go to Market, which is undesirable. 

Bud Lite is an open source end to end inference stack that can work multiple leading hardware types and architectures while ensuring optimal performance on all of them. With Bud Lite, you have the following benefits:

1. **Be hardware agnostic:** Allows you to add new SKU’s that can provide you with better profit margins, while providing better TCO & ROI to the end customers.
2. **End to End Inference & Agentic stack:** Provide an end to end inference stack to the end customers without any extra cost, reducing their go to market time.
3. **Alternative Business Models:** As I write this (29th March 2025), the best reasoning & non-reasoning model is from DeepSeek, which is a completely opensource model. This provides new business opportunities and models to cloud providers - Tokens as a service, Model as a service, Outcome as a service (hopefully soon with Agents). 
4. **Maximise utilisation for all SKUs:** Since Bud Lite supports heterogenous clusters, parallelism with unified set of features across all the hardware types, they can scale up and down across different SKU types for the same workload without sacrificing on performance, SLOs and ROI.
5. **Find more customers through Bud:** Integrate your APIs, SKUs with Bud so that our customers can consume your infrastructure anytime based on the pre-defined set of rules they set. 

**What can Bud do for you?**

1. Help you adopt Bud platform for your end customers.
2. Have a burning requirement that all your customers ask for? Bud team and our community got your back, & yeah tabs on the house most of the time* 🙂
3. List your SKUs & Pricing in our hardware/cloud finder and autoscaling system.

**Update:** We are releasing a new functionality with Bud lite - end user account enabling CSPs to easily offer model as a service or token as a service.

</details>

<details>

Currently, you probably are using 5-10 different tools or a service for every part of your GenAI product, for everything from inference gateway, caching, prompt optimisation, finops, orchestration system, eval system, load balancing/rate limiting/retry systems etc. This quickly adds to the technical debt, performance issues, quality issues, higher unexpected costs. If you have started out with a cloud LLM or cloud based intelligence of any form, you soon will be forced to choose a local model because of cost, IP, customisation requirements or for scalability reasons. When the eventuality of a local LLM infrastructure is 100% probable, its best to start with a system that can help you with both the phases with all the features you need in one platform that you own. Even in the early stage, bud introduces no extra overhead or complexity but it rather simplifies the process & reduce your go to market time, but drastically reducing the number of integrations that you have to do.

1. Have a foundational GenAI stack that supports every product lifecycle - From early experimentation/research, PoC, Pilot, Production to Internet scale.
2. One Inference stack with all the necessary components for a GenAI Application: Any GenAI application requires a few mandatory components - A gateway, load balancer, caching system, observability system, Eval system, guardrails, Prompt management system etc. Currently you are probably integrating to different paid or opensource components, which can impact your go to market time, tech scalability, cost etc.
3. Until you win, we also don't: You do not pay a single cent until you reach 100M in value.
4. Help with new features and functionalities that you require.

**1. Simplified Development and Reduced Technical Debt**

- Unified Platform: Bud integrates critical components like an inference gateway, load balancing, caching, prompt optimization, observability, evaluation systems, guardrails, and financial operations (FinOps) into a single stack. This eliminates the need to cobble together disparate tools, reducing integration complexity and minimizing technical debt from the outset.
- Seamless Cloud-to-Local Transition: Bud supports both cloud-based large language models (LLMs) and local models, allowing startups to begin with cloud services and shift to local infrastructure as needs evolve (e.g., for cost savings, intellectual property control, or customization). This flexibility avoids the need for costly rearchitecting later.
- Lightweight Early-Stage Design: Even during experimentation or proof-of-concept (PoC) phases, Bud introduces no unnecessary overhead, simplifying the process while providing a robust foundation for future scaling.

**2. Accelerated Time-to-Market**

- Pre-Built Features: With capabilities like prompt compression, caching, intelligent routing, and multi-LoRA support built in, startups can deploy advanced functionality without spending time building these from scratch, speeding up development cycles.
- Zero-Config Simplicity: Features such as auto-quantization and automated scaling require minimal setup, enabling teams to launch quickly without deep expertise in GenAI infrastructure.
- Focus on Core Product: By abstracting away infrastructure complexities (e.g., retries, rate limiting), Bud lets founders concentrate on building their application’s unique value proposition, shortening the path from idea to market.

**3. Cost Efficiency and Financial Flexibility**

- No Upfront Costs: Bud’s model of not charging until a startup reaches $100M in value removes financial barriers, allowing founders to allocate resources to product development and growth rather than infrastructure costs.
- Cost Optimization Tools: Integrated FinOps features provide real-time monitoring and optimization of cloud and LLM usage costs, preventing unexpected expenses as the application scales.
- Efficient Resource Use: Prompt compression and caching reduce token consumption and API calls, lowering operational costs—crucial for budget-conscious startups.

**4. Enhanced Innovation and Competitive Edge**

- Abstraction of Complexity: By managing the underlying infrastructure, Bud frees up engineering teams to focus on innovation—building unique features rather than wrestling with technical plumbing.
- Advanced Capabilities: Support for real-time streaming (voice, video, text), multi-modality (e.g., text-to-audio), and agent orchestration enables startups to explore cutting-edge use cases without additional development effort.
- Performance Optimization: Optimized kernels and heterogeneous parallelism ensure high efficiency, giving startups a performance advantage over competitors using less streamlined solutions.

**5. Security, Compliance, and Control**

- Enterprise-Grade Security: Features like API key management, security scans, and cluster security ensure startups meet compliance and safety standards from day one, critical for industries with strict regulations.
- Data Ownership: As a platform you own, Bud gives startups full control over their data, models, and infrastructure—key for protecting IP and ensuring privacy.
- Customizability: While comprehensive, Bud is adaptable, allowing startups to tailor it to their specific needs without losing the benefits of an integrated solution.

[Need something that we already don't have?] — Contact us with a Partnership or feature request.

###

</details>

<details>

<summary>For Enterprises</summary>

Enterprises adopting GenAI right now are handling the entire development process with an adhoc approach of "figure it out as we face it," which drastically increases costs, technical debt, and go-to-market time, among other challenges. A recent Accenture survey mentions that 74% of the surveyed enterprises stated that AI is contributing to their company's technical debt. It is also crucial for them to ensure that a strong foundational layer is established, on top of which all future agentic workflows and autonomous agents can be built.

What does Bud Lite offer to enterprises:

1. **Built for non-technical users:** Bud Lite allows enterprises to adopt production-ready systems at scale without the need to invest millions in new GenAI technical resources. The 'Ask Bud' feature is intended to automate the deployment, management, and scaling of GenAI systems, so you can focus on your business and its objectives with GenAI. What’s the point of GenAI and Agents if they cannot automate themselves? 😕
2. **Engineered for performance:** In GenAI, better performance means a much better ROI. The Bud stack is engineered from the ground up to ensure optimal performance for the given hardware— from the OS layer to the clusters.
3. **Secure & compliant at every level:** Bud stack is compliant with AWE, ATT&CK, AIPC SOC etc.
4. **Cloud & hardware agnostic:** Bud heterogenous cluster and parallelism technology allows enterprises to not depend upon a single cloud or hardware type. We provide an abstraction layer that allows enterprises to scale at their will without the constraints of the clouds or hardwares. This also means that you can scale up or down at your will & ROI metrics without hardware scarcity or long term reservation of GPUs.
5. **Start small:** Bud supports CPU inference allowing enterprises to get started with their GenAI deployments without large capex or opex commitments. Bud also have integration with 200+ cloud providers & models, allowing you to go from an idea to agent in a day, and scale it to your own infrastructure or on-prem as you see value.

## What is coming?

---

1. Prompt analysis, optimisation & tracing
2. RAG Components - ReRankers, Chunker, Database - that supports vector, Graph, etc.
3. Dynamic UI Generation in Playground
4. Structured data to APIs, with custom logic through lambda functions
5. Evaluations - Custom datasets
6. Optimised & Secure distros for different hardware types
7. Secured Distroless for containers
</details>
