INCLUDE Irvine32.inc
.DATA

msg1 byte "enter 1 for Linear Search ",0 
msg2 byte "enter 2 for Binary Search ",0
msg4 byte "enter 3 for Exit ",0
msg3 byte "enter a Number : ",0
var1 byte "you are exit now !! GOOD BYE !"


arr word 10,4,7,14,299,156,3,19,29,300,20
o1 byte "Enter the number to search: ",0
o2 byte "Number found",0
o3 byte "Not Found",0
i1 word ?



array byte 10 DUP(?)
num byte ?
first byte 0
middle byte 0
last byte 0
num1 byte " Enter 10 Number in Array : ",0
num2 byte " Enter Number to Find: ",0
num3 byte " Found ",0
num4 byte " Not Found ",0

.CODE
main PROC

mov edx , offset msg1
call writestring
call crlf
mov edx , offset msg2
call writestring
call crlf
mov edx , offset msg4
call writestring
call crlf
mov edx , offset msg3
call writestring
call readInt
call crlf

;===================================================================linear searching perform======================================================

.if (eax == 1)

mov eax,0
mov edx,offset o1
call writestring
call readint                             
mov i1,ax                          
mov ecx,11
mov esi,offset arr                                          

L1:
mov ax,[esi]
cmp ax,i1
je p
add esi,2
loop L1
mov edx,offset o3
call writestring
jmp e

p:
mov edx,offset o2
call writestring

e:
call crlf
.endif
;========================================================== end linear searching ==================================================

;========================================================== binary search =========================================================
.if(eax == 2)
call clrscr
call crlf
mov edx,offset num1
call writestring
call crlf
mov edx,offset array
mov ecx,lengthof array
mov esi,0
L:
call readint
mov array[esi],al
inc esi
loop L

call crlf
mov edx,offset num2
call writestring
call readint
mov num,al

mov al,lengthof array
add al,first
mov bl,2
                        
div bl
mov middle,al
mov bl,first

.while bl <= last
movzx si,middle
mov al,num
.if array[si] < al
mov al,middle
add al,1
mov first,al
mov al ,10
add al , first
mov bl , 2
div bl
mov middle , al
mov bl ,al

.elseif array[si] == al
mov edx,offset num3
call writestring
call crlf
jmp e 

.else

mov al,middle
sub al,1
mov last,al
add al,first
mov bl,2
div bl
mov middle,al
.endif
.endw

mov edx,offset num4
call writestring
call crlf

e1:
.endif 

.if (eax == 3)
mov edx , offset var1
call writestring
.endif

;================================================================= end binary search ================================================================
exit
main ENDP
END main
