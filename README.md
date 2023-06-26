# SHAP_XAI_VM
El desarrollo original del proyecto fue realizado en una máquina virtual preconfigurada usando como imagen base Python 3.9. Referirse a [este link](https://github.com/gradient-ai/base-container/tree/main/pt112-tf29-jax0314-py39) para ver todas las dependencias incluídas en dicho entorno. Es recomendable el uso de entornos virtualizados mediante [Miniconda](https://docs.conda.io/en/latest/miniconda.html).
Las siguientes dependencias fueron necesarias instalarlas de forma manual:
- stable-baselines3[extra]
- gym
- shap

En el repositorio únicamente estará presente un modelo en el directorio, `/Models/RL/RL_001_Balanced.zip`, por las limitaciones de espacio de GitHub. Este es el modelo necesario para la parte explicativa. En la carpeta `./Utils` estarán tanto el _KernelExplainer_ como `SHAP_explainer.pkl`; como las muestras usadas para la creación de las explicaciones `x_samples_5000.csv` y `y_samples_5000.csv`; como los valores de SHAP  calculados en base a las muestras `shap_values_5000.pkl`. Es necesario cargar estos archivos si se quiere ejecutar los cuadernos sin necesidad de volver a seleccionar muestras y calcular los valores de SHAP. Es posible que sea necesario cambiar las rutas definidas, dado que las máquinas virtuales exigían escribir las rutas de forma absoluta.

Si se quiere realizar un recorrido completo del proyecto, realizar los siguientes pasos:

 1. Descargar el repositorio.
 2. Crear en el repositorio dos directorios vacíos, `./Dataset`, `./FinalDataset` y dentro de `./Models` uno para cada modelo exceptuando el de RL que ya está creado (DT, RF, XGB, ML).
 3. Descargar el *dataset* UNSW-NB15 por ejemplo, de [Kaggle](https://www.kaggle.com/datasets/mrwellsdavid/unsw-nb15), y mover los archivos `UNSW_NB15_testing-set.csv` y `UNSW_NB15_training-set.csv` al directorio `./Dataset` creado.
 4. Cambiar las rutas en los cuadernos por la razón expuesta anteriormente.
 5. Ejecutar los cuadernos en orden numérico, salvo para la parte explicativa, en la que se debería ejecutar primero `3_XRL_Global&Class.ipynb`. Tener en cuenta que en algunos casos se deben cambiar variables de forma manual (como es el caso del umbral en la generación de los *dataframes* en el cuaderno 1). Es recomendable ejecutar las celdas secuencialmente y  de forma manual y no ejecutar todas las celdas a la vez, ya que algunas instrucciones pueden estar comentadas y darían lugar a error.
