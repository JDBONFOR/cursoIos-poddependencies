# Curso iOS - Swift 4
Branch donde se detalla el procedimiento para agregar CocoaPods al proyecto.  
El website de cocoapods es el siguiente: https://cocoapods.org/, en él se encuentra la documentacion necesaria.

## Pasos
1. Abrir una nueva terminal  
2. Posicionarnos en la raiz del proyecto ( cd folder project )  
3. Ejecutar el comando, pod init
4. Ejecutar el comando, pod install  
5. Editar el archivo PodFile como se indica en el siguiente punto
  
## Configuracion archivo Podfile
Aparecea con la configuracion inicial indicando valores para iOS9.  ( A descomentar, en caso de ser soportado )

``` swift
    target 'CocoaPodes-dependencies' do
      # Comment the next line if you don't want to use dynamic frameworks
      use_frameworks!

      # Pods for CocoaPodes-dependencies

    end
```  
  
Ejemplo de agregado de POD basico

``` swift
    target 'CocoaPodes-dependencies' do
      # Comment the next line if you don't want to use dynamic frameworks
      use_frameworks!

      # Pods for CocoaPodes-dependencies
      pod 'SVProgressHUD'
    end
```  
  
Ejemplo de agregado de POD especificando version
  
``` swift
      target 'CocoaPodes-dependencies' do
        # Comment the next line if you don't want to use dynamic frameworks
        use_frameworks!

        # Pods for CocoaPodes-dependencies
        pod 'SVProgressHUD', '2.2'
      end
  ```  

Ejemplo de agregando un POD desde GIT  
Agrega lo que se encuentre en MASTER.

``` swift
    target 'CocoaPodes-dependencies' do
      # Comment the next line if you don't want to use dynamic frameworks
      use_frameworks!

      # Pods for CocoaPodes-dependencies
      pod 'SVProgressHUD', :git => ' url del repositorio '
    end
```  





### Dependencias instalacion
    
* SVProgressHUD ( Loader )  
⋅⋅⋅ Para instalarlo, agregar la linea dentro del target como pod 'nombre de la dependencia'  
Posteriormente, en la terminal, nos posicionaremos en la raiz de nuestro proyecto y ejecutaremos  
* pod install  
Revisaremos la estructura del proyecto verificando el target Pods > Folder pods y veremos una nueva carpeta de la dependencia instalada.

### Comandos basicos
* pod init, inicia pods en nuestro proyecto.
* pod install, instala las dependencias indicadas en el podfile.
* pod update, actualizara a las versiones expresadas en el podfile las dependencias.  
* pod --help, indica todos los comandos posibles.
* pod deintegrate, desinstala PODs del proyecto. Eliminar a mano, el archivo .lock, podfile y .xcworkspace

## 

  
## Concideraciones
Al ejecutar el paso de pod init, se generará el archivo podfile.  
Este archivo es quien contiene las dependencias que vayamos a agregar en el futuro.  
Al ejecutar el paso de pod install, veremos que genera 3 nuevos ficheros.  
* Podfile.lock - Integridad de dependencias.
* Carpeta Pods - donde se instalan todas las dependencias
* Archivo del proyecto .xcworkpace  
El nuevo archivo de proyecto, es que a partir de ahora, debemos ejecutar para abrir el proyecto.

