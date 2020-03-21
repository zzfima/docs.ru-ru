---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152454"
---
# <a name="x509securitytokenhandlerrequirement"></a>\<x509SecurityTokenhandlerтребование>
Предоставляет дополнительную <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> конфигурацию для классов или производных классов.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerтребование>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|certificateValidationMode|Значение, <xref:System.ServiceModel.Security.X509CertificateValidationMode> опознавававававрежим проверки для использования для сертификата X.509. Значение по умолчанию — «PeerOrChainTrust».|  
|mapToWindows|Уточняется, следует ли обработчику маркеров отображения токена проверки в учетную запись Windows с помощью входящего требования UPN. Значение по умолчанию — «false».|  
|revocationMode|Значение, <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> оговариваев режим отзыва для использования для сертификата X.509. Значение по умолчанию "Онлайн".|  
|trustedStoreLocation|Значение, <xref:System.Security.Cryptography.X509Certificates.StoreLocation> опоедая магазин сертификатов X.509. Значение по умолчанию — «LocalMachine».|  
|сертификатВалистатор|Пользовательский тип, который <xref:System.IdentityModel.Selectors.X509CertificateValidator>происходит от . Если `certificateValidationMode` атрибут является "Custom", экземпляр этого типа используется для проверки сертификата эмитента.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<добавить>](add.md)|Добавляет указанный обработчик маркеров безопасности в коллекцию обработчика маркеров.|  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
