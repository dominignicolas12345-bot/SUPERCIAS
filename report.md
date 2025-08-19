# Descripción detallada de la plantilla Excel para los 4 TXT de la Superintendencia

## Introducción

La plantilla Excel "Matriz automatizada 4 TXT" está diseñada para automatizar la elaboración y envío de los cuatro estados financieros requeridos por la Superintendencia de Compañías del Ecuador. Estos estados son: el **Estado de Situación Financiera**, el **Estado de Resultados Integral**, el **Estado de Flujos de Efectivo** y el **Estado de Cambios en el Patrimonio**. La plantilla permite capturar información de periodos anteriores y del periodo actual, calcular variaciones, clasificar las cuentas según su naturaleza y actividad, validar que los estados cuadren y, finalmente, generar automáticamente los archivos de texto (TXT) en el formato exigido por la Superintendencia.

Un recurso de referencia explica que esta plantilla automatizada permite elaborar el estado de flujo de efectivo y el cambio en el patrimonio ingresando los estados financieros del periodo anterior y del actual; la propia plantilla realiza todas las operaciones de variaciones y clasificación por tipo de actividad【408761763729270†L48-L56】. Además, la misma fuente indica que la plantilla ayuda a verificar que los estados financieros estén cuadrados, de modo que el usuario pueda generar los cuatro archivos TXT con un solo clic【408761763729270†L58-L62】.

## Flujo de trabajo del usuario

1. **Ingresar los estados financieros**. El usuario debe llenar las secciones de la plantilla con el **estado de situación financiera** del periodo anterior y del periodo actual, así como el **estado de resultados** del periodo actual. A partir de estos datos, la plantilla calcula las variaciones entre periodos y los saldos finales.

2. **Asignar el tipo de actividad**. Cada cuenta contable se clasifica según su actividad (operación, inversión o financiación). La plantilla incluye una sección donde el usuario selecciona el tipo de actividad para cada cuenta; el sistema calcula automáticamente las variaciones y determina si corresponden a entradas o salidas de efectivo【408761763729270†L71-L73】.

3. **Validar y cuadrar los estados**. La plantilla totaliza las columnas de cada estado financiero y del flujo de efectivo en la parte inferior de las hojas. Estos totales permiten comprobar que las cifras cuadran y que no existen diferencias【408761763729270†L76-L77】. También contiene una hoja de control de errores donde se refleja cualquier desajuste entre cuentas de activo, pasivo, patrimonio y resultados.

4. **Revisar los estados finales**. Existen hojas con versiones finales de los estados de situación financiera y de resultados que se llenan automáticamente mediante fórmulas, a partir de los datos ingresados y los cálculos intermedios【408761763729270†L81-L86】. Igualmente, hay una hoja para el estado de flujos de efectivo parametrizado con fórmulas.

5. **Generar los archivos TXT**. Una vez verificado que todos los estados cuadran, se pueden ejecutar las macros integradas en la plantilla para generar los cuatro archivos de texto. Algunas versiones de la plantilla permiten exportar únicamente los TXT, ingresando los estados financieros ya cuadrados【408761763729270†L62-L62】. Estas macros convierten la información de los estados en un formato tabulado que sigue las especificaciones de la Superintendencia (códigos de cuentas, importe con signo, indicador de saldo deudor o acreedor, etc.) y guardan los archivos en una carpeta designada.

## Estructura y hojas de la plantilla

La plantilla contiene múltiples hojas, cada una con un propósito específico:

### Hojas de entrada y parametrización

- **DATOS DE LA EMPRESA / INDUCCIÓN**. Página de presentación con instrucciones generales y campos para ingresar datos básicos de la empresa y del periodo. Suele contener también botones o hipervínculos para ejecutar las macros de generación de TXT.

- **FORMULARIO 101 RENTA SOCIEDADES**. Hoja donde se puede pegar la información del formulario 101 del SRI; algunas macros permiten importar automáticamente datos del formulario del periodo anterior para facilitar la carga inicial.

- **MAPEO EEFF, MAPEO ER, PLANTILLA EFE, PLANTILLA ECP**. Hojas de mapeo para cada uno de los estados financieros (situación financiera, resultados, flujo de efectivo y cambios en el patrimonio). Estas hojas relacionan las cuentas del plan contable con los códigos requeridos por la Superintendencia y permiten personalizar el mapeo según las particularidades de la empresa. Por ejemplo, la plantilla incluye códigos del SRI para el estado de flujo de efectivo【408761763729270†L71-L73】 y del estado de resultados, de manera que cada cuenta se clasifica correctamente en los grupos oficiales.

