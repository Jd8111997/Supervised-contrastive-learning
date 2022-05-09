# Supervised-Contrastive-Learning
Implementation of Supervised Contrastive Learning for pretrained language models[https://arxiv.org/abs/2011.01403].

- In this project, we tried to reproduce the paper results on SST2 and CoLA datasets using Roberta-large model of huggingface.     
- Although, we couldn't reproduce the results for few shot learning tasks(20 and 50 training samples), but when training on whole dataset, we got 1.5% gain on test accuracy, which is sampled from original dev set and it contains 500 samples with equal distribution of labels as per mentioned in the paper.
- All other hyper-parameters are same as given in paper.
- Some of the challenges that we faced is when trying this method on few shot learning setting, the model is started getting overfitted on training set and in the paper, the authors didn't mentioned how they resolve the overfitting issue while training on < 50 samples.    
- We tried dorpout, layer normalization, LeakyReLU activation etc, but it didn't resolve overfitting issue.
- Below are visualizations of learned sentence embeddings of model trained with scl loss and without scl loss.   
- With supervised contrasive loss, we can see that the model is able to seperate out the two clusters(+ve ad -ve sentiment for SST2)
 ![Alt text](./viz/with_scl.png?raw=true "Title")
- Learned sentence embeddings without using supervised contrastive loss.
 ![Alt text](./viz/without_scl.png?raw=true "Title")




