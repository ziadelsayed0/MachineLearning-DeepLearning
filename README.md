# MachineLearning-DeepLearning
<h2 id="Fine-Tuning-MARBERT-for-Multiclass-Text-Classification-For-Arabic-Language">Fine Tuning MARBERT for Multiclass Text Classification<a href="https://github.com/ziadelsayed0/MachineLearning-DeepLearning/blob/main/NLP/Topic-Classification-For-Arabic-Language_Marbert_PyTorch_Fine_tuning.ipynb" class="anchor-link">¶</a></h2>
<ur>
  <li><h3><Model - 'MARBERT'</h3></li>
  <li>Dataset <h3>called 'MergedTopics' collected from separated text files</h3></li>
</ur>
<div data-mime-type="text/markdown" class="jp-RenderedHTMLCommon jp-RenderedMarkdown jp-MarkdownOutput">
<h2 id="First-What-is-BERT?">First What is BERT?</h2><p>BERT stands for Bidirectional Encoder Representations from Transformers. The name itself gives us several clues to what BERT is all about.</p>
<p>BERT architecture consists of several Transformer encoders stacked together. Each Transformer encoder encapsulates two sub-layers: a self-attention layer and a feed-forward layer.</p>
<h3 id="There-are-two-different-BERT-models:">There are two different BERT models:</h3><ul>
<li><p>BERT base, which is a BERT model consists of 12 layers of Transformer encoder, 12 attention heads, 768 hidden size, and 110M parameters.</p>
</li>
<li><p>BERT large, which is a BERT model consists of 24 layers of Transformer encoder,16 attention heads, 1024 hidden size, and 340 parameters.</p>
</li>
</ul>
<p>BERT Input and Output
BERT model expects a sequence of tokens (words) as an input. In each sequence of tokens, there are two special tokens that BERT would expect as an input:</p>
<ul>
<li>[CLS]: This is the first token of every sequence, which stands for classification token.</li>
<li>[SEP]: This is the token that makes BERT know which token belongs to which sequence. This special token is mainly important for a next sentence prediction task or question-answering task. If we only have one sequence, then this token will be appended to the end of the sequence.</li>
</ul>
<p>It is also important to note that the maximum size of tokens that can be fed into BERT model is 512. If the tokens in a sequence are less than 512, we can use padding to fill the unused token slots with [PAD] token. If the tokens in a sequence are longer than 512, then we need to do a truncation.</p>
<p>And that’s all that BERT expects as input.</p>
<p>BERT model then will output an embedding vector of size 768 in each of the tokens. We can use these vectors as an input for different kinds of NLP applications, whether it is text classification, next sentence prediction, Named-Entity-Recognition (NER), or question-answering.</p>
<hr>
<p><strong>For a text classification task</strong>, we focus our attention on the embedding vector output from the special [CLS] token. This means that we’re going to use the embedding vector of size 768 from [CLS] token as an input for our classifier, which then will output a vector of size the number of classes in our classification task.</p>
<hr>
<p><img data-canonical-src="https://imgur.com/NpeB9vb.png" alt="Imgur" src="https://camo.githubusercontent.com/96067cf91537b008231c93548384430e33ad4a183d57051317e907f89f7d4ea8/68747470733a2f2f696d6775722e636f6d2f4e7065423976622e706e67"></p>
<hr>
</div>
