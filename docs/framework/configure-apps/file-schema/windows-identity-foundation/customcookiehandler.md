---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a3d032279d0b568d7072dbbe020344365c341c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724022"
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
Задает тип обработчика пользовательских файлов cookie. Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемент является «Custom». Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 \<system.identityModel.services>  
\<federationConfiguration>  
\<cookieHandler >  
\<customCookieHandler>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Задает пользовательский тип, производный от <xref:System.IdentityModel.Services.CookieHandler> класса. Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> используется для чтения и записи файлов cookie.|  
  
## <a name="remarks"></a>Примечания  
 При указании пользовательский обработчик файлов cookie, задав `mode` атрибут `<cookieHandler>` элемент на «Пользовательский», необходимо указать тип пользовательский обработчик файлов cookie, включив `<customCookieHandler>` дочерний элемент, ссылающийся на тип обработчика файлов cookie. Этот элемент не может быть указан при `mode` атрибут имеет значение «Chunked» или «Default». Обработчики пользовательских файлов cookie должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 `<customCookieHandler>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.CustomTypeElement> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере настраивается SAM, чтобы использовать пользовательский обработчик типа `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.IdentityModel.Services.CookieHandler>
