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
 Homework2
import nltk 
from nltk.tokenize import word_tokenize 
from nltk.corpus import stopwords 
from nltk.stem import PorterStemmer 
nltk.download('stopwords') 
download_stopwords = stopwords.words('english') 
stop_text = [] 
#nltk.download('punkt') 

text = '''Humans are uniquely adept at using systems of symbolic communication (such as language and art) for self-expression and the exchange of ideas, and for organizing themselves into purposeful groups''' 
tokens = word_tokenize(text) 
lenght = len(tokens) 
file = open("text.txt", "w") 
for word in tokens: 
file.write(word + '\n') 
file.write(str(lenght) + (' слов(а)')) 
file.close() 

for i in tokens: 
if i not in download_stopwords: 
stop_text.append(i) 
dif = len(tokens) - len(stop_text) 
proc = 100*dif/len(tokens) 

stemsPorter = [] 
porter = PorterStemmer() 
for w in tokens: 
w = porter.stem(w) 
if w != "": 
stemsPorter.append(w) 
text = open("deliting.txt", "w") 
text.write(str(dif) + (' слов или ') + str(proc) + ('% слов удалено') + '\n') 
stemsPorter = [] 
porter = PorterStemmer() 
for w in tokens: 
a = porter.stem(w) 
text.write(w + ':' + a + '\n') 
text.close()
