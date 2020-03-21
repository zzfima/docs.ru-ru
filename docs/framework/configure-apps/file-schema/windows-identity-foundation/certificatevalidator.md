---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 3f3d79d3567c1714a79423b7767ce3f454b9d52d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152792"
---
# <a name="certificatevalidator"></a>\<сертификатВалидатор>
Определяет пользовательский тип для проверки сертификата. Этот тип используется только `certificateValidationMode` в том случае, если атрибут [ \<сертификатаВалисация>](certificatevalidation.md) элемент установлен на "Custom".  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<сертификатВалиста>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<сертификатВалидатор>**  
  
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
  
|attribute|Описание|  
|---------------|-----------------|  
|type|Определяет пользовательский тип, который вытекает <xref:System.IdentityModel.Selectors.X509CertificateValidator> из класса. Установите `certificateValidationMode` атрибут [ \<сертификатаПроверка>](certificatevalidation.md) элементом "Custom" для использования этого типа. Для получения дополнительной информации `type` о том, как указать атрибут, см. [Custom Type References](../windows-workflow-foundation/index.md) Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<сертификатВалиста>](certificatevalidation.md)|Контролирует настройки, которые обработчики маркеров используют для проверки сертификатов.|  
  
## <a name="example"></a>Пример  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
