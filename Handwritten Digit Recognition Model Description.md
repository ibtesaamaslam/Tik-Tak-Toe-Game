## Handwritten Digit Recognition Model

During my internship at DigitalEmpowerment Pakistan, I successfully completed a task of developing a Handwritten Digit Recognition Model. This project honed my skills in Python programming, implementing machine learning algorithms, and handling data preprocessing and feature extraction. The model features accurate digit recognition, robust data handling, and effective use of deep learning techniques.

### Features

- **Digit Recognition**: Classify handwritten digits with high accuracy.
- **Pre-trained Models**: Utilize pre-trained models for robust and accurate digit recognition.
- **Sample Dataset**: Includes examples of handwritten digits for demonstration purposes.

### Installation

To get started, clone this repository and install the required dependencies:

```bash
git clone https://github.com/your-username/Handwritten-Digit-Recognition.git
cd Handwritten-Digit-Recognition
pip install -r requirements.txt
```

### Usage

1. **Run the Script**: Use the provided script to perform digit recognition on sample images.

   ```python
   import torch
   from torchvision import datasets, transforms
   from torch import nn, optim
   import matplotlib.pyplot as plt

   # Define a transform to normalize the data
   transform = transforms.Compose([transforms.ToTensor(),
                                   transforms.Normalize((0.5,), (0.5,))])

   # Download and load the training data
   trainset = datasets.MNIST('~/.pytorch/MNIST_data/', download=True, train=True, transform=transform)
   trainloader = torch.utils.data.DataLoader(trainset, batch_size=64, shuffle=True)

   # Define the model
   class SimpleNN(nn.Module):
       def __init__(self):
           super(SimpleNN, self).__init__()
           self.hidden = nn.Linear(784, 128)
           self.output = nn.Linear(128, 10)

       def forward(self, x):
           x = x.view(x.shape[0], -1)
           x = torch.relu(self.hidden(x))
           x = self.output(x)
           return x

   model = SimpleNN()

   # Define the loss and optimizer
   criterion = nn.CrossEntropyLoss()
   optimizer = optim.SGD(model.parameters(), lr=0.003)

   # Train the model
   epochs = 5
   for e in range(epochs):
       running_loss = 0
       for images, labels in trainloader:
           optimizer.zero_grad()
           output = model(images)
           loss = criterion(output, labels)
           loss.backward()
           optimizer.step()
           running_loss += loss.item()
       else:
           print(f"Training loss: {running_loss/len(trainloader)}")

   # Save the model
   torch.save(model.state_dict(), 'handwritten_digit_model.pth')

   # Load the model
   model.load_state_dict(torch.load('handwritten_digit_model.pth'))

   # Test the model
   def predict_digit(image):
       with torch.no_grad():
           output = model(image)
           _, predicted = torch.max(output, 1)
           return predicted.item()

   # Display a sample image and prediction
   images, labels = next(iter(trainloader))
   plt.imshow(images[0].numpy().squeeze(), cmap='gray_r')
   plt.title(f'Predicted Digit: {predict_digit(images[0])}')
   plt.show()
   ```

2. **Notebook**: Alternatively, you can explore the project using the provided Jupyter notebook `Hand Written Digit Recognition Model.ipynb`.

### Dependencies

- `torch`
- `torchvision`

### Contributing

Contributions are welcome! If you have any suggestions or improvements, feel free to open an issue or submit a pull request.

### License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

### Acknowledgments

- PyTorch for providing the deep learning framework and tools.
