function [root, fx, ea, iter] = falsePosition(func, xl, xu, es, maxit, varargin)
%falsePosition finds the root of a function using false position method
%% The function has 5 possible inputs, each need to be "accounted" for
if nargin < 3
    error('Need more inputs')

elseif nargin < 4
    es = 0.0001;
elseif nargin < 5 
    maxit = 200
    es = 0.0001;
end 
%% Set up new variables 
func_U = func(xu);
func_L = func(xl);
new = xl;
ea = 100;
iter = 0;
%%Check signs on inputs
while func(xl)*func(xu)>0
    error('Input different values for xl and xu')
end
%% Loop for False Position method
while ea > es
    old = new
new = xu-((func_U.*(xl-xu))/(func_L-func_U));
x = new;
f_new = func(new);
   if f_new > 0
       xu = new;
   elseif f_new < 0
       xl = new;
   end 
iter = iter+1;
ea = abs((new-old)/new)*100;
end 

fx = f_new;
root = x
iter = 1; 



end
