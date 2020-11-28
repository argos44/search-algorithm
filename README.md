
%Initialize two vaariables, a single integer type number 
%(occupying 3 bytes in memory, plus the value of the integer, which is equalling to the databye of an integer data type)
%And an integer vector, consisting of 16 elements (16 single integer type numbers in a row)
x = 4;
y = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16];


%for i = 1:length(y)
%  disp(y(i));
%endfor

%was just testing the syntax

%serial search subroutine
%find x in y[]

%for i = 1:length(y)
%  if(y(i) == x)  %note, that it does matter logically, witch side of the equation x is on
%    disp("the elment number equalling to x is:"),disp(i);
%    break;
%  endif
%endfor

%binary, or logarithmic search subroutine
%find x in y[]

for i = 1:length(y) %binary or logarithmic search is requiring way fewer iterations, or steps than serial. SO, in this case 16 iterations would be fine.
  %though a good programmer with time would find a way to reduce unnecessary, never used iterations
  
  if(y(length(y)/2) > x)  %y(element number)     length(y)/2 is the middle point, in this case 8, because length(y) is 16
    
    disp(y(length(y)/2));
    
    tmp = y;
    y = tmp(1:length(y)/2); %slice the row vector at the breakpoint (at the middle)
    
    %note, that y row vector's RANGE is changed, not the row vector itself. I'm not sure if any other way would be stable.
    %Imagine saving a data file to a casette player, or ZX spectrum microdrive (slow), AND editing it at the same time. Not really a good idea.
  
  endif
  
  if(y(length(y)/2) < x) 

    disp(y(length(y)/2));

    tmp = y;
    y = tmp(length(y)/2):length(y);
  
  
  endif
  
   if(y(length(y)/2) == x)  
    disp("element found"), disp(y(length(y)/2));
    break; break;
  endif

endfor

