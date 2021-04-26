# 2021_science_fair
Project materials, code, and data for the 2021 BC/Yukon Virtual Science Fair and 2021 Canada Wide Science Fair

# Project Summary
**Abstract**

Every year, around 400 Canadians lose their lives and another 30 000 are injured because of driver fatigue. Clearly, driver fatigue is as concerning of an issue as driving under the influence of drugs & alcohol and distracted driving. However, this issue is further complicated because, unlike drunk driving, there is no established measure of driver fatigue. To address the lack of methods to measure driver fatigue, I created a fully vertically integrated deep learning pipeline to quantitatively measure driver drowsiness through an electrocardiogram (ECG).

**Reasoning**

During my preliminary research, one of the most underdressed and pressing issues I found was the high number of traffic accidents related to drowsiness, something which is completely unregulated today. This pushed me to pursue an innovative solution that could effectively serve as a method to measure and quantify drowsiness, thus allowing for effective regulation

Before starting, I researched potential methods for drowsiness detection. In order to be effective, a solution must be cheap and easy to implement. Furthermore, it must also be accurate and eliminate subjectivity. These design criteria made me choose to use an ECG, as if it can be implemented correctly and with accuracy, it would perfectly fit all the design criteria I have set. Comparatively, this was far better than any other option that was feasible.

**Procedure**

The procedure used in this project is best represented by three main steps. The first step is to collect a large amount of data. This data must be collected over the course of a day, with large variations in drowsiness. I chose to record a 5-minute ECG and a 2-minute ECG every hour from 6 P.M. to 2 A.M. The 5-minute ECG would serve as the training data, and the 2-minute ECG would be used as testing data. The data must be accurate and free of outside biases such as caffeine or activity. As such, before and during the data collection process, I ensured that I was not drinking any form of caffeine, or doing any physically or mentally strenuous task.

Secondly, is the task of processing the data. This involves the process of reading the data from the standard PDF format into a form that the neural network can process. This is accomplished through a series of steps. First, I convert the pdf into a series of images and then into a 3-dimensional boolean array. Then, using a custom function, the data is enumerated and read into a CSV file.

Thirdly is the process of applying a neural network to that data. This involves defining a custom dataset class for the Pytorch DataLoader, as well as setting out a network architecture with different activation functions, layers, and number of nodes. Next is the process of using a training loop with an optimizer to minimise the network loss. Furthermore, my program includes multiple methods of understanding and visualizing the training process, namely an option to save the loss of the neural network into a graph as well as print out the average deviation from the expected value.

Several parameters can also be optimized and tweaked to increase network efficiency and accuracy. This includes the structure of the network itself such as the number and size of the layers and the type of activation function used. This also includes things like the optimizer and loss function used, as well as their parameters like learning rate. Furthermore is how and what data is being given to the network, as cleaner and more consistent data leads to better results.

**Results**

My network showed very low error values with a standard deviation of +- 0.13. Furthermore it proved to be extremely fast during execution taking only 0.11 seconds to iterate over a test dataset of 575 30-second ecgs on my laptop (Intel Core i7-8565U) whilst running using a single thread. This means that aside from accuracy, this neural network has the potential to be run by very small microprocessors on integrated boards, allowing for a vast range of applications.

**Impacts**

This project has the potential to allow for the systematic regulation of drowsiness through measurement. As drowsiness is often underdressed due to its lack of measurement, this project also serves to create acceptable standards on drowsiness by defining what drowsiness is. I would also like to point out that while I used the example of driving to perpetuate my impacts, a properly implemented system potentially has much more far reaching impacts. As this project is meant to be as compact and accessible as possible, it is possible to apply the same techniques to places such as aviation, industry, or even office spaces to increase employee productivity. This project itself is not bound to any specific application.

**Future Plans**

The next steps in this project are very clear. That is, creating a much more broadly applicable model that can be used by other individuals. This would require the collection of a large amount of data from other individuals.
