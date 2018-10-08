---
title: '&lt;certificateValidator&gt;'
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 65b8aa6fa4422579ce0d1c5e33d3418ea051612a
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/08/2018
ms.locfileid: "48849702"
---
# <a name="ltcertificatevalidatorgt"></a>&lt;certificateValidator&gt;
Задает пользовательский тип для проверки сертификата. Этот тип используется только в том случае, если `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) имеет значение «Custom».  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<certificateValidation >  
\<certificateValidator >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Задает пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса. Задайте `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) элемент на «Пользовательский», чтобы использовать этот тип. Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). Необязательный.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Управляет параметрами, используемых обработчиками токена для проверки сертификатов.|  
  
## <a name="example"></a>Пример  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
