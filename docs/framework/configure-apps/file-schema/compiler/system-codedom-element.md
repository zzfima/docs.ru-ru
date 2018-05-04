---
title: '&lt;System.CodeDom&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 5939fa31a2f87348922d4586e3e7b7b52066fb09
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemcodedomgt-element"></a>&lt;System.CodeDom&gt; элемент
Задает параметры конфигурации компилятора для доступных поставщиков языков.  
  
 \<Конфигурация > элемент  
\<System.CodeDom > элемент  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль элементов [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) или несколько.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<configuration>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="net-framework-version-20"></a>Платформа .NET framework версии 2.0  
 [ \<System.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) элемент содержит параметры конфигурации компилятора для поставщиков языков, установленных на компьютере помимо поставщиков по умолчанию, которые устанавливаются вместе с .NET Framework, такие как <xref:Microsoft.CSharp.CSharpCodeProvider> и <xref:Microsoft.VisualBasic.VBCodeProvider>. [ \<Компиляторы >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) элемент содержит ноль или более [ \<компилятора >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) элементов. Каждый [ \<компилятора >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 Разработчики и компилятора можно добавить параметры конфигурации в файле конфигурации компьютера (Machine.config) нового <xref:System.CodeDom.Compiler.CodeDomProvider> реализации. Используйте <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> метод программное перечисление поставщиков языков по умолчанию и определяется на компьютере, параметры конфигурации компилятора поставщиков языков.  
  
> [!NOTE]
>  В .NET Framework версий 1.0 и 1.1, язык по умолчанию, поставщиков, предоставляемых платформой .NET Framework, определяются в [ \<компиляторы >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) элемента. Поставщики языков по умолчанию не определены в .NET Framework версии 2.0 в [ \<компиляторы >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) элемент, но могут быть перечислены с помощью <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> метод.  
  
## <a name="net-framework-versions-10-and-11"></a>Версии платформы .NET framework 1.0 и 1.1  
 [ \<System.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) элемент содержит параметры конфигурации компилятора для поставщиков языков на компьютере. [ \<Компиляторы >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) элемент содержит ноль или более [ \<компилятора >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) элементов. Каждый [ \<компилятора >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.  
  
 В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент может использоваться в файле конфигурации компьютера и файл конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показано типичная конфигурация компилятора.  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
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
