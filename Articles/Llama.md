https://arxiv.org/abs/2302.13971

https://blogs.microsoft.com/blog/2023/07/18/microsoft-and-meta-expand-their-ai-partnership-with-llama-2-on-azure-and-windows/

https://huggingface.co/blog/llama2

https://pub.aimind.so/this-is-why-you-cant-use-llama-2-d33701ce0766

LLaMA is a collection of [[Large Language Models#Foundation models|foundation language models]] ranging from 7B to 65B parameters. For a given compute budget, the best performances are not achieved by the largest models, but by smaller models trained on more data. 

Meta and Microsoft have partnered to expand Llama 2 on Azure and Windows so that developers and organizations can build AI powered tools and experiences. Open and frontier models are supported and developers can choose the type of model they wish to work with.
Developers can now utilize Azure AI's advanced features for model training, fine-tuning, inference, and AI safety through the availability of the Llama 2 models. By incorporating these models into Windows, it enhances the platform as the ideal choice for developers to create personalized AI experiences for their customers. This integration also allows developers to leverage powerful tools such as Windows Subsystem for Linux (WSL), Windows terminal, Microsoft Visual Studio, and VS Code.

Llama 2 has also been integrated into HuggingFace,  a French-American company that develops tools for building applications using machine learning.  Llama 2-Chat is likely to be the best open source chatbot. The features accessible now are:

- Transformers integration
- Text generation inference
- Models on the hub
- Examples to fine-tune the small variants of the model with a single GPU
- Integration with Inference Endpoints


Llama-2's largest version has 70 billion parameters. The scale of this ensures that for most researchers, hobbyists or engineers, the hardware requirements are a significant barrier.

**Costs** :
- To load a model in full precision, i.e. 16-bit (or float-16) on a GPU for downstream training or inference, it costs about 2GB in memory per 1 billion parameters. So, just to load Llama-2 at 70 billion parameters, it costs around 140GB in memory at full precision. 
-  Loading models at different precision levels is possible. Loading in 8 bit means, 1GB per 1 billion parameters, requiring 70GB of memory.
- For fine-tuning using the AdamW optimiser, each parameter requires 8 bytes of GPU memory. For Llama-2, this would mean an additional 560GB of GPU memory. In total, we would require between 630GB and 840GB to fine-tune the Llama-2 model
- For many, access to GPUs is done via Google Colab. The highest-spec GPU available in Colab currently is the A100 with 80GB of memory, which is not enough for fine tuning as well.

**Alternative**

_Petals_ - an open source project for democratizing LLMs.
Petals works on a client-server architecture. The client uses an LLM for inference or fine-tuning. The servers are third parties that have opted to allocate some of their GPU resource to the Petals network, also called public swarm.

**Working**


The given transformer model is divided into different parts and distributed across multiple public servers based on their GPU memory. When a client wants to make a prediction using the model, it identifies a sequence of servers that collectively possess all the required parts of the model. The client has the embedding layer stored locally and generates the embeddings itself. These embeddings are then sent to the servers which process them through the subsequent parts of the model. The servers send the updated representations back to the client, which uses them for predicting the next token. Essentially, the usual prediction tasks performed by a large language model are spread across various public servers.

**Current issues with Petals**:

- Not enough servers on the network for it to be practical
- Privacy concerns, as servers operating on the first layers of models can reverse engineer them to recover the input embeddings



