# Evaluación-practica
## Ejercicio 1 - Instalación del ambiente

##### Enunciado: Instalación de las herramientas necesarias para el desarrollo de la evaluación.
###### Resolución:
Para la realización de la evaluación se procedió a la instalacion y configuración del ambiente de desarrollo solicitado, incorporando las siguientes herramientas:

**1. Visual Studio Code**

Se instalo Visual Studio Code, un IDE (Entorno de Desarrollo Integrado) utilizado para el desarrollo de aplicaciones web y móviles.
Esta herramienta facilita la escritura, organización y mantenimiento del código, permitiendo trabajar con múltiples leguajes y tecnologías como:
- **HTML**
- **CSS**
- **JavaScript**
- **C#**
- **NodeJS**
- **Angular**
- **React**
- **TypeScript**

Visual Studio Code destaca por su ligereza, extensibilidad mediante plugins y su integración con sistemas de control de versiones como Git.

**2. Git y Git Bash**

Se instaló Git, un sistema de control de versiones que permite gestionar y mantener un historial de cambios del código fuente.
Con Git es posible:
- Versionar archivos del proyecto
- Mantener un respaldo de versiones anteriores
- Restaurar cambios cuando sea necesario
- Trabajar de forma colaborativa
- Almacenar el código en la nube mediante repositorios remotos (por ejemplo, GitHub)

Adicionalmente, se instaló Git Bash, una interfaz de línea de comandos que facilita la ejecución de comando Git y la interacción con repositorios desde un entorno de consola.


## Ejercicio 2 - Protocolo HTTP


**1. ¿Qué es un servidor HTTP?**

Un servidor HTTP es un sistema que recibe solicitudes (request) realizadas por clientes, generalmente navegadores web, y responde (responses) utilizando el protocolo HTTP.
Su función principal es procesar pedidos y devolver recursos como páginas web, archivos, datos o servicios.

**2. ¿Qué son los verbos HTTP?**

Los verbos HTTP indican la acción que el cliente desea realizar sobre un recurso.
Los más utilizados son:
- **GET:** Obtener información.
- **POST:** Enviar información.
- **PUT:** Actualizar un recurso existente.
- **DELETE:** Eliminar un recurso.
- **PATCH:** Actualizar parcialmente un recurso.

**3. ¿Qué es un reques y un response? ¿Qué son los headers?**

- **Request:** Es la solicitud que realiza el cliente al servidor.
- **Response:** Es la respuesta que devuelve el servidor al cliente.

Los headers son metadatos que acompañan al request y al response, y contienen información adicional como el tipo de contenido, autenticación, idioma, entre otros.

**4. ¿Qué es un queryString?**

Un queryString es un conjunto de parámetros que se envían en una URL para transmitir información adicional al servidor.

**5. ¿Qué es el responseCode?**

El responseCode (codigo de estado HTTP) indica el resultado de una solicitud realizada a servidor.
Agrupados en categorías como:
- **2xx:** Éxito (ej. 200 OK)
- **3xx:** Redirección
- **4xx:** Error del cliente (ej. 404 Not Found)
- **5xx:** Error del servidor (ej. 500 Internal Server Error)

**6. ¿Cómo se envia la data en un GET y en un POST?**

- **GET**: La información se envía a través de la URL mediante queryStrings.
- **POST**: La información se envía en el cuerpo (body) de la solicitud, de forma mas segura y sin ser visible en la URL.

**7. ¿Qué verbo HTTP utiliza el navegador al acceder a una pagina?**

El navegador utiliza el verbo **GET** para solicitar el contenido de una página web.

**8. ¿Qué son JSON y XML?**

JSON (JavaScrip Object Notation) y XML (eXtensible MArkup Language) son formatos de intercabio de datos.

Ejemplo JSON:
```json
{
	"nombre" : "Rocio",
	"edad" : 22
}
```
Ejemplo XML:
```xml
<usuario>
	<nombre>Rocio</nombre>
	<edad>22</edad>
</usuario>
```

