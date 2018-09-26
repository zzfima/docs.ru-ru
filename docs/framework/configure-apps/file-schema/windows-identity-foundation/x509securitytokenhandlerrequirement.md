---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 994677904cada71dbc7cce4b6ca0de1d4dc65014
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085667"
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a>&lt;x509SecurityTokenHandlerRequirement&gt;
Предоставляет вариант конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> классом или производными классами.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<add>  
\<x509SecurityTokenHandlerRequirement >  
  
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
  
|Атрибут|Описание|  
|---------------|-----------------|  
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, определяющее режим проверки для сертификата X.509. Значение по умолчанию — «PeerOrChainTrust».|  
|mapToWindows|Указывает ли обработчик токенов следует сопоставить маркер проверки в учетную запись Windows с помощью входящего утверждения имени участника-пользователя. Значение по умолчанию — «false».|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, определяющее режим отзыва для сертификата X.509. Значение по умолчанию — «В сети».|  
|trustedStoreLocation|Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, которое указывает хранилище сертификатов X.509. Значение по умолчанию — «LocalMachine».|  
|certificateValidator|Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>. Если `certificateValidationMode` атрибут «Custom», экземпляр этого типа используется для проверки сертификата издателя.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.|  
  
## <a name="example"></a>Пример  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
