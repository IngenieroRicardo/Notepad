# Notepad
Block de notas

Esta aplicacion fue creada para ser descompilada con un grado de dificultad media usando: https://github.com/zrax/pycdc


### Dificultad 1
El descompilador no puede asignar los nombres de las variables dentro de los argumentos de la funcion a ejecutar, para estos casos es necesario modificarlo manualmente, Ejemplo:

<table>
<tr>
<td>
      
```python      
self.config(self.barra_de_menus, **('menu',))
self.menu1 = Menu(self.barra_de_menus, 0, **('tearoff',))
self.menu1.add_command('Nuevo', self.nuevo, **('label', 'command'))
```

</td>
</tr>
<tr>
<td>

```python      
self.config(menu=self.barra_de_menus)
self.menu1 = Menu(self.barra_de_menus, tearoff=0)
self.menu1.add_command(label='Nuevo', command=self.nuevo)
```
    
</td>
</tr>
</table>



### Dificultad 2
Asignar nombre de variables a un argumentos compuesto, Ejemplo:

<table>
<tr>
<td>
      
```python      
selectordearchivo = filedialog.askopenfile((('text files', '*.txt'), ('All files', '*.*')), **('filetypes',))
```

</td>
</tr>
<tr>
<td>

```python      
selectordearchivo = filedialog.askopenfile(filetypes=(('text files', '*.txt'), ('All files', '*.*')))
```
    
</td>
</tr>
</table>



### Dificultad 3
El descompilador no logra determinar si las funciones requieren argumentos decimales, por lo que asignara valores enteros a todos los argumentos, para solventarlo es necesario validar que funciones requeriran otro tipo de variables y cambiarlas, Ejemplo:

<table>
<tr>
<td>
      
```python      
self.texto.delete(1, END)
```

</td>
<td>

```python      
self.texto.delete(1.0, END)
```
    
</td>
</tr>
</table>




