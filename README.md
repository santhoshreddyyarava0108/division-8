# division-8
org 100h

mov al,15h
mov bl,05h
div bl
mov bl,al
mov bh,ah

and al,0f0h
shr al,4
add al,30h
cmp al,39h
jle print_first_digit1
add al,7

print_first_digit1:
    mov dl,al
    mov ah,02h
    int 21h

mov al,bl
and al,0fh
add al,30h
cmp al,39h
jle print_second_digit1
add al,7

print_second_digit1:
    mov dl,al
    mov ah,02h
    int 21h

mov al,bh
and al,0f0h
shr al,4
add al,30h
cmp al,39h
jle print_first_rem_digit
add al,7

print_first_rem_digit:
    mov dl,al
    mov ah,02h
    int 21h

mov al,bh
and al,0fh
add al,30h
cmp al,39h
jle print_second_rem_digit
add al,7

print_second_rem_digit:
    mov dl,al
    mov ah,02h
    int 21h

ret

