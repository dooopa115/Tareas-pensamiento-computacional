Ejemplo #1

perfil\_usuario\["antiguedad\_meses"] = 12



.setdefault() 

perfil\_usuario.setdefault("pais", "España")



print("Diccionario tras insertar:", perfil\_usuario)

{'usuario': 'TechGuy', 'rango': 'Admin', 'antiguedad\_meses': 12, 'pais': 'España'}



Ejemplo #2

perfil\_usuario\["rango"] = "SuperAdmin"



.update()

(Permite modificar o insertar múltiples datos al mismo tiempo)

perfil\_usuario.update({"antiguedad\_meses": 14, "estado": "Activo"})



print("Diccionario tras modificar:", perfil\_usuario)

{'usuario': 'TechGuy', 'rango': 'SuperAdmin', 'antiguedad\_meses': 14, 'pais': 'España', 'estado': 'Activo'}



Ejemplo #3

perfil\_usuario\["pais"]



&#x20;.pop()

estado\_eliminado = perfil\_usuario.pop("estado")



&#x20;.clear()

perfil\_usuario.clear() -> Esto lo dejaría así: {}



print("Diccionario tras eliminar:", perfil\_usuario)

print("Valor recuperado del pop:", estado\_eliminado)



{'usuario': 'TechGuy', 'rango': 'SuperAdmin', 'antiguedad\_meses': 14}



