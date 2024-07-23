# Presentations
Presentaciones del curso del Club Γα=Ω5

Para editar las presentaciones ocupas de la extensión de [marp](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) junto al paquete de extensiones [GitHub Markdown Preview](https://marketplace.visualstudio.com/items?itemName=bierner.github-markdown-preview) instaladas dentro de [VScode](https://code.visualstudio.com/Download).

Para marp ocupas cualquier navegador basado en chrome instalado en tu computadora, también debes activar el html en la configuración de la extension en el apartado `markdown.marp.enableHtml` 

para convertir las presentaciones a HTML de una manera más eficiente ocupamos descargar 'marp-cli', para windows se puede descargar a través de <https://github.com/marp-team/marp-cli/releases> o con el gestor de paquetes [scoop](https://scoop.sh/#/) `scoop install main/marp` y para MacOS con [homebrew](https://brew.sh/) `brew install marp-cli`
 
Y para compilar las presentaciones a HTML con marp-cli ejecutamos el siguiente comando dentro de la carpeta del proyecto y del año (2024): 
```powershell
marp --allow-local-files --html --theme ../src/am_nord.scss ./presentacion.md
```

muchas gracias a Chu Hong por la plantilla de marp [awesome](https://github.com/favourhong/Awesome-Marp/tree/main)