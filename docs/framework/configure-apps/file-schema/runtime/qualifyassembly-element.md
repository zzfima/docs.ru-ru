---
title: Элемент <qualifyAssembly>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a4741c6a4745bdba00fdb525b39b70d0b15e005
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109452"
---
# <a name="qualifyassembly-element"></a>\<qualifyAssembly > элемент
Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.  
  
 \<configuration>  
\<Среда выполнения >  
\<assemblyBinding >  
\<qualifyAssembly >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`partialName`|Обязательный атрибут.<br /><br /> Задает имя частичной сборки, как оно отображается в коде.|  
|`fullName`|Обязательный атрибут.<br /><br /> Указывает полное имя сборки, как оно отображается в глобальном кэше сборок.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Примечания  
 Вызов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> среда CLR для поиска сборки только в базовой папке приложения вызывает метод, с помощью частичных имен сборок. Используйте  **\<qualifyAssembly >** элемент в файле конфигурации приложения для предоставления полных сведений о сборке (имя, версию, токен открытого ключа и язык и региональные параметры) и привести к среда CLR для поиска для сборки в глобальный кэш сборок.  
  
 **FullName** атрибут должен содержать четыре поля удостоверение сборки: имя, версия, токен открытого ключа и языка и региональных параметров. **PartialName** атрибут частично необходимо сослаться на сборку. Необходимо указать по крайней мере текстовое имя сборки (наиболее распространенный случай), но можно также включить версия, токен открытого ключа, или язык и региональные параметры (или любое сочетание четырех, но не все четыре). **PartialName** должно соответствовать имени, указанному в вызове. Например, нельзя указать `"math"` как **partialName** атрибута в файл конфигурации и вызвать `Assembly.Load("math, Version=3.3.3.3")` в коде.  
  
## <a name="example"></a>Пример  
 В следующем примере производится логически вызов `Assembly.Load("math")` в `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Обнаружение сборок в среде выполнения](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Частичные ссылки на сборки](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
