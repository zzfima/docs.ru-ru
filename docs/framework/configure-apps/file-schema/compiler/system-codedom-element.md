---
title: Элемент <system.codedom>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 19f37095bd01b76fda8b1e29423c413dbdb06a65
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168919"
---
# <a name="systemcodedom-element"></a>\<Элемент System. CodeDom >
Задает параметры конфигурации компилятора для доступных поставщиков языков.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp; **\<> System. CodeDom**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<compilers>](compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль элементов [\<compiler>](compiler-element.md) или несколько.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Примечания  
  
## <a name="net-framework-version-20"></a>.NET Framework версии 2,0  
 <xref:Microsoft.CSharp.CSharpCodeProvider> [ ЭлементSystem.CodeDom>содержитпараметрыконфигурациикомпиляторадляпоставщиковязыков,установленныхнакомпьютеревдополнениекпоставщикампоумолчанию,которыеустанавливаютсявместе\<](system-codedom-element.md) с .NET Framework, например и <xref:Microsoft.VisualBasic.VBCodeProvider>. Компилятор > элемент содержит ноль или больше [ \<элементов > компилятора](compiler-element.md) . [ \<](compilers-element.md) Каждый элемент > компилятора задает атрибуты конфигурации компилятора для конкретного поставщика языка. [ \<](compiler-element.md)  
  
 Разработчики и поставщики компиляторов могут добавлять параметры конфигурации в файл конфигурации компьютера (Machine. config) для новой <xref:System.CodeDom.Compiler.CodeDomProvider> реализации. <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> Используйте метод для программного перечисления поставщиков языка по умолчанию и поставщиков языков, определенных параметрами конфигурации компилятора на компьютере.  
  
> [!NOTE]
> В .NET Framework версиях 1,0 и 1,1 поставщики языка по умолчанию, предоставляемые .NET Framework, определяются в [ \<элементе компиляторы >](compilers-element.md) . В .NET Framework версии 2,0 поставщики языка по умолчанию не определяются в [ \<>ном](compilers-element.md) элементе компиляторов, но их можно <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> перечислить с помощью метода.  
  
## <a name="net-framework-versions-10-and-11"></a>.NET Framework версии 1,0 и 1,1  
 Элемент [System. CodeDom > содержит параметры конфигурации компилятора для поставщиков языков на компьютере. \<](system-codedom-element.md) Компилятор > элемент содержит ноль или больше [ \<элементов > компилятора](compiler-element.md) . [ \<](compilers-element.md) Каждый элемент > компилятора задает атрибуты конфигурации компилятора для конкретного поставщика языка. [ \<](compiler-element.md)  
  
 В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 В следующем примере показана типичная конфигурация компилятора.  
  
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

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Схема файла конфигурации](../index.md)
- [Схема параметров компилятора и поставщика языков](index.md)
- [Элемент \<compiler>](compiler-element.md)
