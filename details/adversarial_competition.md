# The Adversarial Competition Era (GANs)

```mermaid
graph LR
    Noise[Random Noise z] --> Generator[Generator G]
    Text[Text Embedding t] --> Generator
    Generator --> Fake[Fake Image G(z, t)]
    Fake --> Discriminator[Discriminator D]
    Real[Real Image x] --> Discriminator
    Text --> Discriminator
    Discriminator --> Loss[Loss & Backpropagation]
    Loss -.->|Optimize G & D| Generator
```

### Introduction
Generative Adversarial Networks (GANs) dominated the early era of text-to-image generation (~2014-2021). The foundational concept is a game-theoretic competition between two neural networks: a **Generator** and a **Discriminator**.

### Architecture
- **Generator (G):** Takes a random noise vector $z$ and a text embedding $t$ (extracted from a text encoder) to synthesize a fake image $G(z, t)$ that looks as realistic as possible.
- **Discriminator (D):** Takes either a real image $x$ or a fake image $G(z, t)$, along with the text embedding $t$, and evaluates the probability that the image is real and matches the text description.

### Key Milestones
- **Reed et al. (2016):** The first successful text-to-image GAN architecture using character and word-level text embeddings.
- **StackGAN (2017):** Introduced a multi-stage architecture where Stage-I generated rough shapes and Stage-II refined details.
- **AttnGAN (2018):** Incorporated attention mechanisms to allow the generator to focus on specific sub-words while synthesizing different sub-regions of the image.

### Limitations
- **Volatile Training:** GANs suffer from training instability, requiring careful hyperparameter tuning to balance the generator and discriminator.
- **Mode Collapse:** The generator often learns to produce only a limited set of realistic-looking images (modes), failing to capture the full diversity of the dataset.
- **Limited Global Logic:** Difficulties in capturing complex spatial reasoning or long sentences because of the lack of recursive structures or stable global density mapping.

---

[↩ Back to Main README](../README.md)
