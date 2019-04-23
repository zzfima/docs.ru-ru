---
title: Расширение разметки x:Array
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: 4f4e26eb3e5ccaf66b2173c7fc9952375c5f2a58
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139143"
---
# <a name="xarray-markup-extension"></a>Расширение разметки x:Array
Предоставляет общую поддержку для массивов объектов в XAML посредством расширения разметки. Это соответствует `x:ArrayExtension` тип XAML в [MS-XAML].  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`typeName`|Имя типа, ваш `x:Array` будет содержать. `typeName` может быть (и часто является) с префиксом для XAML определения типов пространство имен, содержащее XAML.|  
|`arrayContents`|Элементы содержимого, назначенного к встроенным `ArrayExtension.Items` свойство. Как правило, эти элементы задаются в виде одного или нескольких элементов объектов, содержащихся в `x:Array` открывающих и закрывающих тегов. Объекты, указанные здесь, должны содержать может быть назначен для типа XAML, указанного в `typeName`.|  
  
## <a name="remarks"></a>Примечания  
 `Type` атрибут является обязательным для всех `x:Array` объектных элемента. Объект `Type` значение параметра не требуется использовать `x:Type` расширение разметки; короткое имя типа является типом XAML, который может быть указан как строка.  
  
 В реализации служб XAML .NET Framework, отображается связь между тип входных данных XAML и выходных данных среды CLR <xref:System.Type> созданный массива зависит от контекста службы для расширения разметки. Выходные данные <xref:System.Type> — <xref:System.Xaml.XamlType.UnderlyingType%2A> входного типа XAML, после поиска необходимого <xref:System.Xaml.XamlType> на основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver> предоставляет контекст службы.  
  
 При обработке содержимое массива назначаются `ArrayExtension.Items` внутреннее свойство. В <xref:System.Windows.Markup.ArrayExtension> реализации, оно представлено <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.  
  
 В реализации служб XAML .NET Framework, обработка данного расширения разметки определяется <xref:System.Windows.Markup.ArrayExtension> класса. <xref:System.Windows.Markup.ArrayExtension> не запечатан и может использоваться в качестве основы для реализации расширения разметки для пользовательского типа массива.  
  
 `x:Array` — Это сведения предназначены для общих расширения языка в XAML. Но `x:Array` также можно использовать для указания XAML значений определенных свойств, которые принимают в качестве их структурированного содержимого свойств коллекций поддерживается в XAML. Например, можно указать содержимое <xref:System.Collections.IEnumerable> свойство с `x:Array` использования.  
  
 `x:Array` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. `x:Array` частично является исключением из этого правила, так как вместо предоставления альтернативной обработки значения атрибута, `x:Array` обеспечивает альтернативную обработку его внутреннего текстового содержимого. Такое поведение позволяет типов, которые могут не поддерживаться существующей модели содержимого сгруппированы в массив и ссылается позже в коде доступа к именованным массива. Вы можете вызвать <xref:System.Array> методы для получения отдельных элементов массива.  
  
 Все расширения разметки в XAML используйте фигурные скобки ({,} `)` в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать значение атрибута. Дополнительные сведения о расширениях разметки в целом см. в разделе [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions-for-xaml.md).  
  
 В XAML 2009 г. `x:Array` определяется как примитив вместо расширения разметки языка. Дополнительные сведения см. в разделе [встроенные типы для общих примитивов языка XAML](built-in-types-for-common-xaml-language-primitives.md).  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Как правило, объектные элементы, заполняющие `x:Array` , не являются элементами, которые существуют в [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] пространства имен XAML и необходимо выполнить сопоставление префикса пространства имен XAML не по умолчанию.  
  
 Например, ниже приведен простой массив из двух строк с `sys` префикс (и также `x`) определены на уровне массива.  
  
 [xaml]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Для пользовательских типов, которые используются в качестве элементов массива класс должен также поддерживать требования для создания экземпляров в XAML как элементы объекта. Дополнительные сведения см. в разделе [XAML и пользовательские классы для WPF](../wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## <a name="see-also"></a>См. также

- [Расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [Типы, перенесенные из WPF в System.Xaml](types-migrated-from-wpf-to-system-xaml.md)
