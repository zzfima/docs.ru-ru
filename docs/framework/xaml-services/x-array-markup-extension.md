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
ms.openlocfilehash: 7c728b63c16d8f24c4ad68d07e6d174f510204ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565017"
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
|`typeName`|Имя типа, ваш `x:Array` будет содержать. `typeName` может быть (и часто является) для XAML в качестве префикса пространства имен, содержащего XAML определения типов.|  
|`arrayContents`|Элементы содержимого, назначенного к встроенным `ArrayExtension.Items` свойство. Как правило, эти элементы задаются в виде одного или нескольких элементов объектов, содержащихся в `x:Array` открывающих и закрывающих тегов. Объекты, указанные здесь должно быть можно назначить тип XAML, заданный в `typeName`.|  
  
## <a name="remarks"></a>Примечания  
 `Type` является обязательным атрибутом для всех `x:Array` элементов объекта. A `Type` значение параметра не требуется использовать `x:Type` расширение разметки, короткое имя типа является тип XAML, который может быть указан как строка.  
  
 В реализации служб XAML .NET Framework, отображается связь между тип входных данных XAML и вывод CLR <xref:System.Type> созданного массива зависит от контекста службы для расширения разметки. Выходные данные <xref:System.Type> — <xref:System.Xaml.XamlType.UnderlyingType%2A> из типа входных данных XAML после поиска необходимого <xref:System.Xaml.XamlType> на основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver> предоставляет контекст службы.  
  
 При обработке содержимого массива назначаются `ArrayExtension.Items` внутреннее свойство. В <xref:System.Windows.Markup.ArrayExtension> реализацию, он представлен <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.  
  
 В реализации служб XAML .NET Framework определяется обработка для данного расширения разметки <xref:System.Windows.Markup.ArrayExtension> класса. <xref:System.Windows.Markup.ArrayExtension> не запечатан и может использоваться в качестве основы для реализации расширения разметки для пользовательского типа массива.  
  
 `x:Array` — более предназначен общего расширения языка в XAML. Но `x:Array` также можно использовать для задания значений XAML некоторых свойств, которые принимают поддерживаемые XAML коллекции в качестве их структурированного содержимого свойств. Например, можно указать содержимое <xref:System.Collections.IEnumerable> свойство с `x:Array` использования.  
  
 `x:Array` является расширением разметки. Расширения разметки обычно реализуются, если требуется заменить значения атрибутов на нелитеральные значения или имена обработчиков и если требуется больше, чем простая настройка преобразователей типов на работу с определенными типами или свойствами. `x:Array` частично является исключением из этого правила, так как вместо предоставления альтернативной обработки значения атрибута, `x:Array` обеспечивает альтернативную обработку его внутреннего текстового содержимого. Данное поведение позволяет типов, которые могут не поддерживаться сгруппированы в массив и ссылается позже в коде программной именованный массив; доступ к существующей модели содержимого можно вызвать <xref:System.Array> методы для получения отдельных элементов массива.  
  
 Все расширения разметки в XAML используйте фигурные скобки ({,} `)` в синтаксисе их атрибутов, который является соглашением, по которому обработчик XAML узнает, что расширение разметки должно обработать значение атрибута. Дополнительные сведения о расширениях разметки в целом см. в разделе [преобразователи типов или расширения разметки для XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).  
  
 В XAML 2009 `x:Array` определен как примитив вместо расширения разметки языка. Дополнительные сведения см. в разделе [встроенные типы общих примитивов языка XAML](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Как правило, объектные элементы, заполняющие `x:Array` не являются элементами, которые существуют в [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] пространства имен XAML и необходимо выполнить сопоставление префикса пространства имен XAML не по умолчанию.  
  
 Например, ниже приведен простой массив двух строк с `sys` префикс (а также `x`) определенным на уровне массива.  
  
 [xaml]  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 Для пользовательских типов, которые используются в качестве элементов массива класс должен также поддерживать требования, к которому они создаются в XAML в качестве элементов объекта. Дополнительные сведения см. в разделе [XAML и пользовательские классы для WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).  
  
## <a name="see-also"></a>См. также  
 [Расширения разметки и XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [Типы, перенесенные из WPF в System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
