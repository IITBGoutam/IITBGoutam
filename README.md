# Goutam Singh

Materials Science undergrad at **IIT Bombay**, with a minor in Machine Learning
& Data Science.

I like problems where the interesting part is the measurement, not just the
build — does the fine-tuned model actually beat the baseline, does the lock-free
path actually lower latency. Most of what's here started as a question I
couldn't answer by reading.

---

### Selected work

**[phi3-writing-style-lora](https://github.com/IITBGoutam/phi3-writing-style-lora)** · Python, PEFT, transformers
LoRA fine-tune of Phi-3-mini-4k-instruct to reproduce a specific author's
writing style from only 75 samples. **Beats few-shot-prompted GPT-5 by +0.12
SBERT cosine similarity** (0.58 → 0.70). The trick was generating neutral
counterparts for each sample, turning an unpaired style corpus into a
supervised rewriting task.

**[multithreaded-limit-order-book](https://github.com/IITBGoutam/multithreaded-limit-order-book)** · C++17
Single-symbol limit order book with price-time priority matching, fed by a
producer–consumer pipeline over a bounded blocking queue written from scratch
(mutex + condition variables). Includes a latency benchmark harness and a
written post-mortem of a single-condvar deadlock.

**[vehicle-Insurance-_mlops](https://github.com/IITBGoutam/vehicle-Insurance-_mlops)** · Python, MongoDB, AWS, Docker
End-to-end MLOps pipeline — ingestion from MongoDB, validation, transformation,
training, evaluation and model push to S3, wired to a GitHub Actions workflow
deploying to AWS.

**[flappy-bird-reinforcement-learning](https://github.com/IITBGoutam/flappy-bird-reinforcement-learning)** · PyTorch
DQN agent trained in a custom Gymnasium environment built from scratch with
pygame.

**[leetcode-profile-comparator](https://github.com/IITBGoutam/leetcode-profile-comparator)** · Python
Diffs two LeetCode profiles to surface exactly which problems you haven't
solved that someone else has — filterable by difficulty, topic and rating.
CLI plus a local web UI.

---

### Working with

`Python` · `C++17` · `PyTorch` · `transformers` / `PEFT` · `scikit-learn`
`Docker` · `AWS` · `MongoDB` · `GitHub Actions` · `DVC`

📫 23b2428@iitb.ac.in
