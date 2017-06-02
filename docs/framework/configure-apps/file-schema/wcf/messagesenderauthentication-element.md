---
title: "Элемент &lt;messageSenderAuthentication&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Элемент &lt;messageSenderAuthentication&gt;
Задает параметры проверки подлинности для одноранговых отправителей сообщений.  
  
 Дополнительные сведения об одноранговом программировании см. в разделе [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## Синтаксис  
  
```  
  
<messageSenderAuthentication  
customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|customCertificateValidatorType|Тип и сборка, используемые для проверки пользовательского типа.  Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.|  
|certifcateValidationMode|Задает один из трех режимов для проверки учетных данных.  Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.|  
|revocationMode|Один из режимов, используемых для проверки списков отозванных сертификатов \(CRL\).|  
|trustedStoreLocation|Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.  Данное значение используется при согласовании сертификата службы для клиента.  Проверка выполняется для хранилища **Доверенные лица** в указанном местоположении хранилища.|  
  
## Атрибут customCertificateValidatorType  
  
|Значение|Описание|  
|--------------|--------------|  
|Строковое|Необязательно.  Задает имя типа и сборку, а также другие данные, используемые для поиска типа.  Требуется, как минимум, пространство имен и имя типа.  К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.|  
  
## Атрибут certificateValidationMode  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Необязательно.  Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.  Значение по умолчанию — `ChainTrust`.  Значение по умолчанию — `ChainTrust`.<br /><br /> Для получения дополнительной информации см. [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Атрибут revocationMode  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Одно из следующих значений: `NoCheck`, `Online`, `Offline`.  Значение по умолчанию — `Online`.<br /><br /> Для получения дополнительной информации см. [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Атрибут trustedStoreLocation  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Одно из следующих значений: `LocalMachine` или `CurrentUser`.  Значение по умолчанию — `CurrentUser`.  Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.  Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.  Значение по умолчанию — `CurrentUser`.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.|  
  
## Заметки  
 Этот элемент должен быть настроен, если выбрана проверка подлинности сообщения.  Для каналов вывода каждое сообщение подписывается с помощью сертификата, предоставленного [\<certificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md).  Во всех сообщениях перед доставкой приложению проверяются учетные данные сообщения с помощью модуля проверки, заданного атрибутом `customCertificateValidatorType` этого элемента.  Модуль проверки может принять или отклонить учетные данные.  
  
## Пример  
 В приведенном ниже примере кода устанавливается режим проверки отправителя сообщения `PeerOrChainTrust`.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
      <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
        <messageSenderAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
       <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
```  
  
## См. также  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>   
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/ru-ru/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/ru-ru/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)