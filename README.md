# Notepad
Block de notas

Esta aplicacion fue creada para ser descompilada con un grado de dificultad media usando: https://github.com/zrax/pycdc

Dificultad 1, el descompilador no puede asignar los nombres de las variables dentro de los argumentos de la funcion a ejecutar, para estos casos es necesario modificarlo manualmente, Ejemplo:

<table>
<tr>
<td>
      
```python      
self.config(self.barra_de_menus, **('menu',))
self.menu1 = Menu(self.barra_de_menus, 0, **('tearoff',))
self.menu1.add_command('Nuevo', self.nuevo, **('label', 'command'))
```

</td>
<td>

      
```python      
self.config(menu=self.barra_de_menus)
self.menu1 = Menu(self.barra_de_menus, tearoff=0)
self.menu1.add_command(label='Nuevo', command=self.nuevo)
```
    
</td>
</tr>
</table>
