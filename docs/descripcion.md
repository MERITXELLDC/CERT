## Descripción del Proyecto

#### Los nuevos estándares tecnológicos y europeos (Blockchain, identidad digital autosoberana SSI, eIDAS2 y EBSI) aplicables en un sistema de credenciales verificables para una formación  modular y acumulable de la nueva FP.

Cert es el proyecto que realizará la implementación de un sistema de acreditación de
titulaciones adaptado al marco de la nueva ley de Formación Profesional utilizando el
estándar europeo EBSI basado en la tecnología Blockchain. Permitirá también que las
entidades empleadoras puedan acreditar los logros obtenidos por los trabajadores.
El ciudadano siempre tendrá control sobre quién puede visualizar su “cartera digital de
acreditaciones -wallet-”.
Significa un cambio radical que implica la simplificación de trámites, garantía de veracidad de
la información registrada en el sistema y mejora en el intercambio de información entre los
diferentes sistemas formativos y laborales, incluyendo posibles convalidaciones.
EBSI está basado en web3: “digital wallets”, credenciales verificables (eDiploma) y Blockchain.


### Como funciona?

El centro de Formación Profesional  (entidad emisora) que emite una credencial sobre un alumno indicando que ha superado un título. 
El alumno (propietario de la identidad) acepta dicha credencial (avalada por una entidad emisora, su centro educativo) incorporándola a su identidad digital, que estará en una especie de “cartera digital”, un programa que la gestiona.
El alumno realiza una solicitud para trabajar en una empresa, que solicita verificar la credencial emitida por el centro educativo para asegurarse que el alumno dispone del título.

![Esquema 1](blockchain-grafica.png)

### Conceptos a tener en cuenta

![Esquema 2](general.png)

### Documentos DID
Un **DID Document** (Documento de Identificador Descentralizado) es un archivo que contiene información para verificar la identidad de una entidad (persona, organización o dispositivo) en una red descentralizada. 
Este documento está asociado a un **DID** (Decentralized Identifier) y se utiliza en sistemas de identidad soberana (Self-Sovereign Identity, SSI).

#### Estructura básica de un Documento DID

1. **Contexto (`@context`)**: Define el marco de referencia (JSON-LD) para interpretar el contenido.
   
2. **Identificador (`id`)**: Es el DID que identifica de forma única a la entidad en la red.

3. **Claves públicas (`publicKey`)**: Son las claves que permiten verificar la autenticidad de la identidad; pueden incluir métodos de verificación criptográfica.

4. **Métodos de autenticación (`authentication`)**: Especifica cómo se puede autenticar la identidad, utilizando una de las claves públicas.

5. **Servicios (`service`)**: Define servicios asociados al DID, como puntos de contacto o endpoints para intercambiar datos.

### Ejemplo sencillo de un Documento DID en JSON

```json
{
  "@context": "https://www.w3.org/ns/did/v1",
  "id": "did:example:123456789abcdef",
  "publicKey": [
    {
      "id": "did:example:123456789abcdef#keys-1",
      "type": "RsaVerificationKey2018",
      "controller": "did:example:123456789abcdef",
      "publicKeyPem": "-----BEGIN PUBLIC KEY...END PUBLIC KEY-----"
    }
  ],
  "authentication": [
    "did:example:123456789abcdef#keys-1"
  ],
  "service": [
    {
      "id": "did:example:123456789abcdef#service-1",
      "type": "VerifiableCredentialService",
      "serviceEndpoint": "https://example.com/credentials"
    }
  ]
}
```

