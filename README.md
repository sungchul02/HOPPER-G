# HOPPER-G: Title-Mention Path Contexts for Small Language Models

> **Status:** research in progress (follow-up to [HOPPER](https://github.com/sungchul02/HOPPER)). Code will be released with the paper (공개 예정).

HOPPER-G is a training-free method that builds the input context for small 4-bit language models in multi-hop question answering. It links the documents in the context into a graph (document A → document B when a sentence of A mentions the title of B), starts from a document whose title the question mentions, follows a path of at most three documents, and gives the model the sentences on that path. When no such path exists, it uses the sentences selected by HOPPER. Context construction runs on a CPU without neural model calls or training.

The paper is organized by condition rather than by dataset. It examines when the path context helps: the expected case is a question whose path covers all gold documents, typically a 2-hop question in which the question names the first document and that document names the second. Single-hop questions, collections without title mentions and chains of three or more hops are reported as conditions outside this scope. Results will be reported with the paper.

**The code will be added when the paper is released.** It will include the context construction code, prompts, evaluation question IDs, model digests and run records.

**Research line**

| Work | Topic | Status |
|---|---|---|
| [HOPPER](https://github.com/sungchul02/HOPPER) | Training-free sentence extraction for small models | Accepted (IJIBC) |
| HOPPER-G (this repository) | Title-mention path contexts and the conditions under which they help | In progress |
| Conditional compressor | Path rules chosen by link type, hop count and model size; evaluation on real retrieval; budget rule; comparison with model-based document selection | Planned |
| Offline maintenance-document QA | Application to documents that cite each other by section number | Planned |

Related: [WHEN-TO-COMPRESS](https://github.com/sungchul02/WHEN-TO-COMPRESS) (compression budget and input length for small models) and [AGENT-CONTEXT](https://github.com/sungchul02/AGENT-CONTEXT) (document selection for multi-step agents).

---

HOPPER-G는 멀티 홉 질의응답에서 4비트 소형 언어모델의 입력 문맥을 구성하는 방법이며, 학습이 필요 없다. 문맥 안의 문서 사이에 제목 언급 관계로 그래프를 만들고, 질문이 제목을 언급한 문서에서 출발하는 최대 3개 문서의 경로 위 문장을 입력한다. 경로가 없으면 HOPPER가 고른 문장을 쓴다. 압축은 신경망 호출 없이 CPU에서 동작한다.

논문은 데이터셋별이 아니라 조건별로 구성하였다. 이득은 경로가 정답 문서를 모두 담는 질문, 주로 질문이 첫 문서를 언급하고 그 문서가 둘째 문서를 언급하는 2홉 질문에서 기대하며, 단일 홉 질문, 제목 언급이 없는 문서, 3홉 이상의 질문은 범위 밖 조건으로 보고한다. 결과는 논문과 함께 공개한다. [HOPPER](https://github.com/sungchul02/HOPPER)의 후속 연구로 현재 진행 중이며, **코드는 논문 공개 시 이 저장소에 기재한다**. 후속으로는 연결 유형, 홉 수, 모델 크기에 따라 경로 규칙을 고르는 조건형 압축기와, 조항 번호로 서로 참조하는 정비 문서에 적용하는 연구를 계획하고 있다.