JSON es mas liviano y ampliamente utilizado en APIs modernas, mientras que XML es mas estructurados y verboso.

**9. ¿Qué es el estandar SOAP?**

**SOAP (Simple Object Access Protocol)** es un protocolo de comunicación basado en XML que define reglas estrictas para el intercambio de información entre sistemas, comunmente utilizado en servicios empresariales.

**10. ¿Qué es el estandar REST full?**

**REST full** es un estilo de arquitectura para el diseño de APIs que utiliza los verbos HTTP para operar sobre recursos.
Se caracteriza por ser liviano, escalable y generalmente utiliza JSON como formato de intercambio de datos.

**11. ¿Qué son los headers en un request?¿Para qué se utiliza Content-Type?**

Los headers en un request contienen información adicional que describe la solicitud.
El header Content-Type indica el formato de los datos que se estan enviando al servidor, por ejemplo:
- `application/json`
- `application/xml`
- `text/html`

## Ejercicio 3 - Request con Postman y JSON
##### Enunciado: Realizar request HTTP utilizando Postman para interactuar con un endpoint, la cual permite realizar solicitudes HTTP simulando el comportamiento de un cliente.
###### Resolución:
1. Request GET - Obtención de contactos

Se realizó un request GET a la siguente URL:

[https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts.json](https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts.json)

Este request permitió obtener la información almacenada en el servidor en formato JSON, devolviendo un listado de contactos existentes.

