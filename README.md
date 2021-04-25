# Introduzione
Hai mai guardato le foto delle tue vacanze chiedendoti: *qual è il nome di questo tempio che ho visitato in Cina? Chi ha creato questo monumento che ho visto in Francia?*  :japanese_castle::tokyo_tower: \
In questi casi il **Landmark Recognition** può aiutare!  :muscle:\
Questa tecnologia può prevedere le label delle località direttamente dai pixel dell'immagine, aiutando gli utenti ad organizzare meglio le proprie raccolte di foto.

# Problema ed Approccio
Il dataset su cui abbiamo lavorato deriva dalla Google Landmark Recognition Challenge che si è svolta su Kaggle: in questa sfida i partecipanti hanno cercato di realizzare un modello che riuscisse a classificare correttamente le immagini messe a disposizione, prevedendo i landmark_ID corrispondenti ai luoghi in cui la fotografia è stata scattata.

![Google Landmark Recognition_Challenge](https://user-images.githubusercontent.com/39646018/60909844-e7427180-a29c-11e9-84c3-4247cf61e4da.png)

I dati di addestramento per il riconoscimento dei landmark contenevano originariamente oltre 1,2 milioni di immagini, corrispondenti a circa 15.000 classi: per un totale complessivo di 90Gb!  :scream_cat:\
Viste le spaventose dimensioni del dataset di partenza, abbiamo deciso di concentrarci su un task più semplice, riducendo il numero di luoghi da riconoscere: nel nostro caso infatti, i landmark considerati sono solamente 100.

Non avendo a disposizione grandi risorse di calcolo, per l’addestramento delle reti abbiamo utilizzato *Google Colab*, una interessante piattaforma che, seppur con alcune limitazioni, ci ha permesso di eseguire codice direttamente sul Cloud, sfruttando la potenza di calcolo fornita da Google.


<img src="https://miro.medium.com/max/1020/1*lk3xo4jdkQ2SHKRRDFxYHw.jpeg" width="300" height="300">

# Prima fase
Un primo problema che abbiamo dovuto affrontare  è stato quello di **scaricare le immagini** che costituiscono il dataset: all’inizio infatti avevamo a disposizione solo gli *URL* e volevamo ottenere le foto corrispondenti, organizzandole in diverse *directory* in base al landmark di appartenenza. \
Successivamente, abbiamo utilizzato una particolare libreria Python, chiamata **[split-folder](https://pypi.org/project/split-folders/)** la quale ci ha permesso di splittare il dataset iniziale in Training Set (*80%*), Validation Set (*10%*) e Test Set (*10%*).\
Il codice relativo a questa **prima fase** del progetto si trova all'interno di *[Data Loader.ipynb](https://github.com/francoMarini/Landmark-Recognition/blob/master/Data%20Loader.ipynb)*.

# Seconda fase
Le tecnologie che abbiamo deciso di utilizzare per il nostro progetto sono le librerie di *Tensorflow* e *Keras*, in quanto permettono di operare ad un livello di astrazione maggiore. In particolare, la seconda ci ha notevolmente colpito, perché oltre ad offrire un’implementazione leggibile ed intuitiva, mette a disposizione diversi modelli già pre-addestrati utilizzando *ImageNet*, un dataset molto famoso nell’ambito del riconoscimento degli oggetti, grazie alle sue 20.000 categorie molto comuni e varie.\
Dopo aver scoperto questo aspetto interessante di Keras, riflettendoci, abbiamo ipotizzato che utilizzare il **Transfer Learning** potesse essere una strategia vincente, perché ci avrebbe permesso di addestrare le nostre architetture semplicemente mettendo a punto modelli pre-addestrati, risparmiando notevoli tempi di calcolo, necessari se avessimo deciso di addestrare le reti da zero. \
Ricordiamo che questa tecnica consente di riutilizzare gran parte dei parametri di una rete neurale già addestrata in precedenza su un problema simile a quello che dobbiamo risolvere, soffermandoci sull’addestramento solo degli ultimi layer, che sono solitamente quelli dedicati alla classificazione delle feature ottenute con i layer precedenti. 

Dopo aver effettuato una ricerca sulle diverse architetture CNN disponibili, ci siamo concentrati su quattro in particolare:
* *ResNet50*
* *MobileNet*
* *EfficientNetB0*
* *Xception*

Nella realizzazione del nostro progetto, abbiamo cercato di ottimizzare le vari architetture di rete neurale selezionate, attraverso un *tuning* manuale degli iperparametri, con lo scopo di ottenere almeno un modello in grado di garantire un’accuratezza vicina al 90%.

<img src="https://i.ibb.co/GV9MYCN/tartarughe-ninja.jpge">


# Valutazioni
Gli obiettivi che ci eravamo prefissati sono stati pienamente raggiunti, ottenendo ben **quattro modelli** con prestazioni nettamente superiori alle aspettative.

<img src="https://i.ibb.co/R20T7Pb/grafico.jpg">

Inoltre, abbiamo deciso di salvare le nostre migliori reti con tutti i pesi già addestrati all’interno della cartella `Models` [*[Download](https://drive.google.com/drive/folders/1Dp0MlYsGVkBI2YdhRVNYvDBs627teZYt?usp=sharing)*]: in questo modo potrete divertirvi ad utilizzarle subito, senza dover attendere il tempo per il training.

*Tanoshinde kudasai* :roller_coaster: :confetti_ball:





