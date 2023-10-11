# 01-The mechanics of learning

> PyTorch Documentation: <https://pytorch.org/docs/stable/index.html>

## Tensor

The word ***tensor*** refers to the overall concept of an **n-dimensional array**.

- A zero-dimensional array is called a **scalar** (e.g., 3.14).
- A one-dimensional array is a **vector** (e.g., [1.9, 2.6, 3.1, 4.0, 5.5]).
- A two-dimensional array is a **matrix**.

> When writing out the dimensions of a tensor like `(B,C,W,H)`, we often use single-letter names with common notations or meanings behind the letters:
> - `B` — The number of batches being used.
> - `D` or `H` — The number of neurons/outputs in a hidden layer (sometimes `N` is also used for this).
> - `C` — The number of channels in an input (e.g., think of “Red, Green, Blue” as three channels) or the number of classes/categories that a model could output.
> - `W` and `H` — The width and height of an image (almost always in conjunction with a `C` dimension for the channels of an image).
> - `T` — The number of items in a sequence.

---

## Gradient descent

The **loss function** is defined as *`l(x)`*, where *x* are the inputs to the network and *`l(x)`* gives us the loss the network received.
The **derivative** is generally defined with respect to a **single variable**, but our networks will have many variables (parameters). When getting the **derivative with respect to multiple variables**, we call it a **gradient**; you can apply the same intuition about derivatives over one variable to gradients over many variables.

![gradient descent](_assets/_images/gradient%20descent.svg ':size=600')

The process to minimize a function *f(x)* using its derivative *f′(x)* is called **gradient descent**. We move *x* in the **opposite** direction of the derivative (
    <code style="font-style: italic;">x<sub>cur</sub> = x<sub>cur</sub> - η·f′(x<sub>cur</sub>)</code>.
    The value *`η`* is called the **learning rate** or **step size**
).
You can also stop early if you have done a lot of updates: “close enough is good enough” holds true for deep learning, and we rarely need to perfectly minimize a function.

---

## PyTorch

The foundational tools that PyTorch provides:
- A **NumPy-like** tensor API, which supports GPU acceleration
- **Automatic differentiation**, which lets us solve optimization problems
- An abstraction for **datasets**

---

?> Update on: 📅 {docsify-updated}