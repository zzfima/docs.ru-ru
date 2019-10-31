---
title: Элемент <assemblyBinding> для <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: c688353583f5e452950d63b7d02c48505b6ae999
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118134"
---
# <a name="assemblybinding-element-for-runtime"></a>\<элемент > assemblyBinding для среды выполнения \<
Содержит сведения о перенаправлении версии сборки и о расположениях сборок.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<assemblyBinding >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**xmlns**|Обязательный атрибут.<br /><br /> Задает пространство имен XML, необходимое для привязки сборок. Используйте строку urn:schemas-microsoft-com:asm.v1 в качестве значения.|  
|**appliesTo**|Задает версию среды выполнения, к которой применяется перенаправление сборки .NET Framework. Этот необязательный атрибут содержит номер версии .NET Framework, к которой применяется перенаправление. Если атрибут **appliesTo** не указан, элемент **\<assemblyBinding>** применяется ко всем версиям платформы .NET Framework. Атрибут **appliesTo** появился в .NET Framework версии 1,1; он игнорируется .NET Framework версии 1,0. Это означает, что при использовании платформы .NET Framework версии 1.0 применяются все элементы **\<assemblyBinding>** , даже если атрибут **appliesTo** задан.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|Инкапсулирует политику привязки и расположение сборки. Используйте один **\<dependentAssembly >** тега для каждой сборки.|  
|[\<probing>](probing-element.md)|Задает вложенные папки, в которых среда CLR выполняет поиск при загрузке сборки.|  
|[\<publisherPolicy>](publisherpolicy-element.md)|Указывает, применяет ли среда выполнения политику издателя.|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="example"></a>Пример  
 В следующем примере показан способ перенаправления одной версии сборки на другую и предоставлена база кода.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 В следующем примере показано, как использовать атрибут **appliesTo** для перенаправления привязки .NET Framework сборки.  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)
- [Перенаправление версий сборки](../../redirect-assembly-versions.md)
