---
title: -langversion (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 523636663744acbbc85a08ebe3535f066e7dc160
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
|default|Компилятор допускает использование любого допустимого синтаксиса языка из последней основной версии, которую он поддерживает. <sup id="TDefault">[По умолчанию](#FDefault)</sup>| 
|ISO-1|Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup>|  
|ISO-2|Компилятор принимает только синтаксис, включенный в спецификацию ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup>|
|3|Компилятор принимает только синтаксис, включенный в спецификацию C# 3.0 или более раннюю <sup id="TCS3">[CS3](#FCS3)</sup>|
|4|Компилятор принимает только синтаксис, включенный в спецификацию C# 4.0 или более раннюю <sup id="TCS4">[CS4](#FCS4)</sup>|
|5|Компилятор принимает только синтаксис, включенный в спецификацию C# 5.0 или более раннюю <sup id="TCS5">[CS5](#FCS5)</sup>|
|6|Компилятор принимает только синтаксис, включенный в спецификацию C# 6.0 или более раннюю <sup id="TCS6">[CS6](#FCS6)</sup>|
|7|Компилятор принимает только синтаксис, включенный в спецификацию C# 7.0 или более раннюю <sup id="TCS7">[CS7](#FCS7)</sup>|
|latest|Компилятор допускает использование любого допустимого синтаксиса языка, который он может поддерживать. <sup id="TLatest">[Последняя версия](#FLatest)</sup>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a>Примечания  
 Параметр компилятора **-langversion** не влияет на метаданные, на которые ссылается ваше приложение C#.  
  
 Так как каждая версия компилятора C# содержит расширения для спецификации языка, параметр **-langversion** не позволяет получить функциональные возможности, аналогичные более ранней версии компилятора.  
 
 Кроме того, в отличие от обновлений версии C#, которые обычно совпадают с основными выпусками платформы .Net Framework, новые функции и возможности синтаксиса могут быть не привязаны к конкретной версии этой платформы. Для работы с новыми версиями требуется обновление компилятора, которое также выпускается с новой редакцией C#. Тем не менее для каждой функции определен собственный набор минимальных требований к API .Net или общеязыковой среде выполнения, в результате чего их можно выполнять на более ранних версиях платформы, добавив необходимые пакеты NuGet или другие библиотеки.
  
 Независимо от того, какой параметр **-langversion** вы задали, для создания файлов с расширением EXE или DLL будет использоваться текущая версия общеязыковой среды выполнения. Единственным исключением являются дружественные сборки и [-moduleassemblyname (параметр компилятора C#)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), которые работают при установке параметра **-langversion:ISO-1**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Щелкните страницу свойств **Сборка**.  
  
3.  Нажмите кнопку **Дополнительно** .  
  
4.  Измените значение свойства **Версия языка**.  
  
 Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
    
## <a name="see-also"></a>См. также  
 [Параметры компилятора C# ](../../../csharp/language-reference/compiler-options/index.md)  
 [Управление свойствами проектов и решений](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a>Спецификация языка C#
 [Справочник по спецификации языка C#](../../../csharp/language-reference/language-specification/index.md): .NET Foundation  
 Информационные технологии C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) — спецификация языка C#: каталог ISO  
 Информационные технологии C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) — спецификация языка C#: каталог ISO  
 C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 в формате PDF: общедоступные стандарты ISO  
 C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) — спецификация языка C# версии 3.0: корпорация Майкрософт  
 C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) — стандарт ECMA-334, 4-й выпуск    
 C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) — спецификация языка C# версии 5.0: корпорация Майкрософт  
 C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) спецификация языка C# версии 6 (неофициальный проект): .NET Foundation  
 C# 7.0 (в настоящее время недоступно)  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a>Минимальная версия компилятора, необходимая для поддержки всех возможностей языка   
[↩](#TDefault)<a name="FDefault">По умолчанию</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 или встроенный компилятор .Net Framework 1.0     
[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 или встроенный компилятор .Net Framework 2.0    
[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 или встроенный компилятор .Net Framework 3.5    
[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 или встроенный компилятор .Net Framework 4.0    
[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 или встроенный компилятор .Net Framework 4.5    
[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015    
[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">последняя версия</a>: Microsoft Visual Studio/Build Tools 2017   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
