---
title: '&lt;компиляторы&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8ce303d33a83d972247609e5d02d16a4a57669ff
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47083798"
---
# <a name="ltcompilersgt-element"></a>&lt;компиляторы&gt; элемент
Контейнер для элементов конфигурации компилятора; содержит ноль элементов [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) или несколько.  
  
 \<configuration>  
\<System.CodeDom >  
\<компиляторы > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|Задает атрибуты конфигурации компилятора для поставщика языка.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|[\<System.CodeDom > элемент](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
  
## <a name="remarks"></a>Примечания  
 [ \<Компиляторы >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) элемент содержит параметры конфигурации компилятора для поставщиков языков на компьютере. Каждый [ \<компилятора >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 .NET Framework определяет начальной компилятора и языковые параметры поставщика в файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться в файле конфигурации компьютера и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показан типичный элемент конфигурации компилятора.  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Схема параметров компилятора и поставщика языков](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [Элемент \<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
