# How To Choose A Local LLM To Use With Your AI Coding IDE

Source:
[The Ultimate Local AI Coding Guide](https://www.yout-ube.com/watch?v=rp5EwOogWEw) by Zen van Riel

## Summary of Keypoints

This masterclass guides you through setting up a local AI coding environment, outlining the necessary hardware knowledge, software tools, performance trade-offs, and integration with popular code agents.

### 1. Hardware and Model Selection Fundamentals

* **Independence from Cloud APIs:** Running a local AI coding assistant is key to becoming independent of commercial cloud APIs [[00:05](http://www.youtube.com/watch?v=rp5EwOogWEw&t=5)].
* **VRAM is the Main Constraint:** The biggest limitation is **VRAM** (Video RAM)—the dedicated memory on your GPU. The entire AI model must be loaded into VRAM, not the computer's regular RAM [[03:41](http://www.youtube.com/watch?v=rp5EwOogWEw&t=221)].
* **Quantization:** To fit larger models onto less VRAM, use **quantized models**. These are downscaled versions of the original models that maintain accuracy and performance while reducing file size (e.g., a 32 billion parameter model can be reduced to 21 GB) [[03:20](http://www.youtube.com/watch?v=rp5EwOogWEw&t=200)].
* **MacBook/Mac Mini Advantage:** Mac devices with Apple's M-series chips use **unified memory**. This allows a large portion of the system RAM (e.g., 48 GB) to be used as VRAM, offering a strong, budget-friendly option for high-context local AI [[05:03](http://www.youtube.com/watch?v=rp5EwOogWEw&t=303)].
* **Avoid VRAM Overload:** If the model's VRAM requirement exceeds your dedicated GPU memory, the system will use **shared GPU memory** (regular RAM), which causes severe performance degradation and lag [[17:06](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1026)].

### 2. The Context Window Challenge

* **Real-World Code Requires More Context:** For real AI code use cases, you need to load a significant amount of file context into the model [[07:33](http://www.youtube.com/watch?v=rp5EwOogWEw&t=453)].
* **Default Settings are Insufficient:** Many tools default to small context windows (e.g., 4,000 tokens), but a simple sample application can easily contain over 9,000 tokens of source code [[08:54](http://www.youtube.com/watch?v=rp5EwOogWEw&t=534)], [[09:16](http://www.youtube.com/watch?v=rp5EwOogWEw&t=556)].
* **VRAM vs. Context:** Increasing the context length drastically increases VRAM usage. Model selection must balance the model's size (parameters) with the required context length you want to support [[10:26](http://www.youtube.com/watch?v=rp5EwOogWEw&t=626)].

### 3. Setup and Performance

* **Recommended Tool (LM Studio):** LM Studio provides a simple user interface for downloading, testing, and running models, and is recommended for beginners [[01:49](http://www.youtube.com/watch?v=rp5EwOogWEw&t=109)].
* **API Compatibility:** Tools like LM Studio expose the local language model using the **OpenAI API format**, ensuring compatibility with most open-source AI coding agents [[02:18](http://www.youtube.com/watch?v=rp5EwOogWEw&t=138)].
* **Speed vs. Quality Trade-off:**
    * **Larger Models** (e.g., 32B parameters) offer better code quality but are significantly slower (e.g., 42 tokens/second) [[19:49](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1189)], [[20:40](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1240)].
    * **Smaller Models** (e.g., 20B parameters) are much faster (e.g., 175 tokens/second) but may have worse performance on complex coding tasks [[20:23](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1223)], [[15:19](http://www.youtube.com/watch?v=rp5EwOogWEw&t=919)].

### 4. Integration and Optimization

* **Connecting to Code Agents:** You can connect the local models running in LM Studio (via the active local server) to popular open-source AI agents inside Visual Studio Code (VS Code), such as **Continue** [[21:49](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1309)] and **Kilo Code** [[22:59](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1379)].
* **Agentic Tools Consume Context:** Agentic AI tools consume context very quickly, meaning you need a large context window to enable them to operate properly without getting stuck in loops [[24:59](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1499)].
* **Optimization Techniques:** To maximize your context window, you can enable experimental optimizations like **Flash Attention** and **K-cache quantization** in your model loading parameters [[25:29](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1529)].
* **Advanced Routing:** Tools like the **Claude Code Router** allow you to redirect cloud-based code editing tools (like `cloud code`) to use your local LM Studio model instead of the cloud API [[29:24](http://www.youtube.com/watch?v=rp5EwOogWEw&t=1764)].

### Final Recommendation

Local AI coding is an excellent tool for **simpler scripts and small software projects**. However, for complex software environments, you must manage your expectations, as you will likely run into context window limitations, and may still need to dedicate some work to state-of-the-art cloud models [[35:13](http://www.youtube.com/watch?v=rp5EwOogWEw&t=2113)].

