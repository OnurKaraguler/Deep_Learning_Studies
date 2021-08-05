## Rock Paper Scissors Dataset

Rock Paper Scissors contains images from various hands, from different races, ages, and genders, posed into Rock / Paper or Scissors and labeled as such. Pictures use a plain white background. Each image is 300×300 pixels in 24-bit color.

<img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128369190-0f91408c-07b3-4f2f-92aa-112b34cf0c68.png"> <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128369291-dad36fbc-d21e-49f8-8929-ce1ac383fe82.png"> <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128369363-ca34eaf8-68b8-4326-89de-f899470adcd3.png">


The study consists of:<br>
(1) Import Packages<br>
(2) Load Dataset<br>
  <ul>
      <li>The dataset downloaded from tensorflow_datasets</li>
      <li>The model trained with 2520 images and tested with 372 images</li>
  </ul>
(3) Data Preprocessing<br>
  <ul>
      <li> Image that are 300×300 pixels in 24-bit color converted to grayscale images, resized to 28×28 pixels and normalized </li>
      <img height="150" alt="image" src="https://user-images.githubusercontent.com/58983814/128373627-ff4c7f2a-6216-43b8-b45d-e916644129e3.png">
  </ul>
(4) Train Network<br>
  <ul>
      <li> The Sequential model</li>
      <li> Conv2D (2D Convolutional Neural Network_CNN)</li>
  </ul>

  4.1 Basic approach<br>
  4.2 Convolutional approach<br>
(5). Evaluation of the model<br>
  5.1 Confusion matrix and metrics<br>
(6). Save and load the model<br>
(7). References<br>

