---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: c25f183679f41f51ffee4f482bfe7a64763647d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941903"
---
# <a name="certificatevalidator"></a>\<Цертификатевалидатор >
Указывает пользовательский тип для проверки сертификата. Этот тип используется только в том случае `certificateValidationMode` , если атрибуту [ \<элемента цертификатевалидатион >](certificatevalidation.md) присвоено значение Custom.  
  
 \<> System. identityModel  
\<identityConfiguration >  
\<Цертификатевалидатион >  
\<Цертификатевалидатор >  
  
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
|type|Указывает пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса. Задайте для `certificateValidationMode` [ атрибута\<элемента > цертификатевалидатион](certificatevalidation.md) значение Custom, чтобы использовать этот тип. Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md). Необязательный параметр.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Цертификатевалидатион >](certificatevalidation.md)|Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.|  
  
## <a name="example"></a>Пример  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />    
</certificateValidation>        
```
