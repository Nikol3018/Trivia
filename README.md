import random
def Puntos_a (Respuesta,puntos,categoria,Pregunta_aleatoria, acumulado):
   
     if Respuesta == categoria[Pregunta_aleatoria][1]:
      print("Correcto: +10 puntos")
      puntos += 10
   
     else:
      print("incorrecto: 0 puntos")
      acumulado += 1
     return acumulado, puntos

def main():
  
   Nombre = (input ("Ingrese su nombre: "))
   Categoria_historia = []
   Categoria_entretenimiento = []
   puntos = 0
   Respuesta = 0
   game_over = True
   acumulado = 0
   entretenimiento=9
   historia=9
  


   

   input(("presione enter para designar una categoria: "))

   #preguntas de historia
   Categoria_historia.append([f"Cuándo acabó la segunda guerra mundial:\n A) 1955\n B) 1911\n C) 1945\n","C"])
   Categoria_historia.append([f"Cuándo empezó la primera guerra mundia:\n A) 1914\n B) 1911\n C) 1899\n","A"])
   Categoria_historia.append([f"En qué año se produjo la revolución francesa:\n A) 1844\n B) 1789\n C) 1695\n","B"])
   Categoria_historia.append([f"En qué año fue el atentado a las torres gemelas:\n A) 2000\n B) 2003\n C) 2001\n","C"])
   Categoria_historia.append([f"En qué año fue derrivado el muro de berlin:\n A) 1989\n B) 1990\n C) 1986\n","A"])
   Categoria_historia.append([f"Cuáto duro la guerra de los 100 años:\n A) 100A\n B) 116A\n C) 99A\n","B"])
   Categoria_historia.append([f"En qué año se hundió el titanic:\n A) 1912\n B) 1910\n C) 1911\n","A"])
   Categoria_historia.append([f"En qué año murió Napoleón:\n A) 1960\n B) 1821\n C) 1956\n","B"])
   Categoria_historia.append([f"Cuántos presidentes ha tenido Colombia:\n A) 61\n B) 56\n C) 39\n","A"])
   Categoria_historia.append([f"En qué año fueron los primeros juegos olimpicos:\n A) 1899\n B) 1896\n C) 1930\n","B"])
   #preguntas de entretenimiento 
   Categoria_entretenimiento.append([f"En qué pelicula de disney se canta bajo el mar: \n A) bob esponja\n B) La sirenita\n C) aquaman\n","B"])
   Categoria_entretenimiento.append([f"Con qué grupo grabo michael jackson su primer disco : \n A) Jackson five\n B) El grupo niche\n C) Beatles\n","A"])
   Categoria_entretenimiento.append([f"Qué familia vive en la ciudad de sprinfield: \n A) Los smith \n B) Los grifin\n C) Los simpson\n","C"])
   Categoria_entretenimiento.append([f"En qué siglo se desarrolla terminator: \n A) XX\n B) XV\n C) XIX\n","A"])
   Categoria_entretenimiento.append([f"Cuántos años tenia harry potter cuando entro en hogwarts: \n A) 9 años\n B) 15 años\n C) 11 años\n","C"])
   Categoria_entretenimiento.append([f"Como se llama el papa se simba: \n A) scar\n B) mufasa\n C) pumba\n","B"])
   Categoria_entretenimiento.append([f"En qué año  se lanzó 'Bomba' de king africa : \n A) 2000\n B) 1999\n C) 2003\n","A"])
   Categoria_entretenimiento.append([f"Qué talento tiene la gente que recibe el premio berlin: \n A) Canto\n B) Actuacion\n C) Magia\n","C"])
   Categoria_entretenimiento.append([f"Qué isla descubre King Kong: \n A) Calavera\n B) Mutante\n C) Gorgona\n","A"])
   Categoria_entretenimiento.append([f"En qué año se estreno nemo: \n A) 2004\n B) 2010\n C) 2003\n","C"])
    
   while game_over : 
     
     

      Categoria_aleatoria = random.randint(0,1)   
     
      if Categoria_aleatoria == 1 and historia !=0:
         #preguntas de historia
         Pregunta_aleatoria = random.randint(0,historia)
         print(f"{Categoria_historia[Pregunta_aleatoria][0]}")
         Respuesta = (input("escriba su respuesta: ")).upper()
         categoria= Categoria_historia

         acumulado,puntos=Puntos_a (Respuesta,puntos,categoria,Pregunta_aleatoria, acumulado)
         Categoria_historia.remove(Categoria_historia[Pregunta_aleatoria])   
         historia -= 1      
      
      elif entretenimiento!=0 and Categoria_aleatoria==0:  
         #preguntas de entretenimiento
         Pregunta_aleatoria = random.randint(0,entretenimiento) 
         print(f"{Categoria_entretenimiento[Pregunta_aleatoria][0]}")
         Respuesta = (input("escriba su respuesta: ")).upper()
         categoria=Categoria_entretenimiento
         acumulado,puntos=Puntos_a (Respuesta,puntos,categoria,Pregunta_aleatoria, acumulado)
         Categoria_entretenimiento.remove(Categoria_entretenimiento[Pregunta_aleatoria])         
         entretenimiento -= 1
          
      Salir = input(("presione enter para la siguiente pregunta o escriba 1 para teminer el juego: "))        
      if Salir == "1":
        game_over = False       
      if acumulado == 3:
         game_over = False
         print("Game Over")
      print(f"los puntos acumulados son: {puntos}")
       
if _name_ == "_main_":
    main()
