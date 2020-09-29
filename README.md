# Covid-19-Detection
Detecting Covid-19 from X-ray Images.

---

## X-ray Dataset:
* Dataset of X-ray Images are taken from [Kaggle](https://www.kaggle.com/praveengovi/coronahack-chest-xraydataset)

---

## Picking Images:
* Here, I have manually chosen images of Covid-19 and Normal State.
* Entire model is trained on total around 400 images.
* For testing, I have used around 50 images.

## Model:
* Below is the model that I have created.
<img src="https://github.com/manthanpatel98/Covid-19-Detection/blob/master/images/covid.h5.png" height="700">

* If you also want to visualize your model check [Netron](https://lutzroeder.github.io/netron/).

### Understanding the Model:

#### Input Image:
* Here, the input image is (224,224,3) which means image is (224,224) size with RGB color.

#### Layers:
* **Conv2D Layer(3,3,3,32):** Conv2D Layer contains 32 kernels, size (3,3) **====>** Output: 32 images of size (222,222).
* **Conv2D Layer(3,3,32,64):** Conv2D Layer contain 64 kernels, size (3,3) **====>** Output: 64 images of size (220,220).
* **MaxPool2D Layer (3,3):**  MaxPool2D Layer is applied with (3,3) pool-size **====>** Output: 64 images of size (73,73).
* **Dropout Layer**
* **Conv2D Layer(3,3,64,64):** Conv2D Layer contain 64 kernels, size (3,3) **====>** Output: 64 images of size (71,71).
* **MaxPool2D Layer (3,3):**  MaxPool2D Layer is applied with (3,3) pool-size **====>** Output: 64 images of size (23,23).
* **Dropout Layer**
* **Conv2D Layer(3,3,64,128):** Conv2D Layer contain 128 kernels, size (3,3) **====>** Output: 128 images of size (21,21).
* **MaxPool2D Layer (3,3):**  MaxPool2D Layer is applied with (3,3) pool-size **====>** Output: 128 images of size (7,7).
* **Dropout Layer**
* **Flatten Layer**: This will flatten all the (7,7,128) images **====>** Output: (6272).
* **Dense Layer(6272,128):** Here Flattened array will be passed to 128 neurons in the Hidden Layer with applying 'relu' Activation Function **====>** Output: (128).
* **Dense Layer(128,2):** Output of 128 Neurons is passed to 2 Neurons with Activation Function 'softmax' which will help in deciding final output. **====>** Output: (2).







