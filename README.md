# Parti

## Introduction

<a href="https://parti.research.google" target="_blank">![website](https://img.shields.io/badge/website-blue)</a>

We introduce the Pathways Autoregressive Text-to-Image model (Parti), an
autoregressive text-to-image generation model that achieves high-fidelity
photorealistic image generation and supports content-rich synthesis involving
complex compositions and world knowledge. Recent advances with diffusion models
for text-to-image generation, such as Google’s
<a href="https://imagen.research.google/" target="_blank">Imagen</a>, have also
shown impressive capabilities and state-of-the-art performance on research
benchmarks. Parti and Imagen are complementary in exploring two different
families of generative models – autoregressive and diffusion, respectively –
opening exciting opportunities for combinations of these two powerful models.

Parti treats text-to-image generation as a sequence-to-sequence modeling
problem, analogous to machine translation – this allows it to benefit from
advances in large language models, especially capabilities that are unlocked by
scaling data and model sizes. In this case, the target outputs are sequences of
image tokens instead of text tokens in another language. Parti uses the powerful
image tokenizer,
<a href="https://doi.org/10.48550/arXiv.2110.04627" target="_blank">ViT-VQGAN</a>,
to encode images as sequences of discrete tokens, and takes advantage of its
ability to reconstruct such image token sequences as high quality, visually
diverse images.

We observed the following results:

*   Consistent quality improvements by scaling Parti’s encoder-decoder up to 20
    billion parameters.
*   State-of-the-art zero-shot FID score of 7.23 and finetuned FID score of 3.22
    on MS-COCO.
*   Effectiveness across a wide variety of categories and difficulty aspects in
    our analysis on Localized Narratives and PartiPrompts, our new holistic
    benchmark of 1600+ English prompts that we release as part of this work.

![parti-overview](https://raw.githubusercontent.com/google-research/parti/main/images/parti_overview.jpeg)

## PartiPrompts benchmark

PartiPrompts benchmark PartiPrompts (P2) is a rich set of over 1600 prompts in
English that we release as part of this work. P2 can be used to measure model
capabilities across various categories and challenge aspects.

![parti-prompts](https://raw.githubusercontent.com/google-research/parti/main/images/parti-propmts.png)

P2 prompts can be simple, allowing us to gauge the progress from scaling. They
can also be complex, such as the following 67-word description we created for
Vincent van Gogh’s The Starry Night (1889):

*Oil-on-canvas painting of a blue night sky with roiling energy. A fuzzy and
bright yellow crescent moon shining at the top. Below the exploding yellow stars
and radiating swirls of blue, a distant village sits quietly on the right.
Connecting earth and sky is a flame-like cypress tree with curling and swaying
branches on the left. A church spire rises as a beacon over rolling blue hills.*

## Acknowledgements

Parti is a collaboration that spans authors across multiple
[Google Research](https://research.google/) teams:

Jiahui Yu<sup>\*</sup>, Yuanzhong Xu<sup>†</sup>, Jing Yu Koh<sup>†</sup>, Thang
Luong<sup>†</sup>, Gunjan Baid<sup>†</sup>, Zirui Wang<sup>†</sup>, Vijay
Vasudevan<sup>†</sup>, Alexander Ku<sup>†</sup>, Yinfei Yang, Burcu Karagol
Ayan, Ben Hutchinson, Wei Han, Zarana Parekh, Xin Li, Han Zhang Jason
Baldridge<sup>†</sup>, Yonghui Wu<sup>\*</sup>

<sup>*</sup>Equal contribution <sup>†</sup>Core contribution

We would like to thank Elizabeth Adkison, Fred Alcober, Tania Bedrax-Weiss,
Krishna Bharat, Nicole Brichtova, Yuan Cao, William Chan, Zhifeng Chen, Eli
Collins, Claire Cui, Andrew Dai, Jeff Dean, Emily Denton, Toju Duke, Dumitru
Erhan, Brian Gabriel, Zoubin Ghahramani, Jonathan Ho, Michael Jones, Sarah
Laszlo, Quoc Le, Lala Li, Zhen Li, Sara Mahdavi, Kathy Meier-Hellstern, Kevin
Murphy, Paul Natsev, Paul Nicholas, Mohammad Norouzi, Niki Parmar, Ruoming Pang,
Fernando Pereira, Slav Petrov, Vinodkumar Prabhakaran, Utsav Prabhu, Evan
Rapoport, Keran Rong, Negar Rostamzadeh, Chitwan Saharia, Gia Soles, Austin
Tarango, Ashish Vaswani, Tao Wang, Tris Warkentin, Austin Waters, Ben
Zevenbergen for helpful discussions and guidance, Peter Anderson, Corinna
Cortes, Tom Duerig, Douglas Eck, David Ha, Radu Soricut and Rahul Sukthankar for
paper review and feedback, Erica Moreira and Victor Gomes for help with resource
coordination, Tom Small for designing the Parti watermark, Google ML Data
Operations team for collecting human evaluations on our generated images and
others in the Google Brain team and Google Research team for support throughout
this project.

We would also like to give particular acknowledgments to the Imagen team,
especially Mohammad Norouzi, Chitwan Saharia, Jonathan Ho and William Chan, for
sharing their near complete results prior to releasing Imagen; their findings on
the importance of CF guidance were particularly helpful for the final Parti
model. We also thank the Make-a-Scene team, especially Oran Gafni, for helpful
discussion on CF-guidance implementation in autoregressive models. We thank the
DALL-E 2 authors, especially Aditya Ramesh, for helpful discussion on MS-COCO
evaluation. We also thank the DALL-Eval authors, especially Jaemin Cho, for help
with reproducing their numbers.

## Note

This is not an officially supported Google product.
