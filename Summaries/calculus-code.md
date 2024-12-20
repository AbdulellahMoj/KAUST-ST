# Calculus Implementations and Projects

## 1. Basic Function Implementations

```python
import numpy as np
import matplotlib.pyplot as plt

def sigmoid(x):
    """Sigmoid activation function"""
    return 1 / (1 + np.exp(-x))

def sigmoid_derivative(x):
    """Derivative of sigmoid function"""
    s = sigmoid(x)
    return s * (1 - s)

def relu(x):
    """ReLU activation function"""
    return np.maximum(0, x)

def relu_derivative(x):
    """Derivative of ReLU function"""
    return np.where(x > 0, 1, 0)

# Visualization
x = np.linspace(-10, 10, 100)
plt.plot(x, sigmoid(x), label='Sigmoid')
plt.plot(x, relu(x), label='ReLU')
plt.legend()
plt.grid(True)
plt.show()
```

## 2. Gradient Descent Implementation

```python
class GradientDescent:
    def __init__(self, learning_rate=0.01):
        self.learning_rate = learning_rate
        
    def update(self, params, grads):
        """Basic gradient descent update"""
        return params - self.learning_rate * grads

class MomentumGD:
    def __init__(self, learning_rate=0.01, momentum=0.9):
        self.learning_rate = learning_rate
        self.momentum = momentum
        self.velocity = None
        
    def update(self, params, grads):
        if self.velocity is None:
            self.velocity = np.zeros_like(params)
        
        self.velocity = self.momentum * self.velocity - self.learning_rate * grads
        return params + self.velocity
```

## 3. Neural Network Implementation

```python
class SimpleNeuralNetwork:
    def __init__(self, input_size, hidden_size, output_size):
        self.W1 = np.random.randn(input_size, hidden_size) * 0.01
        self.b1 = np.zeros((1, hidden_size))
        self.W2 = np.random.randn(hidden_size, output_size) * 0.01
        self.b2 = np.zeros((1, output_size))
        
    def forward(self, X):
        self.z1 = np.dot(X, self.W1) + self.b1
        self.a1 = sigmoid(self.z1)
        self.z2 = np.dot(self.a1, self.W2) + self.b2
        self.a2 = sigmoid(self.z2)
        return self.a2
    
    def backward(self, X, y, output):
        m = X.shape[0]
        
        dz2 = output - y
        dW2 = np.dot(self.a1.T, dz2) / m
        db2 = np.sum(dz2, axis=0, keepdims=True) / m
        
        dz1 = np.dot(dz2, self.W2.T) * sigmoid_derivative(self.z1)
        dW1 = np.dot(X.T, dz1) / m
        db1 = np.sum(dz1, axis=0, keepdims=True) / m
        
        return dW1, db1, dW2, db2
```

## 4. Numerical Methods

```python
def numerical_derivative(f, x, h=1e-7):
    """Calculate derivative using finite difference"""
    return (f(x + h) - f(x)) / h

def numerical_integral(f, a, b, n=1000):
    """Calculate integral using trapezoidal rule"""
    x = np.linspace(a, b, n)
    y = f(x)
    return np.trapz(y, x)
```

## 5. Optimization Problems

```python
def newton_method(f, f_prime, x0, tol=1e-6, max_iter=100):
    """Newton's method for finding roots"""
    x = x0
    for i in range(max_iter):
        fx = f(x)
        if abs(fx) < tol:
            return x
        x = x - fx / f_prime(x)
    return x

def gradient_descent_optimizer(f, grad_f, x0, lr=0.01, tol=1e-6, max_iter=1000):
    """Gradient descent optimization"""
    x = x0
    history = [x]
    
    for i in range(max_iter):
        grad = grad_f(x)
        if np.all(np.abs(grad) < tol):
            break
        x = x - lr * grad
        history.append(x)
    
    return x, history
```

## 6. Example Projects

### Project 1: Linear Regression with Gradient Descent
```python
class LinearRegression:
    def __init__(self, lr=0.01):
        self.lr = lr
        self.weights = None
        self.bias = None
        
    def fit(self, X, y, epochs=100):
        n_samples, n_features = X.shape
        self.weights = np.zeros(n_features)
        self.bias = 0
        
        for _ in range(epochs):
            y_pred = np.dot(X, self.weights) + self.bias
            
            # Gradient descent
            dw = (1/n_samples) * np.dot(X.T, (y_pred - y))
            db = (1/n_samples) * np.sum(y_pred - y)
            
            self.weights -= self.lr * dw
            self.bias -= self.lr * db
```

### Project 2: Neural Network with Backpropagation
[Implementation details available upon request]
