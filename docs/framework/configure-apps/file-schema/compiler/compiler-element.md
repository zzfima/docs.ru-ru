---
title: Элемент <compiler>
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: 46676f25597f85596598d6f67c98930971cb0447
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088054"
---
# <a name="compiler-element"></a>\<>ного элемента компилятора

Задает атрибуты конфигурации компилятора для поставщика языка.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. codedom >** ](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<компилятора**](compilers-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**компилятора >**

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
|`compilerOptions`|Необязательный атрибут.<br /><br /> Задает дополнительные зависящие от компилятора аргументы для компиляции. Значения для атрибута `compilerOptions`, как правило, перечислены в разделе параметров компилятора для компилятора.|
|`extension`|Обязательный атрибут.<br /><br /> Предоставляет разделенный точками с запятой список расширений имен файлов, используемых исходными файлами для поставщика языка. Например, ". cs".|
|`language`|Обязательный атрибут.<br /><br /> Предоставляет разделенный точками с запятой список имен языков, поддерживаемых поставщиком языка. Например, "c#; CS; CSharp".|
|`type`|Обязательный атрибут.<br /><br /> Указывает имя типа поставщика языка, включая имя сборки, содержащей реализацию поставщика. Имя типа должно соответствовать требованиям, определенным при [указании полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).|
|`warningLevel`|Необязательный атрибут.<br /><br /> Задает уровень предупреждений компилятора по умолчанию. Определяет уровень, на котором поставщик языка рассматривает предупреждения компиляции как ошибки.|

### <a name="child-elements"></a>Дочерние элементы

|Элемент|Описание|
|-------------|-----------------|
|[\<Провидероптион > элемент](provideroption-element.md)|Указывает атрибуты версии компилятора для поставщика языка.|

### <a name="parent-elements"></a>Родительские элементы

|Элемент|Описание|
|-------------|-----------------|
|[Элемент \<configuration>](../configuration-element.md)|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|
|[\<System. CodeDom > элемент](system-codedom-element.md)|Задает параметры конфигурации компилятора для доступных поставщиков языков.|
|[\<компиляторы > элемент](compilers-element.md)|Контейнер для элементов конфигурации компилятора; содержит ноль или более элементов `<compiler>`.|

## <a name="remarks"></a>Заметки

Каждый элемент `<compiler>` задает атрибуты конфигурации компилятора для конкретного поставщика языка. Поставщик расширяет класс <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> для конкретного языка; элемент `<compiler>` определяет параметры компилятора и генератора кода для поставщика языка.

В .NET Framework начальные параметры компилятора определены файле конфигурации компьютера (Machine.config). Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider>. С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.

Элементы компилятора в файле приложения или веб-конфигурации могут дополнять или переопределять параметры в файле конфигурации компьютера. Если для одного и того же имени языка или одного расширения файла настроено несколько реализаций поставщика, последняя конфигурация сопоставления переопределяет все предыдущие настроенные поставщики для этого имени языка или расширения файла.

## <a name="configuration-file"></a>Файл конфигурации

Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.

## <a name="example"></a>Пример

В следующем примере показан типичный элемент конфигурации компилятора:

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

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [Схема файла конфигурации](../index.md)
- [\<компиляторы > элемент](compilers-element.md)
- [Указание полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- [Элемент компилятора для компиляторов для компиляции (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))
