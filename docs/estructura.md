La estructura de un proyecto que siga los estándares **EBSI**, **SSI** y **eIDAS2** basado en **Ethereum** involucra tres componentes clave: 
**contratos inteligentes en Ethereum**, un sistema de **Identidad Digital Autogestionada (SSI)** utilizando **DIDs** y **VCs**, y un **wallet compatible con eIDAS2** 
para gestionar la identidad y las credenciales. Los usuarios pueden recibir, almacenar y compartir sus credenciales de forma segura, y los verificadores pueden validarlas 
a través de la blockchain
### 1. **Estructura del Proyecto**
Un proyecto de Ethereum que cumpla con los estándares EBSI, SSI y eIDAS2 incluirá los siguientes componentes clave:

#### **A. Contratos Inteligentes (Smart Contracts)**
   - **Propósito**: Los contratos inteligentes permiten crear, gestionar y verificar la validez de las credenciales (por ejemplo, diplomas, certificados, etc.) directamente en la blockchain.
   - **Tecnología**: El código de los contratos inteligentes debe implementarse en **Solidity** (el lenguaje más utilizado para Ethereum).
   - **Funciones**: 
     - **Emitir credenciales** verificables.
     - **Registrar eventos** como la emisión, actualización o revocación de credenciales.
     - Verificar la **autenticidad** y **validez** de las credenciales.
   - **Interacción**: Los contratos inteligentes pueden interactuar con otros contratos o con aplicaciones externas, como **wallets** y **aplicaciones de verificación**.

#### **B. Sistema de Identidad Digital (SSI)**
   - **Propósito**: El sistema de **Identidad Digital Autogestionada (SSI)** permite que los usuarios sean dueños y controlen sus credenciales sin depender de una entidad centralizada.
   - **Tecnología**:
     - **Verifiable Credentials (VCs)**: Credenciales digitales firmadas criptográficamente que contienen datos verificables.
     - **Decentralized Identifiers (DIDs)**: Identificadores descentralizados que están registrados en una blockchain (en este caso, Ethereum).
   - **Implementación en Ethereum**:
     - **VCs y DIDs** se gestionan a través de contratos inteligentes en la blockchain de Ethereum.
     - Las credenciales pueden ser emitidas por autoridades certificadoras (por ejemplo, universidades) y almacenadas en wallets compatibles con **eIDAS2**.

#### **C. Wallets Compatibles con eIDAS2**
   - **Propósito**: Los **wallets** permiten a los usuarios almacenar y gestionar sus credenciales verificables, así como interactuar con servicios de **identidad digital** basados en blockchain.
   - **eIDAS2**: Es la normativa europea que regula la identidad digital electrónica, y los wallets que cumplen con eIDAS2 permiten la verificación y firma de documentos de forma legalmente vinculante.
   - **Características**:
     - **Almacenamiento de credenciales verificables** (por ejemplo, diplomas).
     - **Firma electrónica** y **verificación** de documentos.
     - Interacción con **DIDs** y **VCs**.
     - Compatible con el **esquema de confianza de eIDAS2**.
   - **Tecnología**: Los wallets pueden ser implementados usando tecnologías como **MetaMask**, **Trinsic**, **uPort**, entre otros, y deben ser compatibles con las especificaciones de **DIDs** y **VCs**.

### 2. **Flujo de Trabajo en el Proyecto (Paso a Paso)**

#### **Paso 1: Emisión de Credenciales**
1. **Emisor de la Credencial (ej., Instituto FP)**:
   - El Instituto FP emite un **Verifiable Credential (VC)** con los detalles del diploma.
   - El VC se firma con la clave privada del emisor (Instituto FP) y se almacena en la blockchain de Ethereum a través de un **smart contract**.
   - El **DID (Decentralized Identifier)** del emisor (Instituto FP) se utiliza para garantizar la **autenticidad** de la credencial.

2. **Smart Contract**:
   - El contrato inteligente se encarga de gestionar la emisión, actualización y revocación de las credenciales.
   - Este contrato almacena las **huellas criptográficas** de las credenciales verificables en la blockchain.

