# sharks_limpieza (proyecto 1)
<img width="819" alt="Screenshot 2022-10-31 at 19 42 35" src="https://user-images.githubusercontent.com/114593402/199085859-f54b8510-3475-48b9-acc9-a4539ed1734a.png">
# Procedimientos del primer proyecto:
  
  paso 1: df.drop_duplicates()   ------>  shape(6312, 24)   ------>   shape_ori(25723, 24) 
  
  paso 2: df.info(memory_usage = 'deep')    ------>   estudiamos la nueva estructura del dataframe ------>    las ultimas dos columnas, full nulos
  
  paso 3: x = (df.isna().mean() * 100) >= 80
          df.drop(columns = x[x == True].index, inplace = True)   ------>   dropeamos las columnas con mas de 80% de valores nulos
          
  paso 4: df.fillna('unknown', inplace = True) ------>    rellenamos los nulos que se quedan por 'unknown'
  
  paso 5: <img width="793" alt="Screenshot 2022-10-31 at 20 04 05" src="https://user-images.githubusercontent.com/114593402/199089174-63a883c0-d82d-4d05-9392-696b220f6e12.png">
