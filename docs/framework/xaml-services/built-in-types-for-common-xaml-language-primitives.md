---
title: Встроенные типы для общих примитивов языка XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML language primitives [XAML Services]
- XAML [XAML Services], built-in types
- x:String [XAML Services]
- x:TimeSpan [XAML Services]
- x:Byte [XAML Services]
- x:Double [XAML Services]
- XAML [XAML Services], types
- x:Uri [XAML Services]
- XAML built-in types [XAML Services]
- x:Int64 [XAML Services]
- x:Single [XAML Services]
- x:Int32 [XAML Services]
ms.assetid: 11de2f08-5b95-4989-b5ec-5178eb968184
ms.openlocfilehash: c6af46fe2ea21d081e693ee83949651bd388a045
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837276"
---
# <a name="built-in-types-for-common-xaml-language-primitives"></a>Встроенные типы для общих примитивов языка XAML
В XAML 2009 появилась поддержка уровня языка XAML для некоторых типов данных, которые являются часто используемыми примитивами в среде CLR и в других языках программирования. В XAML 2009 добавлена поддержка следующих примитивов: `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`и `x:Array`  
  
<a name="previous_techniques_for_language_primitives_in_xaml_markup"></a>   
## <a name="previous-techniques-for-language-primitives-in-xaml-markup"></a>Предыдущие способы использования примитивов языка в разметке XAML  
 В XAML для предыдущих версий WPF можно было ссылаться на примитивы языка среды CLR путем сопоставления сборки и пространства имен, содержащего класс определения примитивов CLR для платформы .NET Framework. Большинство из них содержатся в сборке mscorlib и пространстве имен <xref:System> . Например, чтобы использовать <xref:System.Int32>, можно объявить следующее сопоставление (с показанным ниже примером использования):  
  
```xaml  
<Application xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"   
xmlns:sys="clr-namespace:System;assembly=mscorlib">  
  <Application.Resources>  
    <sys:Int32 x:Key="intMeaning">42</sys:Int32>  
  </Application.Resources>  
</Application>  
```  
  
<a name="xaml_2009_language_primitives"></a>   
## <a name="xaml-2009-language-primitives"></a>Примитивы языка XAML 2009  
 По соглашению примитивы языка XAML и все остальные элементы языка XAML отображаются с префиксом `x:` . Таким образом, элементы языка XAML обычно используются в реальной разметке. Это соглашение соблюдается в основной документации по XAML в WPF, а также в спецификации XAML.  
  
### <a name="xobject"></a>x:Object  
 Для резервирования CLR примитив `x:Object` соответствует <xref:System.Object>.  
  
 Этот примитив обычно не используется в разметке приложения, но может быть полезен в некоторых сценариях, таких как проверка возможности назначения в системе типов XAML.  
  
