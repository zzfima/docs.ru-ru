---
title: Элемент <publisherPolicy>
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
ms.openlocfilehash: cc206e584440778858e61fc0bab51fc8ffa2009a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252383"
---
# <a name="publisherpolicy-element"></a>\<Элемент > Publisherpolicy Apply
Указывает, применяет ли среда выполнения политику издателя.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Publisherpolicy Apply >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`apply`|Указывает, следует ли применять политику издателя.|  
  
## <a name="apply-attribute"></a>применить атрибут  
  
|Значение|Описание|  
|-----------|-----------------|  
|`yes`|Применяет политику издателя. Этот параметр используется по умолчанию.|  
|`no`|Политика издателя не применяется.|  
  
### <a name="child-elements"></a>Дочерние элементы  

Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`dependentAssembly`|Инкапсулирует политику привязки и расположение каждой сборки. Для каждой `<dependentAssembly>` сборки используется один элемент.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Когда поставщик компонента выпускает новую версию сборки, поставщик может включить политику издателя, чтобы приложения, использующие старую версию, теперь использовали новую версию. Чтобы указать, следует ли применять политику издателя для конкретной сборки, вставьте  **\<элемент publisherpolicy Apply >** в  **\<элемент dependentAssembly >** .  
  
 Значение по умолчанию для атрибута **Apply** — **Да**. Присвоение атрибуту **Apply** значения **No** переопределяет любые предыдущие параметры **Yes** для сборки.  
  
 Для приложения требуется явное игнорирование политики издателя с помощью [ \<элемента publisherpolicy Apply Apply = "No"/>](publisherpolicy-element.md) в файле конфигурации приложения. Разрешение предоставляется путем установки <xref:System.Security.Permissions.SecurityPermissionFlag> флага <xref:System.Security.Permissions.SecurityPermission>для. Дополнительные сведения см. в статье [разрешение безопасности перенаправления привязки сборок](../../assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Пример  
 В следующем примере отключается политика издателя для сборки `myAssembly`.  
  
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

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Обнаружение сборок в среде выполнения](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Перенаправление версий сборки](../../redirect-assembly-versions.md)
