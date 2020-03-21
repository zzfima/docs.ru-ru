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
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153923"
---
# <a name="qualifyassembly-element"></a>\<квалификацияСборка> Элемент
Задает полное имя сборки, которая должна загружаться динамически в случае использования неполного имени.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<сборкаОбязательная>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<квалификацияСобрание>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`partialName`|Обязательный атрибут.<br /><br /> Определяет частичное название сборки по мере ее отослания в коде.|  
|`fullName`|Обязательный атрибут.<br /><br /> Упоняет полное название сборки, как она появляется в глобальном кэше сборки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`assemblyBinding`|Содержит сведения о перенаправлении версии сборки и о расположениях сборок.|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## <a name="remarks"></a>Remarks  
 Вызов <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> метода с использованием названий частичной сборки приводит к тому, что время выполнения общего языка будет искать сборку только в базовом каталоге приложения. Используйте ** \<элемент квалификационной сборки>** в файле конфигурации приложения, чтобы предоставить полную информацию о сборке (имя, версия, маркер общедоступного ключа и культуру) и вызвать время выполнения общего языка для поиска сборки в глобальном кэше сборки.  
  
 Атрибут **fullName** должен включать четыре поля идентификатора сборки: имя, версия, маркер общедоступных ключей и культуру. Атрибут **частичного имени** должен частично ссылаться на сборку. Необходимо указать хотя бы имя текста сборки (наиболее распространенный случай), но вы также можете включить версию, маркер общедоступного ключа или культуру (или любую комбинацию из четырех, но не все четыре). **PartialName** должен соответствовать имени, указанному в вашем вызове. Например, нельзя `"math"` указать атрибут **частичного имени** `Assembly.Load("math, Version=3.3.3.3")` в файле конфигурации и вызов в коде.  
  
## <a name="example"></a>Пример  
 Следующий пример логически превращает `Assembly.Load("math")` `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`вызов в .  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Как Время выполнения находит сборки](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Частичные ссылки на сборки](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))
