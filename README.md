# Flujo de Trabajo con NLGenomeSweeper para la Detección de Genes NLR

Este repositorio contiene un flujo de trabajo paso a paso para identificar genes tipo NBS-LRR (NLR) en un genoma vegetal utilizando la herramienta NLGenomeSweeper.

## ¿Qué es NLGenomeSweeper?

[NLGenomeSweeper](https://github.com/ntoda03/NLGenomeSweeper) es una herramienta que permite buscar genes de resistencia NLR en genomas de plantas. Estos genes son fundamentales para entender la resistencia a enfermedades, así como para el mejoramiento genético.

## Requerimientos y Dependencias

Antes de comenzar, asegurémonos de tener instaladas las siguientes herramientas:

- Python 3.x
- HMMER (para la detección de dominios conservados)
- BLAST+ (para comparaciones de secuencias)
- R (opcional, en caso de parsear resultados con scripts R)
- Git (para clonar el repositorio original o este repositorio)
- Cualquier otra dependencia detallada en el repositorio oficial de NLGenomeSweeper.

En este repositorio proporcionamos un script (`scripts/install_dependencies.sh`) que facilita la instalación (ajustar según tu sistema):

```bash
cd scripts/
bash install_dependencies.sh
```

El script install_dependencies.sh contiene:

```bash
# install_dependencies.sh
conda create -y -n NLGenomeSweeper -c bioconda -c conda-forge \
    python=3.6 blast muscle=3.8.1551 samtools bedtools hmmer transdecoder openjdk
conda activate NLGenomeSweeper
```

## Iniciar el Flujo de trabajo

### 1. Clonar este Repositorio

```bash
git clone https://github.com/tuusuario/mi-proyecto-NLGenomeSweeper.git
cd mi-proyecto-NLGenomeSweeper
```

### 2. Preparar el Genoma

Colocar el genoma en formato fasta en la carpeta `data/ppa_v2.asm.fasta`.

```bash
cp ../../ppa_v2.asm.fasta data/ppa_v2.asm.fasta
```

### 3. Preparar la base de datos

NLGenomeSweeper requiere bases de datos de dominios (HMMs) y/o bases BLAST específicas. Si el repositorio oficial indica cómo descargarlas, inclúyelo aquí. 

```bash
mkdir -p data/database
cd data/database
wget http://link-a-base-de-datos.org/NLR-DB.hmm
hmmpress NLR-DB.hmm
cd ../../

```