![](https://raw.githubusercontent.com/RocioAranibar/evaluacion-practica/refs/heads/RocioAranibar-patch-1/Captura.JPG)

2. Request POST - Creacion de nuevo contacto

Se realizó un request POST a la misma URL con el siguiente body, utilizando la opción raw y formato JSON:
```json
{
  "name": "Rocio",
  "email": "rocio.aranibar@procontacto.com.mx"
}
```
Este request permitió enviar información al servidor y crear un nuevo registro de contacto.
Como respuesta, el servidor devolvió un identificador único para el nuevo recurso creado.

![](https://raw.githubusercontent.com/RocioAranibar/evaluacion-practica/refs/heads/RocioAranibar-patch-1/Captura2.JPG)

3. Request GET - Verificación de datos
Se realizó nuevamente un request GET a la URL:
[https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts.json](https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts.json)

En esta ocasión, la respuesta incluyó el nuevo contacto previamente creado mediante el request POST.

![](https://raw.githubusercontent.com/RocioAranibar/evaluacion-practica/refs/heads/RocioAranibar-patch-1/Captura3.JPG)

La principal diferencia entre ambas llamadas es que:
- En el punto 1, el GET devuelve únicamente los contactos existentes antes de realizar el POST.
- En el punto 3, el GET devuelve la lista actualizada de contactos, incluyendo el nuevo registro agregado.

Esto demuestra como un request POST modifica el estado del recurso en el servidor y como un GET refleja los cambios.

## Ejercicio 4 - Trailhead
##### Enunciado: Completar los módulos de Trailhead en ingles y compartir el perfil público
###### Resolución:
Se realizó el cambio de idioma de Trailhead a inglés y se completaron los siguientes módulos utilizando el mismo Playground:
- Fundamentos de la plataforma Salesforce
- Fundamentos de Apex y .NET
- Modelado de datos
- Fundamentos y base de datos de Apex
- Desencadenadores de Apex
Apex Integration Services

Para evidenciar la finalización de los módulos, se comparte el perfil público de Trailhead:
[https://www.salesforce.com/trailblazer/ej78wr3ax4hzkg6axp](https://www.salesforce.com/trailblazer/ej78wr3ax4hzkg6axp)

------------

## Ejercicio 5 - Objetos estandar de Salesforce

**1. Lead**
Un lead representa un posible cliente que aún no fue calificado.
##### Campos estándar:
- First Name
- Last Name
- Company
- Email
- Phone
- Status
- Lead Source

##### Relación: Puede convertirse en Account, Contact y Opportunity.

**2. Account**
Representa una empresa u organización con la que se mantiene una relación comercial.
##### Campos estándar:
- Type
- Industry
- Phone
- Website
- Billing Address

##### Relación: Una Account puede tener muchos Constacts, Opportunities, Assets y Cases.

**3. Contact**
Persona asociada a una cuenta.
##### Campos estándar:
- First Name
- Last Name
- Email
- Phone
- Account Id
- Title

##### Relación: Pertenece a una Account

**4. Oppotunity**
Representa una venta en curso.
##### Campos estándar:
- Opportunity Name
- Amount
- Close Date
- Stage
- Account Id

##### Relación: Pertenece a una Account y puede tener Products y Quotes.

**5. Product**
Producto o servicio que la empresa ofrece.
##### Campos estándar:
- Product Name
- Product Code
- Description
- Active

##### Relación: Se asocia a Opportunities mediante PriceBooks.

**6.  PriceBook**
Lista de precios que define cuánto cuesta cada producto.
##### Campos estándar:
- Price Book Name
- Description
- Active

##### Relación: Relaciona Products con Opportunities.

**7. Quotes**
Cotización generada a partir de una Opportunity.
##### Campos estándar:
- Quote Name
- Status
- Expiration Date
- Opportunity Id

##### Relación: Pertenece a una Opportunity.

**8. Asset**
Producto adquirido por un cliente.
##### Campos estándar:
- Asset Name
- Serial Number
- Install Date
- Account Id

##### Relación: Pertenece a una Account.

**9. Case**
Solicitud de soporte o reclamo de un cliente.
##### Campos estándar:
- Case Number
- Subject
- Status
- Priority
- Account Id

##### Relación: Pertenece a una Account

**10. Article**
Artículo de conocimiento para soporte.
##### Campos estándar:
- Titlle
- Summary
- Content
- Status

##### Relación: No tiene relacion directa obligatoria con otros objetos.

## Diagrama de Relaciones:
![](https://raw.githubusercontent.com/RocioAranibar/evaluacion-practica/refs/heads/RocioAranibar-patch-2/Captura10.JPG)

------------

## Ejercicio 6 - Conceptos de Salesforce

### Soluciones de Salesforce

**A . ¿Qué es Salesforce?**

Es una platafrma CRM en la nube que permite gestionar ventas, servicio, marketing y relaciones con clientes.

**B. ¿Qué es Sales Cloud?**

Solución enfocada en la gestión de ventas, oportunidades, leads y pipeline comercial.

**C. ¿Qué es Service Cloud?**

Solución enfocada a la atención al cliente y soporte mediante casos, canales digitales y automatizaciones.

**D. ¿Qué es Health Cloud?**

Plataforma especializada para el sector salud, que centraliza datos clinicos y de pacientes.

**E. ¿Qué es Marketing CLoud?**
 
 Herramienta para gestionar campañas de marketing digital, automatización y comunicaciones personalizadas.
 
###  Funcionalidades de Salesforce
 
**A. ¿Qué es un RecordType?**
 
 Permite definir distintos procesos, layouts y picklists para un mismo objeto.
 
 **B. ¿Qué es un ReportType?**
 
 Define que objetos y relaciones pueden utilizarse en un reporte.
 
**C. ¿Qué es un Page Layout?**
 
 Controla la disposición de campos, botones y secciones en un registro.
 
**D. ¿Qué es un Compact Layout?**
 
 Define los campos que se muestran en vistas compactas, especialmente en móbile.
 
**E. ¿Qué es un Perfil?**
 
 Define permisos de acceso a objetos, campos y funcionalidades.
 
**F. ¿Qué es un Rol?**
 
 Define la jerarquía de usuarios y el acceso a registros.
 
**G. ¿Qué es un Validation Rule?**
 
 Regla que valida datos antes de guardar un registro.
 
**H. ¿Diferencia entre Master Detail y Lookup?**
 - Master Detail: relación dependiente, con herencia de permisos.
 - Lookup: relación flexible e independiente.
 
 
**I. ¿Qué es un Sandbok?**
 
 Entorno de pruebas aislado del entorno productivo.
 
**J. ¿Qué es un ChangeSet?**
 
 Herramienta para mover configuraciones entre entornos Salesforce.
 
**K. ¿Para qué sirve el Import Wizard?**
 
 Permite importar datos de forma guiada desde archivos.
 
**L. ¿Para qué sirve Web to Lead?**
 
 Crea Leads automáticamente desde formularios web.
 
**M. ¿Para qué srive Web to Case?**
 
 Crea Cases automáticamente desde formularos web.
 
**N. ¿Para qué sirve Omnichannel?**
 
 Distribuye casos y tareas entre agentes de forma inteligente.
 
**O. ¿Para qué sirve Chatter?**
 
 Facilita la colaboración interna entre usuarios.
 
###  Conceptos Generales
 
**A. ¿Qué significa SaaS?**
 
 Sotfware como servicio accesible vía internet.
 
**B. ¿Salesforce es SaaS?**
 
 Sí, es una plataforma SaaS.
 
**C. ¿Qué significa Cloud?**
 
 Que la solución se aloja y ejecuta en la nube.
 
**D. ¿Qué significa On-Premise?**
 
 Que el software se instala en servidores propios.
 
**E. ¿Qué es un pipeline de ventas?**
 
 Visualización de oportunidades en distintas etapas.
 
**F. ¿Qué es un funnel de ventas?**
 
 Representación del proceso de conversión de clientes.
 
**G. ¿Qué es un Customer Experience?**
 
 Experiencia total del cliente con la marca.
 
**H. ¿Qué es omnicanalidad?**
 
 Integración de múltiples canales de atención.
 
 I. B2B, B2C y KPI
 - B2B: negocio entre empresas.
 - B2C: negocio hacia consumidores finales.
 - KPI: indicador clave de desempeño.
 
 
**J. ¿Qué es una API y una Rest API?**
 
 Una API permite comunicación entre sistemas.
 Rest API usa HTTP y estándares de REST.
 
**K. ¿Qué es un Proceso Batch?**
 
 Proceso que ejecuta grandes volúmenes de datos en segundo plano.
 
**L. ¿Qué es Kanban?**
 
 Método visual para gestionar tareas y flujos de trabajo.
 
**M. ¿Qué es un ERP?**
 
 Sistema para gestionar procesos internos de una empresa.
 
**N. ¿Salesforce es un ERP?**
 
 No. Salesforce es un CRM, aunque puede integrarse con ERPs.

## Ejercicio 7 - Trigger y Callout REST

Se desarrolló un trigger sobre Contact que invoca un servicio REST externo para actualizar el correo electrónico utilizando un identificador externo.

### Codigo Apex:
```json
trigger ContactTrigger on Contact (after insert, after update) {
    for (Contact c : Trigger.new) {
        if (c.idprocontacto__c != null) {
            ContactService.obtenerEmail(c.Id, c.idprocontacto__c);
        }
    }
}

```

### Calse Apex (REST Callout)
```json
public class ContactService {

    @future(callout=true)
    public static void obtenerEmail(Id contactId, String externalId) {

        Http http = new Http();
        HttpRequest req = new HttpRequest();

        String endpoint = 'https://procontacto-reclutamiento-default-rtdb.firebaseio.com/contacts/'
                          + externalId + '.json';

        req.setEndpoint(endpoint);
        req.setMethod('GET');

        HttpResponse res = http.send(req);

        if (res.getStatusCode() == 200) {
            Map<String, Object> data =
                (Map<String, Object>) JSON.deserializeUntyped(res.getBody());

            if (data.containsKey('email')) {
                Contact c = new Contact(
                    Id = contactId,
                    Email = (String) data.get('email')
                );
                update c;
            }
        }
    }
}

```
![](https://raw.githubusercontent.com/RocioAranibar/evaluacion-practica/refs/heads/RocioAranibar-patch-3/Ejercicio7.JPG)

![](https://raw.githubusercontent.com/RocioAranibar/evaluacion-practica/refs/heads/RocioAranibar-patch-3/Ejercicio7.2.JPG)
