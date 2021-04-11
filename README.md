# Introduzione
Hai mai guardato le foto delle tue vacanze chiedendoti: *qual è il nome di questo tempio che ho visitato in Cina? Chi ha creato questo monumento che ho visto in Francia?*\
In questi casi il **Landmark Recognition** può aiutare! \
Questa tecnologia può prevedere le label delle località direttamente dai pixel dell'immagine, aiutando gli utenti ad organizzare meglio le proprie raccolte di foto.

# Problema ed Approccio
Il dataset su cui abbiamo lavorato deriva dalla Google Landmark Recognition Challenge che si è svolta su Kaggle: in questa sfida i partecipanti hanno cercato di realizzare un modello che riuscisse a classificare correttamente le immagini messe a disposizione, prevedendo i landmark_ID corrispondenti ai luoghi in cui la fotografia è stata scattata.

![Google Landmark Recognition_Challenge](https://user-images.githubusercontent.com/39646018/60909844-e7427180-a29c-11e9-84c3-4247cf61e4da.png)

I dati di addestramento per il riconoscimento dei landmark contenevano originariamente oltre 1,2 milioni di immagini, corrispondenti a circa 15.000 classi: per un totale complessivo di 90Gb!\
Viste le spaventose dimensioni del dataset di partenza, abbiamo deciso di concentrarci un task più semplice, riducendo il numero di luoghi da riconoscere: nel nostro caso infatti, i landmark considerati sono solamente 100.

Non avendo a disposizione grandi risorse di calcolo, per l’addestramento delle reti abbiamo utilizzato *Google Colab*, una interessante piattaforma che, seppur con alcune limitazioni, ci ha permesso di eseguire codice direttamente sul Cloud, sfruttando la potenza di calcolo fornita da Google.


<img src="https://miro.medium.com/max/1020/1*lk3xo4jdkQ2SHKRRDFxYHw.jpeg" width="300" height="300">