### <a name="xboolean"></a>x:Boolean  
 Для резервирования CLR примитив `x:Boolean` соответствует <xref:System.Boolean>.  
  
 XAML анализирует значения `x:Boolean` без учета регистра. Обратите внимание, что `x:Bool` не является допустимой альтернативой. Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.17 and 5.4.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xchar"></a>x:Char  
 Для резервирования CLR примитив `x:Char` соответствует <xref:System.Char>.  
  
 Строковые и символьные типы взаимодействуют со всей кодировкой файла на уровне XML. Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.7 and 5.4.1](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xstring"></a>x:String  
 Для резервирования CLR примитив `x:String` соответствует <xref:System.String>.  
  
 Строковые и символьные типы взаимодействуют со всей кодировкой файла на уровне XML. Определение спецификации языка XAML см. в разделе [\[MS-XAML\] Sections 5.2.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xdecimal"></a>x:Decimal  
 Для резервирования CLR примитив `x:Decimal` соответствует <xref:System.Decimal>.  
  
 Обратите внимание, что анализ XAML по существу выполняется в рамках языка и региональных параметров `en-US` . В рамках языка и региональных параметров `en-US` правильным разделителем компонентов десятичного числа всегда является точка (`.`), независимо от региональных параметров среды разработки или конечного клиентского компьютера, на котором во время выполнения загружается XAML.  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.14 and 5.4.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xsingle"></a>x:Single  
 Для резервирования CLR примитив `x:Single` соответствует <xref:System.Single>.  
  
 Помимо числовых значений текстовый синтаксис для `x:Single` также позволяет использовать токены `Infinity`, `-Infinity`и `NaN`. Эти токены обрабатываются с учетом регистра.  
  
 `x:Single` может поддерживать значения в экспоненциальном представлении, если первый символ в текстовом синтаксисе `e` или `E`.  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.8 and 5.4.2](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xdouble"></a>x:Double  
 Для резервирования CLR примитив `x:Double` соответствует <xref:System.Double>.  
  
 Помимо числовых значений текстовый синтаксис для `x:Double` позволяет использовать токены `Infinity`, `-Infinity`и `NaN`. Эти токены обрабатываются с учетом регистра.  
  
 `x:Double` может поддерживать значения в экспоненциальном представлении. Чтобы представить часть экспоненты, используйте символ `e` или `E` .  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.9 and 5.4.3](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xint16"></a>x:Int16  
 Для резервирования CLR примитив `x:Int16` , соответствующий <xref:System.Int16> и `x:Int16` , обрабатывается как имеющий знак. В XAML отсутствие знака плюс (`+`) в текстовом синтаксисе означает положительное значение.  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.11 and 5.4.5](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xint32"></a>x:Int32  
 Для резервирования CLR примитив `x:Int32` соответствует <xref:System.Int32>. `x:Int32` рассматривается как имеющий знак. В XAML отсутствие знака плюс (`+`) в текстовом синтаксисе означает положительное значение.  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.12 and 5.4.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xint64"></a>x:Int64  
 Для резервирования CLR примитив `x:Int64` соответствует <xref:System.Int64>. `x:Int64` рассматривается как имеющий знак. В XAML отсутствие знака плюс (`+`) в текстовом синтаксисе означает положительное значение.  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.13 and 5.4.7](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xtimespan"></a>x:TimeSpan  
 Для резервирования CLR примитив `x:TimeSpan` соответствует <xref:System.TimeSpan>.  
  
 Обратите внимание, что анализ XAML для формата даты-времени по существу выполняется в рамках языка и региональных параметров `en-US` .  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.16 and 5.4.10](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xuri"></a>x:Uri  
 Для резервирования CLR примитив `x:Uri` соответствует <xref:System.Uri>.  
  
 Проверка протоколов не является частью определения XAML для `x:Uri`.  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.15 and 5.4.9](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xbyte"></a>x:Byte  
 Для резервирования CLR примитив `x:Byte` соответствует <xref:System.Byte>. <xref:System.Byte> / `x:Byte` считается неподписанным.  
  
 Определение спецификации языка XAML см. в [разделах\[MS-XAML\] Sections 5.2.10 and 5.4.4](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
### <a name="xarray"></a>x:Array  
 Для резервирования CLR примитив `x:Array` соответствует <xref:System.Array>.  
  
 Можно определить массив в XAML 2006 г. с помощью синтаксиса расширения разметки; однако синтаксис XAML 2009 является определенным языком примитивом, которому не требуется доступ к расширению разметки. Дополнительные сведения о поддержке XAML 2006 см. в разделе [x:Array Markup Extension](x-array-markup-extension.md).  
  
 Определение спецификации языка XAML см. в разделе [\[MS-XAML\] Sections 5.2.18](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).  
  
<a name="wpf_support"></a>   
## <a name="wpf-support"></a>Поддержка WPF  
 В WPF можно использовать возможности XAML 2009, но только для XAML, не скомпилированного с разметкой. Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.  
  
 Сценарий, где можно использовать возможности XAML 2009 вместе с WPF, если разработчик выпустил свободный XAML, а вы затем загрузили этот XAML в среду выполнения WPF и граф объектов с <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>. <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> WPF и его <xref:System.Windows.Markup.XamlReader.Load%2A> может обрабатывать ключевые слова языка XAML 2009 и компоненты в правильное представление графа объектов.
