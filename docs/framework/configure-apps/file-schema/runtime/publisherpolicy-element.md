---
title: '&lt;publisherPolicy&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cc3b7220fe34f5dc049a3da71b160a88f82fdb1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltpublisherpolicygt-element"></a>&lt;publisherPolicy&gt; элемент
Указывает, применяет ли среда выполнения политику издателя.  
  
 \<configuration>  
\<Среда выполнения >  
\<assemblyBinding >  
\<dependentAssembly >  
\<publisherPolicy >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`apply`|Указывает, будет ли применяться политика издателя.|  
  
## <a name="apply-attribute"></a>Применение атрибута  
  
|Значение|Описание|  
|-----------|-----------------|  
|`yes`|Применяет политику издателя. Этот параметр используется по умолчанию.|  
|`no`|Политика издателя не применяется.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Если разработчик компонентов выпускает новую версию сборки, поставщика могут включать политики издателя, приложения, использующие старую версию, теперь будут использовать новую версию. Чтобы указать, будет ли применяться политика издателя для определенной сборки, поместите  **\<publisherPolicy >** элемент в  **\<dependentAssembly >** элемента.  
  
 Значение по умолчанию для **применить** атрибут **Да**. Установка **применить** атрибут **не** переопределит все предыдущие **Да** параметры для сборки.  
  
 Требуется разрешение для приложения, чтобы явно игнорировать политику издателя с помощью [ \<исполняемым = «no» / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) в файле конфигурации приложения. Разрешение можно получить, установив <xref:System.Security.Permissions.SecurityPermissionFlag> флаг <xref:System.Security.Permissions.SecurityPermission>. Дополнительные сведения см. в разделе [разрешение безопасности перенаправления привязки сборок](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Пример  
 В следующем примере производится отключение политики издателя для сборки, `myAssembly`.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [Перенаправление версий сборки](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
