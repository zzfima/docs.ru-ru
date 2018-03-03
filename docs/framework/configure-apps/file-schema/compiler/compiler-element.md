---
title: "&lt;Компилятор&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 242a4780443026e751d76c7e80dd9a77cbbbddc7
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/02/2018
---
# <a name="ltcompilergt-element"></a>&lt;Компилятор&gt; элемент
Задает атрибуты конфигурации компилятора для поставщика языка.  
  
 \<Элемент конфигурации >  
\<system.codedom Element>  
\<компиляторы элемент >  
\<Компилятор > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`compilerOptions`|Необязательный атрибут.<br /><br /> Задает дополнительные аргументы компилятора для компиляции. Значения для `compilerOptions` атрибут обычно отображаются в разделе параметры компилятора для компилятора. В документации по Visual Studio 2005 параметры для компилятора можно найти путем поиска «параметры компилятора» в индексе.|  
|`extension`|Обязательный атрибут.<br /><br /> Предоставляет список разделенных точкой с запятой расширений имен файлов, используемых исходными файлами поставщика языка. Например «.cs».|  
|`language`|Обязательный атрибут.<br /><br /> Предоставляет список разделенных точкой с запятой имен языков, поддерживаемых поставщиком языка. Например «c#; cs; csharp».|  
|`type`|Обязательный атрибут.<br /><br /> Указывает имя типа поставщика языка, включая имя сборки, содержащей реализацию этого поставщика. Имена типов должны отвечать требованиям, определенным в [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|`warningLevel`|Необязательный атрибут.<br /><br /> Задает уровень предупреждений компилятора по умолчанию; Определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<providerOption > элемент](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|Задает атрибуты версии компилятора для поставщика языка.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[Элемент \<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|[\<system.codedom> Element](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|  
|[\<компиляторы > элемент](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более `<compiler>` элементов.|  
  
## <a name="remarks"></a>Примечания  
 Каждый `<compiler>` элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка. Расширяет поставщика <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> класса для конкретного языка; `<compiler>` элемент определяет компилятора и генератора кода для поставщика языка.  
  
 В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.  
  
 Элементы компилятора в приложение или файл веб-конфигурации можно дополнить или переопределить параметры в файле конфигурации компьютера. Если для одного имени языка или расширения файла настроено более одной реализации поставщика, последняя подходящая конфигурация переопределяет всех ранее настроенных поставщиков для этого языка имя или расширение.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться в файле конфигурации компьютера и файл конфигурации приложения.  
  
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
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<компиляторы > элемент](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [Указание полных имен типов](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [Компилятор элемент для компиляторов для компиляции (схема параметров ASP.NET)](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e(v=vs.100))
