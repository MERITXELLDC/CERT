### Pasos para desarrollar el proyecto

### 1. **Planificación y Definición de Requerimientos**

#### **1.1 Entender los Requisitos**
   - **EBSI**: Debes asegurarte de que tu proyecto esté alineado con la infraestructura de **EBSI** de la **Unión Europea**.
   - Esto involucra entender los principios de interoperabilidad, confianza y verificación de datos de la infraestructura.
   - **SSI**: Debes comprender cómo funciona la **Identidad Digital Autogestionada (SSI)**, donde los usuarios tienen control total sobre su identidad, almacenada en **Decentralized Identifiers (DIDs)** y **Verifiable Credentials (VCs)**.
   - **eIDAS2**: El wallet que se utilizará debe ser compatible con la normativa **eIDAS2**, la cual regula la identidad digital electrónica y la firma electrónica legalmente vinculante.

#### **1.2 Definir el Caso de Uso**
   - Ejemplo: **Emisión de diplomas académicos** o **certificados profesionales** como **credenciales verificables (VCs)**.
   - Qué tipo de **credenciales** se emitirán, qué tipo de **emisor** será (institución educativa, instituto de FP etc.), y cómo serán verificadas por otras entidades (empresas, instituciones, etc.).

### 2. **Configuración del Entorno de Desarrollo**

