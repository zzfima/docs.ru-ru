---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152584"
---
# <a name="servicetokenresolver"></a>\<serviceTokenResolver>
Регистрирует разрешителер маркеров службы, используемый обработчиками в коллекции обработчиков токенов. Разрешители токенов службы используются для разрешения маркера шифрования на входящих токенах и сообщениях.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenhandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|type|Определяет тип разрешительного маркера токенов службы. <xref:System.IdentityModel.Selectors.SecurityTokenResolver> Тип или тип, который вытекает <xref:System.IdentityModel.Selectors.SecurityTokenResolver> из класса. Для получения дополнительной информации `type` о том, как указать атрибут, см. Обязательный элемент.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenhandlerConfiguration>](securitytokenhandlerconfiguration.md)|Обеспечивает конфигурацию для сбора обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Remarks  
 Разрешители токенов службы могут быть использованы для разрешения маркера шифрования на входящих токенах и сообщениях. Он используется для получения ключа, который должен быть использован для расшифровки входящих токенов. Необходимо указать `type` атрибут. Указанный тип может <xref:System.IdentityModel.Selectors.SecurityTokenResolver> быть либо или пользовательским <xref:System.IdentityModel.Selectors.SecurityTokenResolver> типом, который вытекает из класса.  
  
 Некоторые обработчики маркеров позволяют указать настройки разрешителя маркеров службы в конфигурации. Настройки отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.  
  
> [!NOTE]
> Определение элемента `<serviceTokenResolver>` в качестве элемента ребенка [ \<идентификационных конфигураций>](identityconfiguration.md) элемента было изуродовано, но по-прежнему поддерживается для обратной совместимости. Настройки элемента `<securityTokenHandlerConfiguration>` переопределяют элементы на элементе. `<identityConfiguration>`  
  
## <a name="example"></a>Пример  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
