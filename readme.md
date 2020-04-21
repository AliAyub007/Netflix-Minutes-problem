Netflix Minutes problem

Netflix decided to change their payment system to charge users to pay by minutes watched. each user is given some minutes for instance 120, 200 and 500 minutes. and they all depend on the package A, B or C.<br/>
When any of the user finishes a movie, a function will be called to deduct the number of minutes that have been watched. Anu user can buy more time.<br/>
Define a procedure that will first initialise the minute count according to A, B, C and which can be used to add or subtract minutes<br/>
your procedure has to have<br/>
subtract<br/>
topup<br/>
and dispatch<br/>

(define (make-account package)<br/>
&emsp;(let ((balance (cond [(equal? package "A") 120]<br/>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;    [(equal? package "B") 200]<br/>
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;    [(equal? package "C") 500])))<br/>

&emsp;(define (deduct minutes)<br/>
&emsp;&emsp;(begin (set! balance (- balance minutes)) balance))<br/>

&emsp;(define (topup minutes)<br/>
&emsp;&emsp;(begin (set! balance (+ balance minutes)) balance))<br/>


&emsp;(define (dispatch cmd)<br/>
&emsp;&emsp;(cond ((eq? cmd 'deduct) deduct)<br/>
&emsp;&emsp;&emsp;&emsp;   ((eq? cmd 'topup) topup)<br/>
&emsp;&emsp;&emsp;&emsp;   (else (error "Unknown command:" cmd))))<br/>
    
&emsp;  dispatch))<br/>