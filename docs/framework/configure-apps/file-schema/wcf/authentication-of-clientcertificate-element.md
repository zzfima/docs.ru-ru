---
title: "&lt;authentication&gt; элемента &lt;clientCertificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;authentication&gt; элемента &lt;clientCertificate&gt;
Указывает расширения функциональности аутентификации для сертификатов клиентов, используемых службой.  
  
## Синтаксис  
  
```  
  
<authentication  
customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
includeWindowsGroups="Boolean"  
mapClientCertificateToWindowsAccount="Boolean"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|customCertificateValidatorType|Необязательная строка.  Тип и сборка, используемые для проверки пользовательского типа.  Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.|  
|certificateValidationMode|Необязательное перечисление.  Задает один из режимов для проверки учетных данных.  Это атрибут типа [System.Servicemodel.Security.X509CertificateValidationMode](assetId:///System.Servicemodel.Security.X509CertificateValidationMode?qualifyHint=False&amp;autoUpgrade=True).  Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.  Значение по умолчанию — `ChainTrust`.|  
|includeWindowsGroups|Необязательный логический атрибут.  Указывает, включены ли группы Windows в контекст безопасности.  Установка для этого атрибута значения `true` снижает производительность, поскольку приводит к расширению всей группы.  Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.|  
|mapClientCertificateToWindowsAcccount|Логическое.  Указывает, может ли клиент сопоставляться с удостоверением Windows с помощью сертификата.  Для этого необходимо включить службу Active Directory.|  
|revocationMode|Необязательное перечисление.  Один из режимов, используемых для проверки списков отозванных сертификатов \(RCL\).  Значение по умолчанию — `Online`.  Это значение не учитывается при использовании безопасности транспорта HTTP.|  
|trustedStoreLocation|Необязательное перечисление.  Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.  Данное значение используется при согласовании сертификата службы для клиента.  Проверка выполняется для хранилища **Доверенные лица** в указанном местоположении хранилища.  Значение по умолчанию — `CurrentUser`.|  
  
## Атрибут customCertificateValidatorType  
  
|Значение|Описание|  
|--------------|--------------|  
|Строковое|Задает имя типа и сборку, а также другие данные, используемые для поиска типа.|  
  
## Атрибут certificateValidationMode  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Одно из следующих значений: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.<br /><br /> Дополнительные сведения см. в разделе [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Атрибут revocationMode  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Одно из следующих значений: NoCheck, Online, Offline.  Дополнительные сведения см. в разделе [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Атрибут trustedStoreLocation  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Одно из следующих значений: `LocalMachine` или `CurrentUser`.  Значение по умолчанию — `CurrentUser`.  Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.  Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|Определяет сертификат X.509, используемый для проверки подлинности клиента по отношению к службе.|  
  
## Заметки  
 Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.  Это дает возможность настраивать способ проверки подлинности клиентов.  Для атрибута `certificateValidationMode` можно задать значение `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` или `Custom`.  По умолчанию установлен уровень `ChainTrust`, который определяет, что каждый сертификат должен находиться в иерархии сертификатов, заканчивающейся *корневым центром* на вершине цепи.  Это наиболее безопасный режим.  Также можно установить значение `PeerOrChainTrust`, в этом случае будут приниматься как самостоятельно выдаваемые сертификаты \(доверие одноранговой группы\), так и сертификаты, которые находятся в цепи доверия.  Данное значение используется при разработке и отладке клиентов и служб, так как самостоятельно выданные сертификаты не нужно приобретать у доверенного центра сертификации.  При развертывании клиента вместо этого значения следует использовать значение `ChainTrust`.  
  
 Также можно установить значение `Custom`.  При установке значения `Custom` необходимо также задать атрибут `customCertificateValidatorType` для сборки и тип, который используется при проверке сертификата.  Для создания собственного пользовательского модуля проверки необходимо наследование от абстрактного класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  Дополнительные сведения см. в разделе [Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).  
  
## Пример  
 В следующем примере кода задается сертификат X.509 и пользовательский тип проверки в элементе `<authentication>`.  
  
```  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## См. также  
 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>   
 <xref:System.ServiceModel.Security.X509CertificateValidationMode>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>   
 <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)