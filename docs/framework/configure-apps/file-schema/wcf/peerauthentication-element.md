---
title: "Элемент &lt;peerAuthentication&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Элемент &lt;peerAuthentication&gt;
Задает параметры проверки подлинности для одноранговых клиентов.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] одноранговом программировании см. в разделе [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## Синтаксис  
  
```  
  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
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
|`customCertificateValidatorType`|Необязательная строка.  Тип и сборка, используемые для проверки пользовательского типа.  Этот атрибут должен быть задан, когда `certificateValidationMode` имеет значение `Custom`.|  
|`certifcateValidationMode`|Необязательное перечисление.  Задает один из трех режимов для проверки учетных данных.  Если свойству присвоено значение `Custom`, также необходимо указать свойство `customCertificateValidator`.  Значение по умолчанию — `ChainTrust`.|  
|`revocationMode`|Необязательное перечисление.  Один из режимов, используемых для проверки списков отозванных сертификатов \(CRL\).  Значение по умолчанию — `Online`.|  
|`trustedStoreLocation`|Необязательное перечисление.  Одно из двух местоположений системного хранилища: `LocalMachine` или `CurrentUser`.  Данное значение используется при согласовании сертификата службы для клиента.  Проверка выполняется для хранилища **Доверенные лица** в указанном местоположении хранилища.  Значение по умолчанию — `CurrentUser`.|  
  
## Атрибут customCertificateValidatorType  
  
|Значение|Описание|  
|--------------|--------------|  
|Строковое|Задает имя типа и сборку, а также другие данные, используемые для поиска типа.  Требуется, как минимум, пространство имен и имя типа.  К дополнительным сведениям относятся: имя сборки, номер версии, язык и региональные параметры и маркер открытого ключа.|  
  
## Атрибут certificateValidationMode  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Одно из следующих значений: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`.  Значение по умолчанию — `ChainTrust`.<br /><br /> Для получения дополнительной информации см. [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Атрибут revocationMode  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Одно из следующих значений: `NoCheck`, `Online`, `Offline`.  Значение по умолчанию — `Online`.<br /><br /> Для получения дополнительной информации см. [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).|  
  
## Атрибут trustedStoreLocation  
  
|Значение|Описание|  
|--------------|--------------|  
|Перечисление|Одно из следующих значений: `LocalMachine` или `CurrentUser`.  Значение по умолчанию — `CurrentUser`.  Если клиентское приложение выполняется под учетной записью системы, сертификат обычно находится в расположении `LocalMachine`.  Если клиентское приложение выполняется под учетной записью пользователя, то сертификат обычно находится в расположении `CurrentUser`.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к одноранговой службе.|  
  
## Заметки  
 Элемент `<authentication>` соответствует классу <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>.  Этот элемент задает модуль проверки, который вызывается во время проверки подлинности «от соседа к соседу» в сетке.  Когда новый одноранговый узел пытается установить соединение с соседним узлом, он передает свои учетные данные в отвечающий одноранговый узел.  Для проверки учетных данных удаленной стороны вызывается проверяющий элемент управления отвечающего узла.  Как только в сетке устанавливается одноранговое соединение, оба одноранговых узла выполняют взаимную проверку подлинности. Это означает, что вызываются проверяющие элементы управления на обоих концах.  
  
## Пример  
 В приведенном ниже примере кода режиму проверки сертификата присваивается значение `PeerOrChainTrust`.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>   
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>   
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Одноранговая сеть](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/ru-ru/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/ru-ru/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [Защита приложений одноранговых каналов](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)