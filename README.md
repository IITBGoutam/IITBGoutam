# Goutam Singh

Materials Science undergrad at **IIT Bombay**, with a minor in Machine Learning
& Data Science.

I like problems where the interesting part is the measurement, not just the
build — does the fine-tuned model actually beat the baseline, does the lock-free
path actually lower latency. Most of what's here started as a question I
couldn't answer by reading.

---

### Selected work

**[cloudstorex](https://github.com/IITBGoutam/cloudstorex)** · TypeScript, PostgreSQL, Kafka, MinIO, Redis
Distributed cloud storage platform — a Drive/Dropbox-style system as an
8-service monorepo. Files are split into 4 MB chunks, gzipped, AES-256-GCM
encrypted, and placed across storage nodes by **consistent hashing with virtual
nodes at replication factor 3**. A replication service watches node heartbeats
and self-heals under-replicated chunks; Kafka carries domain events; Prometheus
and Grafana watch the whole thing. SHA-256 integrity per chunk, resumable
uploads, JWT with refresh-token rotation and Redis-backed revocation.

**[phi3-writing-style-lora](https://github.com/IITBGoutam/phi3-writing-style-lora)** · Python, PEFT, transformers
LoRA fine-tune of Phi-3-mini-4k-instruct to reproduce a specific author's
writing style from only 75 samples. **Beats few-shot-prompted GPT-5 by +0.12
SBERT cosine similarity** (0.58 → 0.70). The trick was generating neutral
counterparts for each sample, turning an unpaired style corpus into a
supervised rewriting task.

**[cellpose-cell-segmentation](https://github.com/IITBGoutam/cellpose-cell-segmentation)** · PyTorch, Cellpose-SAM
Fine-tuning a ViT-scale segmentation foundation model for nucleus detection in
H&E histopathology. Beyond the fine-tune, the model's output head is **replaced
with one emitting `(3 + n_classes) × patch²` channels and reseeded from the
pretrained flow/probability weights** — so 4-class cell typing is learned on top
of a working segmentation model rather than from scratch. Scales to whole-slide
images via OpenSlide tiling.

**[multithreaded-limit-order-book](https://github.com/IITBGoutam/multithreaded-limit-order-book)** · C++17
Single-symbol limit order book with price-time priority matching, fed by a
producer–consumer pipeline over a bounded blocking queue written from scratch
(mutex + condition variables). Includes a latency benchmark harness and a
written post-mortem of a single-condvar deadlock.

**[Airline-Booking-System](https://github.com/IITBGoutam/Airline-Booking-System)** · Node, PostgreSQL, Kafka, Docker
Microservice booking platform — Auth, Flight and Booking services plus a
notification consumer behind an Nginx gateway. **Database-per-service**, with
cross-service references validated over HTTP at request time instead of by
shared foreign keys, and async messaging over Kafka (Redpanda). Load-tested
with k6.

**[option-pricing-neural-networks](https://github.com/IITBGoutam/option-pricing-neural-networks)** · TensorFlow, scikit-learn
Do neural networks price options better than Black-Scholes? Fitted both to the
same 35,591 NSE option contracts and scored against real traded prices: the MLP
**cuts RMSE 3.4× on calls and 6.2× on puts**, by learning the volatility smile
the closed-form model assumes away. Includes an honest write-up of why the
fine-tuning schedule made the call model *worse* after its first checkpoint.

**[vehicle-Insurance-_mlops](https://github.com/IITBGoutam/vehicle-Insurance-_mlops)** · Python, MongoDB, AWS, Docker
End-to-end MLOps pipeline — ingestion from MongoDB, validation, transformation,
training, evaluation and model push to S3, wired to a GitHub Actions workflow
deploying to AWS.

**[leetcode-revision](https://github.com/IITBGoutam/leetcode-revision)** · Python, Gemini
Scrapes your own accepted submissions and distills each into a revision card —
gist, the one key trick, the gotcha, complexity — served from a dependency-free
static page with search and filtering. Runs entirely locally; submissions and
API key never leave the machine.

**[grader-bot-nlp](https://github.com/IITBGoutam/grader-bot-nlp)** · PyTorch, SBERT, TensorFlow
Grades free-text answers by fusing two signals a single model handles badly:
synonym-aware keyword overlap (YAKE/KeyBERT + WordNet, with POS agreement) and
SBERT sentence-level semantic similarity, combined through a small DNN.
Reimplements a published *Expert Systems With Applications* approach.

**[flappy-bird-reinforcement-learning](https://github.com/IITBGoutam/flappy-bird-reinforcement-learning)** · PyTorch
DQN agent trained in a custom Gymnasium environment built from scratch with
pygame.

**[leetcode-profile-comparator](https://github.com/IITBGoutam/leetcode-profile-comparator)** · Python
Diffs two LeetCode profiles to surface exactly which problems you haven't
solved that someone else has — filterable by difficulty, topic and rating.
CLI plus a local web UI.

**[stock-forecasting-deep-learning](https://github.com/IITBGoutam/stock-forecasting-deep-learning)** · TensorFlow, statsmodels
AR, LSTM, GRU and Transformer forecasters on MSFT closes, held to an identical
windowing and rollout so the comparison isolates the architecture. The
attention model wins on the 30-day compounding-error task; a plain AR baseline
is hard to beat at 7 days.

---

### Working with

`Python` · `C++17` · `TypeScript` · `PyTorch` · `transformers` / `PEFT` · `scikit-learn`
`PostgreSQL` · `MongoDB` · `Redis` · `Kafka` · `MinIO`
`Docker` · `AWS` · `GitHub Actions` · `DVC` · `Prometheus` / `Grafana`

📫 23b2428@iitb.ac.in
