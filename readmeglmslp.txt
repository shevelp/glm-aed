# Instalación y Compilación del Proyecto GLM-AED

Este documento detalla los pasos necesarios para instalar y compilar el proyecto **GLM-AED** en un entorno Linux (probado en Linux Mint 22.1).

## Requisitos Previos

Antes de comenzar, asegúrate de que tienes las siguientes dependencias instaladas en tu sistema:

1. **Compilador Fortran**: `gfortran`
   ```bash
   sudo apt update
   sudo apt install gfortran
   ```
2. **Bibliotecas de desarrollo necesarias**:
   ```bash
   sudo apt install libnetcdf-dev libx11-dev libgd-dev
   ```

3. **Git**:
   ```bash
   sudo apt install git
   ```

4. **CMake** (solo si compilas con FABM):
   ```bash
   sudo apt install cmake
   ```

## Clonar el Repositorio

Clona el repositorio principal con todos los submódulos necesarios:
```bash
git clone glm-aed
```

## Configuración del Entorno

1. Asegúrate de que todos los submódulos y directorios requeridos están correctamente inicializados y sincronizados:
   ```bash
   git submodule update --recursive --remote
   ```

2. Asegúrte de tener permisos de ejecución en todos los scripts del directorio `admin` y en los archivos relacionados con la construcción:
   ```bash
   chmod -R 755 glm-aed
   ```

## Compilación del Proyecto

1. Accede al directorio principal del proyecto:
   ```bash
   cd glm-aed/glm-source
   ```

2. Ejecuta el script de compilación:
   ```bash
   bash build_glm.sh
   ```

3. Verifica que la compilación se haya completado exitosamente. El mensaje final debe incluir:
   ```
   Finished build for Linux
   Finished packaging for Linux
   ```

## Archivos Generados

Los binarios y archivos empaquetados se generarán en:
```text
binaries/Linuxmint/22.1/glm_latest/
```

Asegúrate de que los siguientes archivos estén presentes en el directorio de salida:
- `glm` (binario ejecutable)
- `VERSION` (archivo de versión)
- `ReleaseInfo.txt` (información sobre la compilación)

## Ejecución del Proyecto

1. Para ejecutar el binario generado:
   ```bash
   ./binaries/Linuxmint/22.1/glm_latest/glm
   ```

2. Si necesitas usar configuraciones específicas, consulta el manual o documentación adicional del proyecto.

## Limpieza de Archivos

Para limpiar los archivos generados temporalmente durante la compilación:
```bash
bash clean.sh
```


