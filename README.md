java c
CSCI   4041   Algorithms   and   Data   Structures   -   Spring   2025 
Homework   1   -   Asymptotic   Runtime
Due Date: Friday,   February   7,   2025   by   11:59pm.Problem H1.1:    Theory -   Answer the   following   questions.   You   should   prove these   formally   using   definitions    and   theorems   from   the   textbook   or   class    (e.g.       Definitition    of    Big-O,    Big-Ω,    Big-Θ,   Asymptotic   Limit   Theorem,   etc...).
(a) Prove: ∀a   ∈   R, a   >   1,   loga   n   = Θ(lgn)   (*Practice   Problem*)
(b) Prove: f   = Θ(g)   if   and   only   if   f   =   O(g)   and   f   =   Ω(g).    (*Practice   Problem*)
(c)   Let   f(n)   = 2n2    +   7n −   1.   Show   that   f   = O(n3   ).    (*Practice   Problem*)
(d) Prove: n+1/n3(2+sinn) +   7n +   3   = Θ(g(n)),   for   some   function   g(n).Problem H1.2: Runtime -   Give   Θ(f(n))   complexity   for   the   following   examples.      Justify   your answers.    All   lines   should   be   assumed   to   take   constant   time   (including   calls   to   other   functions   like   print(   .   .   .), √3x, log(   .   .   .), etc...).
(a)                                 i      =         1
while         i         <= n
for         j      =         1      to         i
print(j)   i      =         i      +      2
(b)                                 i      =         1
while         i         <= n/3 j = 1
while         j         < n
print (i , j )
j = j * 3√n
i      =         i      +         1
(c)                                 for         i      =         1      to      n   j      =      n
while         j         >         1
j      =      j      /      2
for      k      =         1      to      n/2   print(k)
Problem H1.3: Divide and Conquer 
For   each   of the   following   functions,   if possible   write   the   recurrence   in   the   form.:   T(n)   = aT(n/b)   +   f(n)Then   use   the   Master   Theorem   (if possible)   to   calculate   the   runtime.   Explain   your   reasoning.   If the   Master   Theorem   cannot   be   used,   then   you   do   no   need   to   calculate   the   runtime,   but   explain   why   that theorem   cannot   be   used.    All   lines,   except those   involving   recursive   calls,   should   be   assumed to   take   constant   time.
(a)      calc(n)
for         i      =         1      to      n   print(i)
if      n      ==         0
return         1
s      =      0
for         i      =      0      to         8
s      =         s      +         calc(⌊n/3⌋)   return         s
(b)    (*Practice   Problem*)
closest_diff(A,      n,      x)   if      n      ==         0:
return         ∞   if      n      ==         1:
return         abs(A[1]         -    x)   B      =         []
C      =         []
for         i      =      2      to      n
if      A[i]    < A[1]
B .   append(A[i])   else
C .   append(A[i])   return         min(
abs(A[1]         -      x),
closest   _diff(B,      B   .   length ,    x),   closest   _diff(C,    C   .   length ,    x))
(c)      sort   _often(A,      p,    r)
if      p         < r
n      =      r-p
B      =      new         array[1:n]   for      k      =         1      to      n
B[i]      =      A[i]
q    =    ⌊(r-p)/4⌋
sort_often(A,      p,    q)
sort_often(A,    P      +      q      +         1,      p      +      2q)         sort_often(A,    p      +      2q      +         1,      p      +      3q)   merge_sort(B,      p,    r)
Problem H1.4: Recurrences 
For   each   of   the   following   recurrences,    calculate    Θ(f(n)).       In   all   cases,   assume   T(n)    =    Θ(1)   if n   = Θ(1).   Justify   your   answers:
(a)   T(n) = T(n/3) +   7   (*Practice   Problem*)         (b)   T(n) = 5T(n/5) +   n   (*Practice   Problem*)
(c)   T(n) = 25T(n/5) +   n2
(d)   T(n) = 3T(n/9) +   n0.5
(e)   T(n) =   7T(n/2) +   n2   lg   nProblem H1.5:    GPU Storage - Memory is important when storing images   (textures) on a graph-   ics   card.      Quite   often   GPU   devices   have   limited   memory.      We   will   look   at   this   practical   problem   of   storage   space.    Consider   the 代 写CSCI 4041 Algorithms and Data Structures - Spring 2025 Homework 1 - Asymptotic RuntimePython
代做程序编程语言  following   diagram   showing   a   set   of   animation   frames   and   an   image   that   is   scaled   for   higher   resolution.    Assume   h   and   w   are   the   same   in   both   examples   and   that   the   size of one image takes up m   = whc memory, where c is some constant related to the size of each pixel.

