```python
# Ejemplo en Python: Verificación de Paridad Par 
def verificar_paridad_par(cadena_bits): 
    # Contamos la cantidad de unos en la cadena recibida 
    conteo_unos = cadena_bits.count('1') 
    
    if conteo_unos % 2 == 0: 
        return "Transmisión correcta (Paridad Par verificada)" 
    else: 
        return "¡Error detectado en la transmisión!"
        
    #Prueba del algoritmo 
    mensaje_recibido = "1010111" 
    print(verificar_paridad_par(mensaje_recibido))
```