---
title: '&lt;customCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 61b128d5856fd8e35516949b637177dc38a17164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomcookiehandlergt"></a>&lt;customCookieHandler&gt;
Задает тип обработчика пользовательского файла cookie. Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемента является «Custom». Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
\<cookieHandler >  
\<customCookieHandler >  
  
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
|type|Задает пользовательский тип, который является производным от <xref:System.IdentityModel.Services.CookieHandler> класса. Дополнительные сведения о способах указания `type` см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> используется для чтения и записи файлов cookie.|  
  
## <a name="remarks"></a>Примечания  
 При указании обработчика пользовательского файла cookie, задав `mode` атрибут `<cookieHandler>` элемент на «Custom», необходимо указать тип обработчика пользовательского файла cookie, включая `<customCookieHandler>` дочерний элемент, который ссылается на тип обработчика файлов cookie. Этот элемент не может быть указано при `mode` атрибута задано значение «Chunked» или «Default». Обработчики пользовательских куки-файл должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.  
  
 `<customCookieHandler>` Представлен <xref:System.IdentityModel.Configuration.CustomTypeElement> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере настраивается SAM использование куки-файл пользовательского обработчика типа `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Services.CookieHandler>
