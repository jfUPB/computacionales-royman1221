``` asm

@0                
D=A              
@13               
M=D              

@1                
D=A               
@COUNTER_LOOP    
0;JMP             

(COUNTER_LOOP)    
@13              
D=M              
@1                
D=D+A             
@13             
M=D              

@2               
D=A               
@COUNTER_LOOP2   
0;JMP            

(COUNTER_LOOP2)   
@13              
D=M              
@2               
D=D+A             
@13              
M=D              

@3                
D=A               
@COUNTER_LOOP3    
0;JMP             

(COUNTER_LOOP3)   
@13               
D=M               
@3                
D=D+A            
@13             
M=D             

@4                
D=A               
@COUNTER_LOOP4    
0;JMP             

(COUNTER_LOOP4)   
@13               
D=M               
@4                
D=D+A             
@13               
M=D               

@5                
D=A               
@COUNTER_LOOP5   
0;JMP           

(COUNTER_LOOP5)   
@13               
D=M               
@5                
D=D+A             
@13               
M=D               

@12               
D=A               
@12               
M=D               
0;JMP             
```
