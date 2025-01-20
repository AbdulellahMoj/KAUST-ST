# Calculus for Machine Learning - Summary Notes

## Quick Reference Sheet

### Key Concepts
1. **Functions**
   - Linear: f(x) = mx + b
   - Polynomial: f(x) = ax² + bx + c
   - Exponential: f(x) = eˣ
   - Sigmoid: f(x) = 1/(1 + e⁻ˣ)

2. **Limits**
   - Definition: lim(x→c) f(x) = L
   - Key Patterns:
     - lim(x→0) sin(x)/x = 1
     - lim(x→∞) (1 + 1/x)ˣ = e

3. **Derivatives**
   - Power Rule: d/dx(xⁿ) = n·xⁿ⁻¹
   - Product Rule: d/dx(fg) = f'g + fg'
   - Chain Rule: d/dx(f(g(x))) = f'(g(x))·g'(x)

4. **Integrals**
   - Indefinite: ∫f(x)dx = F(x) + C
   - Definite: ∫ₐᵇf(x)dx = F(b) - F(a)

### Machine Learning Applications

1. **Gradient Descent**
   ```
   θnew = θold - η∇J(θ)
   ```
   - η: Learning rate
   - ∇J(θ): Gradient of cost function

2. **Neural Networks**
   - Forward propagation: z = Wx + b
   - Activation functions:
     - ReLU: max(0, x)
     - Sigmoid: 1/(1 + e⁻ˣ)
     - tanh: (eˣ - e⁻ˣ)/(eˣ + e⁻ˣ)

3. **Optimization**
   - First derivative test: f'(x) = 0
   - Second derivative test: f''(x) for min/max

## Detailed Notes

### 1. Function Analysis
- Domain and range considerations
- Continuity requirements
- Common discontinuities
- Applications in ML models

### 2. Derivative Applications
- Rate of change interpretation
- Gradient computation
- Optimization techniques
- Error minimization

### 3. Integration Applications
- Area under curve
- Probability distributions
- Expected value calculations
- Loss function integration

### 4. Multivariable Calculus
- Partial derivatives
- Gradient vectors
- Hessian matrices
- Chain rule for multiple variables

## Study Tips
1. Start with fundamentals before ML applications
2. Practice computational and theoretical problems
3. Implement concepts in code
4. Visualize using plotting tools
5. Connect concepts to ML applications

## Common Pitfalls
1. Forgetting chain rule in complex derivatives
2. Mixing up partial derivative notation
3. Incorrect integral bounds
4. Overlooking domain restrictions
5. Misapplying optimization conditions
