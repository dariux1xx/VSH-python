# HSE-python
https://docs.google.com/spreadsheets/d/1iQkDsk_n3AluSyZ9f4tEJcn_aWE5FGYBLOeCGRzAExk/edit?usp=sharing
HOMEWORK
import pymorphy2 


text = "Мама мыла раму" 
text_split = text.split( 
' зафиксированная на каком-либо материальном носителе человеческая мысль; в общем плане связная и полная последовательность символов. ') 

File=open("itog.txt","w") 

morph = pymorphy2.MorphAnalyzer() 

for a in text_split: 
parse = morph.parse(a)[0] 
File.write("Простой разбор ") 
File.write(parse) 
result = parse.normalized 
File.write("Нормализовано: ") 
File.write(result) 
sklon = parse.inflect({"gent"}) 
File.write("Склонение в родительном: ") 
File.write(sklon) 
lex = parse.lexeme 
File.write("Лексемы: ") 
File.write(lex) 
File.write("***")