#### **2.1 Selección de Herramientas y Tecnologías**
   - **Blockchain**: **Ethereum** para gestionar los contratos inteligentes y las interacciones con la blockchain.
     - **[Truffle](https://archive.trufflesuite.com/)** o **Hardhat**: Frameworks para desarrollar, probar y desplegar contratos inteligentes en Ethereum.
       -**Truffle** más recomendable apara desarrolladores no familiarizados
     - **[Infura](https://www.infura.io/)** o **Alchemy**: Proveedores de infraestructura que te permiten interactuar con Ethereum sin necesidad de gestionar tu propio nodo.
      -   **Infura** tiene soporte para usuarios prncipiantes
      -   La dos te hacen dependiente de un proveedor externo y se compromete la descentralidad.
   - **Smart Contracts**:
     - **[Solidity](https://soliditylang.org/)**: El lenguaje de programación más utilizado para desarrollar contratos inteligentes en Ethereum.
   - **Verifiable Credentials y DIDs**:
     - **[Decentralized Identity Foundation (DIF)](https://identity.foundation/)**: Explora esta fundación que estandariza **DIDs** y **VCs**.
     - **[Veramo](https://identity.foundation/)** o **[uPort](https://www.uport.me/)**: Herramientas que soportan **SSI** y la gestión de **DIDs** y **VCs**.
   - **Wallets compatibles con eIDAS2**:
     - **MetaMask** o **Trinsic**: Estos wallets permiten interactuar con Ethereum y almacenar **VCs** y **DIDs**.
     - **[uPort](www.uport.me)**  funciona como un wallet de identidad digital descentralizada que permite la gestión de credenciales verificables y la autenticación segura, todo bajo el concepto de **Identidad Soberana Digital (SSI)**.

         **¿Cómo funciona uPort?**
       - Registro de Identidad:  
        Los usuarios crean una identidad digital en uPort, donde se les asigna un DID (identificador descentralizado), que es la base de su identidad soberana.
       - Almacenamiento de Credenciales:  
        Después de crear una identidad, los usuarios pueden recibir credenciales verificables de diferentes entidades (como universidades para títulos académicos, organismos gubernamentales, o plataformas comerciales).  
        Estas credenciales se almacenan de manera segura en el wallet de uPort.   
       - Interacción y Verificación:  
        El wallet de uPort permite a los usuarios compartir sus credenciales verificables con otras partes interesadas (empleadores, instituciones educativas, etc.) para que puedan ser verificadas de manera rápida y segura sin revelar más información de la necesaria.  
        Las credenciales son verificadas mediante blockchain, asegurando su autenticidad y evitando falsificaciones.


#### **2.2 Configuración del Proyecto**
   - **repositorio en GitHub**
   - Instalación y configuración de los **frameworks** de Ethereum (Truffle, Hardhat) y las bibliotecas para **SSI** (Veramo, uPort).

### 3. **Desarrollo de Contratos Inteligentes (Smart Contracts)** **(Solidity)**

#### **3.1 Crear el Contrato Inteligente para la Emisión de Credenciales** con **Solidity**
   - **Propósito**: El contrato debe permitir la creación, verificación y revocación de las **credenciales verificables (VCs)**.
   - **Estructura del contrato**:
     - el centro educativo de FP emite un **VC** con los datos del diploma (como nombre del estudiante, título, fecha de emisión).
     - El contrato firma digitalmente la credencial y la almacena en la **blockchain** de Ethereum.
     - Los estudiantes pueden recibir sus **VCs** a través de sus wallets y compartirlas con empleadores u otros verificadores.
   
  #### **3.2 Despliegue del Contrato Inteligente**
   - Usa **Truffle** o **Hardhat** para probar y desplegar tu contrato en la red Ethereum (testnet antes de usar la mainnet).
   - Interactúa con el contrato usando **Web3.js** o **Ethers.js** en el backend de tu proyecto.

### 4. **Implementación de la Identidad Digital SSI** **(Veramo)**

#### **4.1 Crear y Gestionar DIDs**
   - Los **DIDs** son identificadores descentralizados que representan a una entidad (como un estudiante o institución) en la blockchain.
   - Utiliza bibliotecas como **Veramo** o **uPort** para crear y gestionar **DIDs**.
   - Asegúrate de que los **DIDs** estén relacionados con las **credenciales verificables** emitidas por tu contrato inteligente.

#### **4.2 Verifiable Credentials (VCs)**
   - Las **VCs** son documentos digitales firmados que contienen información sobre un individuo (como un diploma).
   - Los **VCs** se emiten usando un DID de la universidad o institución y se almacenan en el **wallet** del estudiante.
   - **Veramo** o **uPort** son herramientas útiles para crear, almacenar y compartir estos documentos.

#### **4.3 Integración con el Wallet**
   - Los estudiantes recibirán su **VC** en un **wallet** compatible con **eIDAS2**.
   - El **wallet** elegido tiene que ser compatible con la firma electrónica avanzada de **eIDAS2**.
       - Se puede utilizar **uPort** con integración adicional
       - **[iDunion](https://idunion.org/?lang=en)** que es la paltaforma que se integra perfectamente con **elIDAS2** 
   - Los usuarios deben poder **firmar** sus documentos, verificar su identidad y compartir sus credenciales con otras partes de manera segura.

### 5. **Desarrollo del Backend y API de Verificación**

#### **5.1 Crear una API de Verificación de Credenciales**
   - Implementa una API en el backend que permita a los empleadores u otras instituciones verificar la validez de las credenciales.
   - La API debe interactuar con el **smart contract** para verificar si el **VC** es válido y no ha sido revocado.
   

### 6. **Integración de eIDAS2 en el Wallet**
   - El wallet debe cumplir con las normativas de **eIDAS2** para que las firmas electrónicas sean válidas dentro de la UE.
   - Utiliza **MetaMask**, **uPort**, o **Trinsic** para que los usuarios puedan gestionar sus **VCs**, realizar firmas electrónicas y compartir sus credenciales de manera legalmente válida.

### 7. **Pruebas y Despliegue**

#### **7.1 Pruebas**
   - Realiza pruebas exhaustivas en la testnet de Ethereum (como **Rinkeby** o **Goerli**) para asegurarte de que:
     - Los **contratos inteligentes** funcionan correctamente.
     - Los **VCs** se emiten y verifican correctamente.
     - El **wallet** interactúa bien con **eIDAS2** para firmas electrónicas.

#### **7.2 Despliegue en Mainnet**
   - Una vez que todas las pruebas sean satisfactorias, despliega los contratos inteligentes en la **mainnet de Ethereum** y habilita el sistema para su uso en producción.

### 8. **Documentación y Cumplimiento Legal**

   - Documenta todo el proceso de desarrollo, implementación y uso para que los usuarios entiendan cómo gestionar su identidad digital.
   - Asegúrate de que tu sistema cumpla con las normativas de privacidad y
