function [L, U, P] = luFactor(A)
% luFactor(A)
%	LU decomposition with pivotiing
% inputs:
%	A = coefficient matrix
% outputs:
%	L = lower triangular matrix
%	U = upper triangular matrix
%       P = the permutation matrix
% store the length of square matrix A

[nRows, nCols] = size(A);
if nRows ~= nCols
    error('Input matrix A must be a square matrix');
end

s = length(A);

% Assign first matrix A as U and begin pivoting
U = A;

L = zeros(s,s);
Piv = (0:s-1)';
for j = 1:s,
% Check the values of matrix U
% The maximum numeric value in the column first.
[~,inditi] = max(abs(U(j:s,j)));
inditi = inditi+(j-1);
tri = Piv(j); 
Piv(j)=Piv(inditi); 
Piv(inditi)=tri;
tri = L(j,1:j-1); 
L(j,1:j-1)=L(inditi,1:j-1); 
L(inditi,1:j-1)=tri;
tri = U(j,j:end); 
U(j,j:end)=U(inditi,j:end); 
U(inditi,j:end)=tri;

% LU 
L(j,j) = 1;

% loop to check out the L and U
for i = (1+j):size(U,1)
c = U(i,j)/U(j,j);
U(i,j:s) = U(i,j:s)-U(j,j:s)*c;
L(i,j) = c;
end
end

% This is the matrix that stores the permutation/pivoting matrix
P = zeros(s,s);
P(Piv(:)*s+(1:s)') = 1;

end
