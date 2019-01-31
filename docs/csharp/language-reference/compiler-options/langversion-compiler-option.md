---
title: -langversion (параметры компилятора C#)
ms.date: 05/14/2018
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: ee23c962d8ea9adecabc5146af75419c87fcc75a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516802"
---
# <a name="-langversion-c-compiler-options"></a>-langversion (параметры компилятора C#)

Инструктирует компилятор принимать только синтаксис, включенный в заданную спецификацию языка C#.  
  
## <a name="syntax"></a>Синтаксис  

```console
-langversion:option  
```

## <a name="arguments"></a>Аргументы

 `option`  
 Допустимы следующие значения.  
  
|Параметр|Значение|  
|------------|-------------|  
|default|Компилятор допускает использование любого допустимого синтаксиса языка из последней основной версии, которую он поддерживает.|
|ISO-1|Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2003 C# (1.0/1.2) <sup id="TISO1">[ISO1](#FISO1)</sup>|  
|ISO-2|Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup>|
|3|Компилятор принимает только синтаксис, включенный в спецификацию C# 3.0 или более раннюю <sup id="TCS3">[CS3](#FCS3)</sup>|
|4|Компилятор принимает только синтаксис, включенный в спецификацию C# 4.0 или более раннюю <sup id="TCS4">[CS4](#FCS4)</sup>|
|5|Компилятор принимает только синтаксис, включенный в спецификацию C# 5.0 или более раннюю <sup id="TCS5">[CS5](#FCS5)</sup>|
|6|Компилятор принимает только синтаксис, включенный в спецификацию C# 6.0 или более раннюю <sup id="TCS6">[CS6](#FCS6)</sup>|
|7|Компилятор принимает только синтаксис, включенный в спецификацию C# 7.0 или более раннюю <sup id="TCS7">[CS7](#FCS7)</sup>|
|7.1|Компилятор принимает только синтаксис, включенный в спецификацию C# 7.1 или более раннюю <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|Компилятор принимает только синтаксис, включенный в спецификацию C# 7.2 или более раннюю <sup id="TCS72">[CS72](#FCS72)</sup>|
|7.3|Компилятор принимает только синтаксис, включенный в спецификацию C# 7.3 или более раннюю <sup id="TCS73">[CS73](#FCS73)</sup>|
|latest|Компилятор допускает использование любого допустимого синтаксиса языка, который он может поддерживать.|

<!--- Uncomment and move these above
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS8">[CS8](#FCS8)</sup>|
-->

## <a name="remarks"></a>Примечания

 Параметр компилятора **-langversion** не влияет на метаданные, на которые ссылается ваше приложение C#.  
  
 Так как каждая версия компилятора C# содержит расширения для спецификации языка, параметр **-langversion** не позволяет получить функциональные возможности, аналогичные более ранней версии компилятора.  

 Кроме того, в отличие от обновлений версии C#, которые обычно совпадают с основными выпусками платформы .NET Framework, новые функции и возможности синтаксиса могут быть не привязаны к конкретной версии этой платформы. Для работы с новыми версиями требуется обновление компилятора, которое также выпускается с новой редакцией C#. Тем не менее для каждой функции определен собственный набор минимальных требований к API .NET или общеязыковой среде выполнения, в результате чего их можно выполнять на более ранних версиях платформы, добавив необходимые пакеты NuGet или другие библиотеки.
  
 Независимо от того, какой параметр **-langversion** вы задали, для создания файлов с расширением EXE или DLL будет использоваться текущая версия общеязыковой среды выполнения. Единственным исключением являются дружественные сборки и [-moduleassemblyname (параметр компилятора C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), которые работают при установке параметра **-langversion:ISO-1**.  

 Другие способы указания версии языка C# см. в разделе [Выбор версии языка C#](../configure-language-version.md).
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  

## <a name="see-also"></a>См. также

- [Параметры компилятора C# ](index.md)
- [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)

### <a name="c-language-specification"></a>Спецификация языка C#

|Версия|Ссылка|Описание|
|-------|----|-----------|
|C# 1.0|[Загрузить DOC-файл](https://download.microsoft.com/download/a/9/e/a9e229b9-fee5-4c3e-8476-917dee385062/csharp%20language%20specification%20v1.0.doc)|Спецификация языка C#, версия 1.0: Microsoft Corporation|
|C# 1.2|[Загрузить DOC-файл](https://download.microsoft.com/download/5/e/5/5e58be0a-b02b-41ac-a4a3-7a22286214ff/csharp%20language%20specification%20v1.2.doc)|Спецификация языка C#, версия 1.2: Microsoft Corporation|
|C# 2.0|[Загрузить PDF-файл](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/Ecma-334%204th%20edition%20June%202006.pdf)|Стандарт ECMA-334, 4-й выпуск|
|C# 3.0|[Загрузить DOC-файл](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|Спецификация языка C#, версия 3.0: Microsoft Corporation|
|C# 5.0|[Загрузить PDF-файл](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf)|Стандарт ECMA-334, 5-й выпуск|
|C# 6.0|[Ссылка](../language-specification/index.md)|Спецификация языка C# версии 6 (неофициальный проект): .NET Foundation|
|C# 7.0 и более поздние версии||в настоящее время недоступно|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Минимальная версия компилятора, необходимая для поддержки всех возможностей языка

[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .NET 2002 или встроенный компилятор .NET Framework 1.0 [↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 или встроенный компилятор .Net Framework 2.0 [↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 или встроенный компилятор .Net Framework 3.5 [↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 или встроенный компилятор .Net Framework 4.0 [↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 или встроенный компилятор .Net Framework 4.5 [↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015 [↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017 [↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017, версия 15.3 [↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017, версия 15.5 [↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017, версия 15.7

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS8)<a name="FCS8">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