- **CODIGOS SRI EFE, CODIGO SRI ER, codigos**. Tablas de referencia con los códigos numéricos que exige el SRI para cada rubro de los estados. Estas listas se utilizan en las fórmulas para generar el TXT con el formato correcto.

### Hojas de cálculo intermedio

- **ESTADO DE SITUACION FINANC / ESTADO DE RESULTADOS / ESTADO DE RESULTADO INTEGRAL**. Hojas donde se ingresan manualmente los saldos de las cuentas o se importan de otras fuentes. A partir de aquí se calculan sumas y variaciones y se enlaza con el mapeo correspondiente.

- **ESTADO_SITUACION_FINANCIERA / ESTADO_RESULTADO_INTEGRAL**. Representaciones intermedias de los estados, con códigos y cifras organizados en columnas específicas para preparar el TXT.

- **ESTADO FLUJO EFECTIVO / ESTADO CAMBIOS PATRIMONIO**. Hojas intermedias donde se calculan el estado de flujo de efectivo y el estado de cambios en el patrimonio. Las fórmulas parametrizadas asignan cada variación a su tipo de actividad y determinan si es una entrada o salida【408761763729270†L71-L73】.

- **INDICES FINANCIEROS**. Hoja donde se calculan ratios y otros indicadores financieros a partir de los estados, tales como razones de liquidez, solvencia y rentabilidad.

### Hojas de control y validación

- **CONTROL DE ERRORES**. Hoja que compara los totales del activo contra el pasivo más patrimonio, y los ingresos contra los gastos. Si hay diferencias, se registran para que el usuario corrija los datos antes de generar los TXT.

- **HOJAS DE TRABAJO TXT**. Espacios vacíos o de apoyo donde se pueden pegar o transformar datos antes de la salida final.

### Hojas de salida

- **TXT EEFF, TXT FLUJO, TXT ECP, TXT ERI**. Cada una de estas hojas contiene el archivo de texto en forma tabular antes de guardarlo. Cada fila incluye: el código de la cuenta, el monto (con signo positivo o negativo según corresponda), un indicador de tipo (por ejemplo "P" para saldo deudor o "C" para saldo acreedor), y campos de control. Estas hojas se llenan mediante macros que recogen la información de las hojas intermedias y la formatean. Finalmente, al ejecutarse la macro de exportación, el contenido se guarda en archivos .txt listos para ser cargados en el portal de la Superintendencia.

## Automatizaciones (macros)

La plantilla incluye macros que facilitan el trabajo. Entre las más importantes:

- **Importación del Formulario 101**. Algunas versiones permiten, mediante un botón, importar el formulario 101 del periodo anterior para reutilizar la estructura contable y los saldos iniciales.

- **Generación de los TXT**. Al final del proceso, se ejecuta un macro que copia los datos de las hojas TXT EEFF, TXT FLUJO, TXT ECP y TXT ERI a archivos de texto. Estos macros añaden los separadores de tabulación, los ceros y espacios necesarios y guardan los archivos con los nombres y rutas predeterminados.

- **Cálculo de variaciones y clasificación**. El macro que calcula las variaciones entre años y la clasificación por tipo de actividad se apoya en fórmulas y en el mapeo definido por el usuario; es el encargado de llenar el estado de flujo de efectivo y el estado de cambios en el patrimonio【408761763729270†L48-L56】.

## Conclusión

La plantilla Excel 4 TXT es una herramienta integral que automatiza la elaboración de los cuatro estados financieros obligatorios para las empresas reguladas por la Superintendencia de Compañías del Ecuador. Al permitir la importación de datos, el mapeo de cuentas, la validación de los estados y la generación automática de los archivos de texto, la plantilla reduce el riesgo de errores y agiliza el cumplimiento de obligaciones. Las hojas de trabajo guían al usuario en cada paso y las macros realizan los procesos repetitivos, de modo que el usuario solo debe verificar que los datos sean correctos. Según la descripción de un proveedor, la matriz calcula las variaciones, clasifica cada cuenta en el flujo de efectivo, totaliza las columnas para verificar que los estados cuadran y genera los cuatro TXT con un solo clic【408761763729270†L48-L56】【408761763729270†L58-L62】. De esta manera, la plantilla se convierte en un referente útil para el diseño de una aplicación web que replique las mismas funcionalidades.