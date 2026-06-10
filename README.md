# Progetto Data Mining: Classificazione della Pericolosità degli Asteroidi (PHA)

## Obiettivo del Progetto
Questo progetto applica tecniche di Data Mining e Machine Learning per prevedere se un asteroide è fisicamente pericoloso per la Terra (`pha` - Potentially Hazardous Asteroid). L'analisi si basa su una serie di caratteristiche orbitali e fisiche degli asteroidi, come la distanza, il diametro, l'albedo e la magnitudine.

## Struttura dell'Analisi

**1. Esplorazione e Preprocessing dei Dati**
* Pulizia iniziale del dataset: rimozione degli attributi con più dell'80% di valori mancanti e gestione delle istanze con campi `NaN`.
* Analisi esplorativa (EDA): valutazione della distribuzione degli asteroidi vicini alla Terra (NEO) rispetto alla loro pericolosità e studio delle varie classi orbitali.
* Calcolo e interpretazione della Matrice di Correlazione di Pearson per esaminare le relazioni lineari tra le variabili e prevenire problemi di multi-collinearità.

**2. Addestramento dei Modelli di Classificazione**
Sono stati implementati e confrontati molteplici algoritmi, testati dapprima con i loro parametri di default e successivamente ottimizzati:
* **Logistic Regression:** Modello lineare baseline.
* **MLPClassifier (Reti Neurali Artificiali):** Per la cattura di relazioni non lineari.
* **Decision Trees, Random Forest e ExtraTrees:** Modelli basati su alberi decisionali ed ensemble per gestire feature eterogenee.
* **KNN Classifier:** Classificazione basata sulla prossimità ai k-vicini.
* **SGD Classifier:** Modello lineare addestrato con gradiente stocastico.
* **Voting Classifier:** Approccio ensemble per combinare la robustezza di più modelli.

**3. Metriche di Valutazione**
Ogni modello è stato sottoposto a validazione analizzando metriche specifiche per la classificazione binaria:
* **Accuracy, Precision, Recall, F1-Score:** Per determinare il bilanciamento tra falsi positivi e falsi negativi (cruciale nell'individuare oggetti pericolosi).
* **Area Sotto la Curva (AUC) e Curva ROC:** Per quantificare la capacità di discriminazione del modello rispetto a un classificatore casuale.
* **Matrice di Confusione (Confusion Matrix):** Per una visualizzazione dettagliata degli errori di predizione.

## Risultati e Conclusioni
Dalle valutazioni sul Test Set emerge che:
* I modelli **Best MLPClassifier** e **Best LOGClassifier** rappresentano le scelte più solide, combinando buone prestazioni (F1-score attorno a 0.79/0.80) con un rischio molto basso di *overfitting*.
* L'approccio ensemble tramite **Voting Classifier** si dimostra utile per massimizzare la robustezza, compensando le debolezze dei singoli classificatori.
* Modelli come ExtraTrees raggiungono velocità di addestramento elevate mantenendo ottime prestazioni, superando in alcuni contesti il Random Forest classico.

## Tecnologie e Librerie Utilizzate
* Linguaggio: `Python 3`
* Elaborazione Dati: `pandas`, `numpy`
* Visualizzazione: `matplotlib`, `seaborn`
* Machine Learning: `scikit-learn`, `scipy`
