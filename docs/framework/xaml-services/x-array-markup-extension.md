---
title: "x:Array Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:Array"
  - "xArray"
helpviewer_keywords: 
  - "x:Array [XAML Services]"
  - "XAML [XAML Services], x:Array markup extension"
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Array Markup Extension
Предоставляет общую поддержку для массивов объектов в XAML посредством расширения разметки.  Это соответствует типу XAML `x:ArrayExtension` в \[MS\-XAML\].  
  
## Использование элемента объекта XAML  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`typeName`|Имя типа, который будет содержать `x:Array`.  `typeName` может быть \(и часто является\) префиксом пространства имен XAML, содержащего определения типов XAML.|  
|`arrayContents`|Содержимое элемента, присвоенное внутреннему свойству `ArrayExtension.Items`.  Как правило эти элементы задаются в виде одного или нескольких элементов объектов, содержащихся в открывающих и закрывающих тегах `x:Array`.  Объекты, указанные здесь, должно быть можно назначить тип XAML, заданный в `typeName`.|  
  
## Заметки  
 `Type` является обязательным атрибутом для всех объектных элементов `x:Array`.  Значение параметра `Type` не обязательно должно использовать расширение разметки `x:Type`; короткое имя типа — это тип XAML, который может быть указан в виде строки.  
  
 В реализации служб XAML .NET Framework на связь между типом входных данных XAML и типом выходных данных <xref:System.Type> среды CLR для созданного массива влияет контекст службы расширений разметки.  Тип <xref:System.Type> выходных данных определяется свойством <xref:System.Xaml.XamlType.UnderlyingType%2A> типа входных данных XAML, после поиска необходимого <xref:System.Xaml.XamlType> на основе контекста схемы XAML и службы <xref:System.Windows.Markup.IXamlTypeResolver>, предоставляемых контекстом.  
  
 При обработке содержимое массива присваивается встроенному свойству `ArrayExtension.Items`.  В реализации <xref:System.Windows.Markup.ArrayExtension> это представляется свойством <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=fullName>.  
  
 В реализации служб XAML .NET Framework обработка этого расширения разметки определяется классом <xref:System.Windows.Markup.ArrayExtension>.  Класс <xref:System.Windows.Markup.ArrayExtension> не запечатан и может использоваться в качестве основы для реализации расширения разметки для пользовательского типа массива.  
  
 `x:Array` предназначен скорее для общего расширения языка в XAML.  Однако `x:Array` может быть также полезен для задания значений XAML некоторых свойств, которые принимают поддерживаемые XAML коллекции в качестве их структурированного содержимого свойств.  Например, можно задать содержимое свойства <xref:System.Collections.IEnumerable> с использованием `x:Array`.  
  
 `x:Array` является расширением разметки.  Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами.  `x:Array` частично является исключением из этого правила, поскольку вместо предоставления альтернативной обработки значения атрибута `x:Array` обеспечивает альтернативную обработку внутреннего текстового содержимого.  Это поведение позволяет типам, которые, возможно, не поддерживаются существующей моделью содержимого, группироваться в массив и служить впоследствии объектом ссылок в файлах кода программной части посредством доступа к именованному массиву; можно вызвать методы <xref:System.Array>, чтобы получить отдельные элементы массива.  
  
 Все расширения разметки в XAML используют фигурные скобки \({,}`)` в синтаксисе их атрибутов, который является соглашением, по которому процессор XAML распознает, что расширение разметки должно обработать значение атрибута.  Дополнительные сведения о расширениях разметки в целом см. в разделе [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 В XAML 2009 `x:Array` определен как примитив языка, а не как расширение разметки.  Дополнительные сведения см. в разделе [Built\-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).  
  
## Примечания об использовании WPF  
 Как правило, объектные элементы, заполняющие `x:Array`, не являются элементами, существующими в пространстве имен XAML [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], и для них требуется сопоставление с пространством имен XAML, не являющимся пространством имен по умолчанию.  
  
 Например, ниже приведен простой массив из двух строк с префиксом `sys` \(а также `x`\), определенным на уровне массива.  
  
 \[xaml\]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Для настраиваемых типов, используемых в качестве элементов массива, класс также должен поддерживать требования для элементов, созданных в XAML как объектные элементы.  Дополнительные сведения см. в разделе [Код XAML и пользовательские классы для WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## См. также  
 [Расширения разметки и XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)