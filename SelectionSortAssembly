
MOV BX,0200H                  
MOV BYTE PTR [BX],02h
MOV BYTE PTR [BX+1],75H
MOV BYTE PTR [BX+2],0B4H
MOV BYTE PTR [BX+3],91H
MOV BYTE PTR [BX+4],31H    ;sayilar bellek bolgelerine yerlestirilir
MOV BYTE PTR [BX+5],0A9H
MOV BYTE PTR [BX+6],0D3H
MOV BYTE PTR [BX+7],05H
MOV BYTE PTR [BX+8],0F3H
MOV BYTE PTR [BX+9],61H


MOV DI,0        ; dis dongu indisi (i)
MOV SI,0        ; ic dongu indisi  (j)


OUTER_LOOP:
            
    MOV DL,[BX+DI] ; DL registerina en kucuk sayi kabul edilir
    MOV SI,DI      ; dis dongudeki i indisi degeri ic dongudeki j'ye kopyalanir
    INC SI         ; j degeri bir arttirilir

INNER_LOOP:
           
    MOV AL,[BX+SI]  ; AL registerina sonraki deger kopyalanir 
    CMP AL,DL       ; AL registerindaki deger ile DL registeri karsilastirilir
    JB SIRALA       ; AL registerindaki deger daha kucuk ise SIRALA kismi calistirilir
    INC SI          ; SIRALA kismi calizmazsa dongu degiskeni arttirilir
    CMP SI,09       ; ic dongu degiskeni j indisi kontrol edilir
    JBE INNER_LOOP  ; eger dongu degiskeni siniri gecmediyse ic dongu tekrarlanir

         
INC DI         ; dis dongu degiskeni i indisi bir arttrilir
CMP DI,09      ; dis dongu degiskeni i indisi kontrol edilir
JB OUTER_LOOP  ; eger dongu degiskeni siniri gecmediyse dis dongu tekrarlanir
HLT            ; dis dongu de bittiyse program sonlanir


SIRALA:

    MOV CL,AL ; AL registerindaki deger yedeklenir
    MOV AL,DL ; DL registerindaki deger AL registerina kopyalanir.
    MOV DL,CL ; CL registerina yedeklenen deger DL registerina kopyalanir


MOV CL ,[BX+SI]         ; ic dongudeki deger yedeklenir
MOV BYTE PTR [BX+SI],AL ; ic dongudeki degere en kucuk deger kopyalanir   
MOV BYTE PTR [BX+DI],CL ; en kucuk elemanin adresine ic dongude bakilan deger kopyalanir


INC SI          ; ic dongu degiskeni j indisi bir arttrilir    
CMP SI,09       ; ic dongu degiskeni j indisi kontrol edilir
JBE INNER_LOOP  ; eger dongu degiskeni siniri gecmediyse ic dongu tekrarlanir
JA OUTER_LOOP   ; eger dongu degiskeni siniri gectiyse dis donguye donulur





