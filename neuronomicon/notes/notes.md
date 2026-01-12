# The Neuronomicon

## Biologie

- “One neuron, one Transmitter” - jedes Neuron setzt an allen seinen Synapsen denselben Neurotransmittern frei (Dale-Prinzip, gilt seit Entdeckung von Co-Transmittern nicht mehr)
- Neurotransmitter können erregend (exzitatorisch) oder inhibitorisch auf postsynaptische Zelle wirken - analog zu positiven und negativen Gewichten in ANN

## Analogies

- Skip Connections sind Gradient Super-Highway (Andrew Karpathy)
- Transformer sind Communication (between tokens, by Self-Attention) and Computation (Tokens looked at each other but didn’t had time to think about it, requires feedforward network) - Andrew Karpathy

## Terminology

- Tokenize: convert raw text string to sequence of vocabulary indices as integers
- Super-Convergence: speed up training of neural networks with large learning rates (https://arxiv.org/abs/1708.07120)

## Questions

Warum kann man neuronale Netze nicht analytisch lösen? Wenn wir alle Minima finden, bleiben wir nicht in lokalen Minimum stecken, außerdem können wir uns den Gradientenabstieg sparen…
- für eine Schicht möglich
- kommen sonst nicht durch nichtlinearität durch, konvexe Lösung oder so?

Wie groß muss die Lernrate, Learning Rate sein?
- Andrew Karpathy in “Let’s build GPT from scratch., in code, spelled out.”: usual good learning rate: - 1e-4, but for small networks, you could get away with a higher rates like 1e-3
- Bei größeren Netzen machen größere Lernraten das Training instabil, da sich Neuronen gegenseitig beeinflussen
- Learning Rate kann Performance eines Neuronalen Netzes extrem beeinflussen - dasselbe Netz, dass mit niederiger Lernrate perfekte Genauigkeit erreicht, lernt mit größerer Lernrate gar nichts

## Papers

Szegedy et al.: "Intriguing Properties of Neural Networks" (2014)
- semantic meaning seems to be encoded in embedding space rather than in individual high-level neurons
- deep neural networks have "blind spots", allows to compute adversarial examples
- proposal of upper Lipschitz constant as a measure of neural network instability
- (Lipschitz constant of a layer seems to be related to the norm of the weight matrix)

## Other

Notizen

- Falls bei PyTorch ein Modell eine Liste von Modulen (zum Beispiel Hidden Layer) besitzt, sollte ModuleList aus torch.nn verwendet werden! Werden die Schichten stattdessen in einer normalen Liste gespeichert, erkennt Torch nicht automatisch die Parameter. Diese Schichten werden also sonst nicht optimiert.
