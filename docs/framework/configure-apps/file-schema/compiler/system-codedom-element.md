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
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155392"
---
# <a name="systemcodedom-element"></a>\<system.codedom> Элемент
Задает параметры конфигурации компилятора для доступных поставщиков языков.  
  
[**\<конфигурация>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.codedom>**  
  
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
|[\<>составители](compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более [ \<элементов компил>ятора.](compiler-element.md)|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<конфигурация>](../configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="net-framework-version-20"></a>Рамочная версия .NET 2.0  
 Элемент [ \<system.codedom>](system-codedom-element.md) содержит настройки конфигурации компилятора для языковых провайдеров, установленных на компьютере <xref:Microsoft.CSharp.CSharpCodeProvider> в <xref:Microsoft.VisualBasic.VBCodeProvider>дополнение к поставщикам по умолчанию, которые установлены с помощью рамочной системы .NET, таких как и . [ \<Компиляторы>](compilers-element.md) элемента содержат ноль или более [ \<элементов компилятора>.](compiler-element.md) Каждый [ \<компилятор>](compiler-element.md) элемент определяет атрибуты конфигурации компилятора для определенного поставщика языков.  
  
 Разработчики и поставщики компилятов могут добавлять настройки конфигурации <xref:System.CodeDom.Compiler.CodeDomProvider> в файл конфигурации машины (Machine.config) для новой реализации. Используйте <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> метод для программного перечисления как поставщиков языков по умолчанию, так и поставщиков языков, определенных настройками конфигурации компилятора на компьютере.  
  
> [!NOTE]
> В версиях .NET Framework 1.0 и 1.1 поставщики языков по умолчанию, поставляемые рамочной системой .NET, идентифицируются в [ \<компиляторах>](compilers-element.md) элементе. В версии 2.0.NET Framework поставщики языков по умолчанию не идентифицируются в [ \<компиляторах>](compilers-element.md) элементом, но могут быть перечислены с помощью метода. <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A>  
  
## <a name="net-framework-versions-10-and-11"></a>Рамочные версии .NET 1.0 и 1.1  
 Элемент [ \<system.codedom>](system-codedom-element.md) содержит настройки конфигурации компилятора для языковых провайдеров на компьютере. [ \<Компиляторы>](compilers-element.md) элемента содержат ноль или более [ \<элементов компилятора>.](compiler-element.md) Каждый [ \<компилятор>](compiler-element.md) элемент определяет атрибуты конфигурации компилятора для определенного поставщика языков.  
  
 В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.  
  
## <a name="configuration-file"></a>Файл конфигурации  
 Этот элемент можно использовать в файле конфигурации машины и файле конфигурации приложения.  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует типичную конфигурацию компилятора.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Схема конфигурации файлов](../index.md)
- [Схема настройки компилятора и языкового провайдера](index.md)
- [\<компилятор> Элемент](compiler-element.md)
