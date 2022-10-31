# sharks_limpieza (proyecto 1)
<img width="819" alt="Screenshot 2022-10-31 at 19 42 35" src="https://user-images.githubusercontent.com/114593402/199085859-f54b8510-3475-48b9-acc9-a4539ed1734a.png">
 Procedimientos del primer proyecto:
  
 paso 1: df.drop_duplicates()   ------>  shape(6312, 24)   ------>   shape_ori(25723, 24) 
  
 paso 2: df.info(memory_usage = 'deep')    ------>   estudiamos la nueva estructura del dataframe ------>    las ultimas dos columnas, full nulos
  
 paso 3: x = (df.isna().mean() * 100) >= 80
 df.drop(columns = x[x == True].index, inplace = True)   ------>   dropeamos las columnas con mas de 80% de valores nulos: shape(6312, 22)
          
 paso 4: df.fillna('unknown', inplace = True) ------>    rellenamos los nulos que se quedan por 'unknown'
  
  paso 5: 
  <img width="793" alt="Screenshot 2022-10-31 at 20 04 05" src="https://user-images.githubusercontent.com/114593402/199089174-63a883c0-d82d-4d05-9392-696b220f6e12.png">
  
 paso 6:  df['Fatal (Y/N)'].replace(['UNKNOWN', ' N', 'M','2017','N ','y'],
                 ['unknown','N','unknown','unknown','N','Y'], inplace=True)    ------>   con esta funcion limpiamos la columna de fatal y pasamos de tener
                                                                                          6 categorias a 3
                                                                                          
 paso 7:    df.drop(df.tail(10).index, inplace = True)  ------>   tenia 10 filas con mas de 10 unknowns, asi que las elimine con esta formula (estaban
                                                                  todas juntas)
                                                                  
 paso 8:    shape(6312, 22)   ------>    shape(6302, 22)    
 
 paso 9:   def cleanact(x):
              dicc_actividades = .....
           df['Activity'] = df['Activity'].apply(cleanact)   aplique, usando regex, una definicion con un bucle para limpiar la columna de Activity

 paso 10:    utilice la funcion .replace para limpiar tres columnas mas (Type y Sex)

 paso 11:    def limpiar_date(date):
                  date = re.findall('\d+.\d+.\d+', date)
                  date = ''.join(date)                                   ------>   con esta funcion limpie la columna de date, usando regex
                  return date
             df['Case Number'] = df['Case Number'].apply(limpiar_date)

 paso 12:    Con esa misma formula cambie las columnas case_number.1 y case_number.2

                                                                     FIN
            