#### **Paso 2: Almacenamiento y Gestión en el Wallet**
1. **Usuario/Estudiante**:
   - El estudiante recibe el **Verifiable Credential (VC)** en su **wallet** compatible con eIDAS2, como **MetaMask**, **Trinsic**, o un wallet basado en Ethereum.
   - El wallet está habilitado para almacenar **credenciales verificables (VCs)** y **DIDs**, lo que permite que el estudiante tenga control total sobre su identidad digital.

2. **eIDAS2 Compliance**:
   - El wallet permite que el estudiante firme y autentique documentos de manera que cumpla con las regulaciones de **eIDAS2**.
   - Además, el wallet debe estar en conformidad con las normativas de **firma electrónica avanzada** y **identidad electrónica** de **eIDAS2**.

#### **Paso 3: Verificación de Credenciales**
1. **Verificador (ej., empresa, institución educativa)**:
   - Un verificador puede consultar el **smart contract** en Ethereum para validar la autenticidad de las credenciales.
   - El verificador utiliza la **dirección DID** del emisor (por ejemplo, Instituto FP) para verificar la **firma digital** y confirmar la **validez** de la credencial.

2. **Verificación en la Blockchain**:
   - El verificador consulta el **VC** a través de la blockchain y valida su **firma** utilizando el **DID** del emisor registrado en la red.
   - Si la transacción está registrada en la blockchain, el verificador puede estar seguro de que la credencial es auténtica y no ha sido alterada.

### 3. **Tecnologías y Herramientas**

#### **A. Herramientas de Blockchain**:
   - **Ethereum**: La blockchain base para gestionar las credenciales y los contratos inteligentes.
   - **Truffle/Hardhat**: Herramientas para desarrollar, probar y desplegar contratos inteligentes en Ethereum.
   - **Infura/Alchemy**: Para interactuar con la blockchain de Ethereum sin necesidad de gestionar tu propio nodo.

#### **B. Herramientas de SSI**:
   - **Verifiable Credentials (VC)** y **Decentralized Identifiers (DID)**: Usados para crear y gestionar la identidad digital.
   - **DIF (Decentralized Identity Foundation)**: Estándares y herramientas que soportan SSI.
   - **Veramo**: Framework para la creación y gestión de **DIDs** y **VCs** en aplicaciones.

#### **C. Herramientas de Wallets eIDAS2**:
   - **MetaMask**: Para gestionar y almacenar **DIDs** y **VCs**.
   - **uPort** y **Trinsic**: Plataformas para crear wallets de identidad digital compatibles con **eIDAS2**.
   - **Verifiable Credential Wallets**: Soluciones que permiten almacenar y compartir credenciales verificables en cumplimiento con **eIDAS2**.

### 4. **Diagrama de Flujo**

```
+------------------------+      +---------------------+       +------------------+
|   Emisor (Instituto FP)  | ---> | Smart Contract (ETH) | ---> | Verificador (Emp) |
| - Emitir VC (Diploma)   |      | - Registrar VC       |       | - Verificar VC    |
| - Firmar con DID        |      | - Verificar VC       |       | - Validar Firma   |
+------------------------+      +---------------------+       +------------------+
              |                           |                           |
              |                           |                           |
    +------------------------+      +----------------------+   +----------------------+
    |    Wallet del Usuario   | <--- |   Interacción con     | < | Verificación en la Blockchain |
    |   (Alumno)               |      |   el Wallet (MetaMask) |   | (Ethereum)               |
    | - Almacenar VC (Diploma) |      | - Firmar y Almacenar   |   | - Consultar el estado   |
    | - Control total de DID   |      |   Credenciales         |   | - Validación de VC      |
    +------------------------+      +----------------------+   +----------------------+
```

### 5. **Consideraciones de Seguridad**
- **Criptografía**: Usar **firmas digitales** para garantizar la integridad y la autenticidad de las credenciales.
- **Privacidad**: Los datos personales deben ser cifrados y **solo compartidos con el consentimiento del usuario**.
- **Cumplimiento**: Asegúrate de que todas las transacciones y la gestión de identidad cumplan con las normativas de **eIDAS2**, **GDPR**, y otros estándares regulatorios europeos.
