### Exercises

#### Exercise 1.9

Each of the following two functions defines a method for adding two positive integers in terms of the functions inc, which increments its argument by 1, and dec, which decrements its argument by 1.

```lisp
(defun add (a b)
  (if (== a 0)
      b
      (inc (+ (dec a) b))))

(defun add (a b)
  (if (== a 0)
      b
      (+ (dec a) (inc b))))
```

Using the substitution model, illustrate the process generated by each function in evaluating ``(+ 4 5)``. Are these processes iterative or recursive? 

#### Exercise 1.10

The Ackermann function is defined as

$$
A(m, n) =
\begin{cases}
n+1 & \mbox{if } m = 0 \\
A(m-1, 1) & \mbox{if } m > 0 \mbox{ and } n = 0 \\
A(m-1, A(m, n-1)) & \mbox{if } m > 0 \mbox{ and } n > 0.
\end{cases}
$$

Here is the function in LFE:

```lisp
(defun ackermann
  ((0 n) (+ n 1))
  ((m 0) (ackermann (- m 1) 1))
  ((m n) (ackermann (- m 1) (ackermann m (- n 1)))))
```

What are the values of the following expressions?

```lisp
(ackermann 1 10)
(ackermann 2 4)
(ackermann 3 3)
```

Consider the following functions, where ``ackermann`` is the function defined above:

```lisp
(defun f (n) (ackermann 0 n))

(defun g (n) (ackermann 1 n))

(defun h (n) (ackermann 2 n))

(defun k (n) (* 5 n n))
```

Give concise mathematical definitions for the functions computed by the functions ``f``, ``g``, and ``h`` for positive integer values of ``n``. For example, ``(k n)`` computes $$5n^2$$. 
