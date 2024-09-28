# Text-mining-project

# Analisi del Sentiment delle Recensioni di una Serie TV su IMDb

## Descrizione del Progetto

Questo progetto si occupa dell'analisi del sentiment delle recensioni di una serie TV tratte dal sito IMDb. L'obiettivo è scaricare le recensioni, pre-processarle e classificarle utilizzando tecniche di text mining e machine learning. Inoltre, il progetto esplora la distribuzione delle recensioni in base a vari parametri, come le stelle assegnate dagli utenti.

## Struttura del Progetto

Il progetto è suddiviso in più sezioni, ciascuna dedicata a uno specifico aspetto dell'analisi:

**Scraping delle Recensioni**

**Analisi Descrittiva**

**Bag of Words**

**Word2Vec**

**TF-IDF**

**Finetuning**

**1. Scraping delle Recensioni**

Il primo step è stato l'estrazione automatica delle recensioni da IMDb utilizzando Selenium e BeautifulSoup. È stato implementato uno script per fare il web scraping delle recensioni e raccogliere informazioni come utente, voto (in stelle), data della recensione e testo.

**2. Analisi Descrittiva**

Una volta ottenuti i dati, abbiamo eseguito un'analisi esplorativa. Questa include:

Distribuzione delle recensioni per voto: Un grafico che mostra come sono distribuite le recensioni in base al numero di stelle assegnate dagli utenti.

Distribuzione temporale: Un'analisi dell'evoluzione temporale del numero di recensioni.

Andamento del sentiment: La suddivisione delle recensioni in "positive" (voti ≥ 7) e "negative" (voti < 7), con l'analisi dell'andamento temporale.

Lunghezza del testo delle recensioni: Un confronto tra la lunghezza delle recensioni positive e negative.

Parole più frequenti: Estrazione delle 10 parole e aggettivi più comuni nelle recensioni.

**3. Bag of Words**

Ho utilizzato un approccio di Bag of Words (BoW) per la classificazione del sentiment. Il testo delle recensioni è stato pre-elaborato per rimuovere stopwords e caratteri speciali. Abbiamo poi rappresentato il testo come una matrice di termini (vettorializzazione) e testato diversi modelli di machine learning:

Multinomial Naive Bayes

Support Vector Machine (SVM)

Decision Tree

**4.Word2Vec**

Ho anche implementato un modello di Word2Vec per rappresentare il testo delle recensioni come vettori di parole. Utilizzando i vettori di parola, abbiamo calcolato i vettori di frase e testato i seguenti modelli di classificazione:

Support Vector Machine (SVM)

Random Forest

Decision Tree

Multinomial Naive Bayes

**5.TF-IDF**

Il testo preprocessato viene trasformato utilizzando il modello TF-IDF, che converte ogni recensione in un vettore numerico in base alla frequenza e importanza dei termini nel corpus.
I modelli usati sono stati:

Multinomial Naive Bayes (MultinomialNB)

Support Vector Machine (SVM)

Albero Decisionale (DecisionTreeClassifier)

**6.Modello pre-addestrato senza fine-tuning**

Pipeline pre-addestrato: Viene utilizzata la pipeline sentiment-analysis di Hugging Face basata sul modello pre-addestrato "cardiffnlp/twitter-roberta-base-sentiment". Il modello è in grado di prevedere sentimenti come positivo, negativo e neutro.

**7.Fine-tuning con RoBERTa per 3,10,15 e 20 epoche**

**Tokenizzazione**: Il testo pulito viene tokenizzato usando il tokenizer di RobertaTokenizer in modo da essere utilizzabile dal modello RobertaForSequenceClassification.

**Creazione del dataset**: Viene utilizzata la libreria datasets per creare un dataset compatibile con Hugging Face che contiene il testo tokenizzato e le etichette di sentiment preprocessate.

**Addestramento del modello**:
Viene utilizzato Trainer di Hugging Face per addestrare il modello per 10 epoche con un learning rate di 5e-5.
Il fine-tuning è monitorato da WandB (Weights & Biases) per tracciare le metriche di addestramento.