(a)   Determine   and justify   the   storage   complexity   Θ(f(k))   for   both   Animation   and   Scaling.
(b)    Assume we store 60 animation frames   on   the   GPU   at   anytime   to   achieve   6o   frames   per   second   (FPS) video.   We would like to store higher resolution for   each   frame   even   if the FPS   decreases.   Assuming   that   the   scale   factor   must   be   a   power   of 2,   what   is   the   maximum   resolution   we   can   store   while   maintaining   the   same   memory   requirements?    How   many   frames   can   we   store   at   the   higher   resolution?   Justify   your   answer.
(c)    Assume   we   are   storing   an   animation   of   a   special   effect   that   requires   the   image   resolution   to   scale   by   the   frame   number.   The   first   frame   scales   by   1,   the   second   by   2,   the   third   by   3,   etc...   What   is   the   precise   amount   of memory   would   we   need   to   store   k   frames?   Formally   show   that   the   memory   complexity   is   Θ(f(k))   for   some   common   function   f(k).
Problem H1.6: Programming Problem Instructions: Write a python program that takes   an   array of floats,   A,   and   finds   the   k-closest   float   pairs   (pairs   of   float   values   in   A   that   have   the   smallest   difference).    The   program   returns   an   array   of   float   sets   of   size   2   ordered   by   the   distance   between   the   two   numbers   in   each   pair   (from   least   to   greatest).Submission: Submit   a   file   named   H1 6.py   to   the“Homework    1.6”submission   on   Gradescope.   The   file   should   contain   the   closest pairs(A,    k)   function   defined   below.       Since   the   problem   is   autograded,   you   may   submit   to   Gradescope   as   many   times   as   you   like   up   to   the   deadline:
def         closest_pairs(A,      k):
...
#    Calculate    the    k         closest         pairs       (from    least    to         greatest         difference):   #    k   _closest   _pairs    =       [[a1,    b1],         [a2,    b2],         [a3,    b3],         .   .   .         [ak,    bk]]
...
return         k_closest_pairs
Additional details: 
•    Array   values   can   be   reused.    In   Example    1   below,   both    1.5   and   2.5   are   repeated   in   separate   pairs.
•    Each   unique   pair   should   only   be   listed   once.    (i.e.    [a,   b]   =    [b,   a])
•    Report   your   answer   with   the   smallest   element   appearing   first.    (i.e.    a   ≤ b)
•    In   case   of ties   report   the   pair   [a,   b]   whose   smallest   element   appears   in   the   array   before   any   c,   d   appearing   in   a   tie   pair   [c,   d].
• You   may   assume   1 ≤ k ≤ (2(n)).
Examples: 
•      Example   1
>>>      A      =       [1 .   5,         2 .   5,         3,         1 .   1,         7]   >>>      print(closest_pairs(A,3))
#         Output:
[[1   .   5,         1   .   1],         [2   .   5,    3],       [2   .   5,         1   .   5]]
•      Example   2
>>>      A      =       [1,         2,      3,      4]
>>>      print(closest_pairs(A,2))
#         Possible         Output:   [[1,         2],         [3,         2]]
#         Possible         Output:   [[3,      4],         [1,         2]]
#         Possible         Output:   [[2,         3],         [4,         3]]
#    Many         other         permutations         are         valid .   .   .(*Practice Problem*)   Analyze the runtime of your algorithm.    How might you change your algorithm   if   you   only   needed   to   find   the   closest   pair?      (i.e.      the   k=1   case)   Can   your   new   k=1   case   be   more   efficient   than   the   original   algorithm?



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
