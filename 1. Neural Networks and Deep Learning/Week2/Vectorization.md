## Vectorization

Avoid for loops, use vectors instead

Before Vectorization

![alt text][logo14]

[logo14]: 14.png "14"

After Vectorization

![alt text][logo15]

[logo15]: 15.png "15"

## Broadcasting in Python

Vertical Axis = `axis=0`

Horizontal Axis = `axis=1`

`np.sum(axis=0)` means it collapses on the row, hence adding them column wise

![alt text][logo16]

[logo16]: 16.png "16"

Applying mathematical operations on an `(m,n)` matrix with a `(1,n)` matrix, will transform `(1,n)` matrix to a `(m,n)` matrix.

Applying mathematical operations on an `(m,n)` matrix with a `(m,1)` matrix, will transform `(m,1)` matrix to a `(m,n)` matrix.

Applying mathematical operations on an `(m,1)` matrix with a `(1,1)` matrix, will transform `(1,1)` matrix to a `(m,1)` matrix.

Applying mathematical operations on an `(1,n)` matrix with a `(1,1)` matrix, will transform `(1,1)` matrix to a `(1,n)` matrix.

## Other Notes on Broadcasting

Don't use Rank matrices `(5,)`. Instead, use proper matrix `(5,1)`

`a = np.random.randn(5)` <-- No

`a = np.random.randn(5,1)` <-- Yes
