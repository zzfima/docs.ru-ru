---
title: Расширение разметки x:Type
ms.date: 03/30/2017
f1_keywords:
- x:TypeExtension
- Type
- x:Type
- xType
- TypeExtension
helpviewer_keywords:
- x:Type markup extension [XAML Services]
- XAML [XAML Services], x:Type markup extension
- XAML [XAML Services], TargetType attribute
- TargetType attribute [XAML Services]
- Type markup extension in XAML [XAML Services]
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
ms.openlocfilehash: df0b3fe53cb8f284fc6e2d79a9b2cea86318d701
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459913"
---
# <a name="xtype-markup-extension"></a>Расширение разметки x:Type
Предоставляет <xref:System.Type> CLR-объект, который является базовым типом для указанного типа XAML.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```xaml  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`prefix`|Необязательный. Префикс, который сопоставляет пространство имен XAML, отличное от используемого по умолчанию. Указывать префикс часто необязательно. См. заметки.|  
|`typeNameValue`|Обязательный. Имя типа, которое разрешается в текущее пространство имен XAML по умолчанию; или указанный сопоставленный префикс, если указан `prefix`.|  
  
## <a name="remarks"></a>Заметки  
 Расширение разметки `x:Type` имеет аналогичную функцию оператора `typeof()` в C# или оператора `GetType` в Microsoft Visual Basic.  
  
 Расширение разметки `x:Type` предоставляет поведение преобразования из строки для свойств, которые принимают тип <xref:System.Type>. Входные данные являются типом XAML. Связь между входным типом XAML и выходными данными CLR <xref:System.Type> заключается в том, что выходным <xref:System.Type> является <xref:System.Xaml.XamlType.UnderlyingType%2A> входных <xref:System.Xaml.XamlType>, после поиска необходимой <xref:System.Xaml.XamlType> на основе контекста схемы XAML и службы <xref:System.Windows.Markup.IXamlTypeResolver>, предоставляемой контекстом.  
  
 В .NET Framework службах XAML обработка этого расширения разметки определяется классом <xref:System.Windows.Markup.TypeExtension>.  
  
 В определенных реализациях платформы некоторые свойства, принимающие <xref:System.Type> в качестве значения, могут напрямую принять имя типа (строковое значение типа `Name`). Однако реализация этого поведения является сложным сценарием. Примеры см. в разделе "Примечания об использовании WPF" ниже.  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `x:Type`, присваивается в качестве значения <xref:System.Windows.Markup.TypeExtension.TypeName%2A> соответствующего класса расширения <xref:System.Windows.Markup.TypeExtension>. В контексте схемы XAML по умолчанию для служб .NET Framework XAML, основанных на типах CLR, значением этого атрибута является либо <xref:System.Reflection.MemberInfo.Name%2A> требуемого типа, либо значение, <xref:System.Reflection.MemberInfo.Name%2A> перед префиксом для сопоставления пространства имен XAML не по умолчанию.  
  
 Расширение разметки `x:Type` можно использовать в синтаксисе объектного элемента. В этом случае для правильной инициализации расширения требуется указать значение свойства <xref:System.Windows.Markup.TypeExtension.TypeName%2A>.  
  
 Расширение разметки `x:Type` также можно использовать в качестве подробного атрибута. Однако это нетипичное использование: `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Сопоставление типов и пространства имен XAML по умолчанию  
 Пространство имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, необходимых для типичных сценариев XAML. Таким образом, часто можно избежать префиксов при ссылке на значения типа XAML. Может потребоваться сопоставить префикс, если вы ссылаетесь на тип из пользовательской сборки или для типов, существующих в сборке WPF, но из пространства имен CLR, которое не было сопоставлено с пространством имен XAML по умолчанию. Дополнительные сведения о префиксах, пространствах имен XAML и сопоставлении пространств имен CLR см. в разделе [пространства имен и сопоставление пространств имен XAML для WPF XAML](../wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Свойства типа, поддерживающие TypeName в виде строки  
 WPF поддерживает приемы, позволяющие указывать значения некоторых свойств типа <xref:System.Type> без необходимости использования расширения разметки `x:Type`. Вместо этого можно указать значение в виде строки с именем типа. Примерами этого являются <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> и <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Поддержка этого поведения не предоставляется ни с помощью преобразователей типов, ни из расширений разметки. Вместо этого это поведение, реализованное с помощью <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight поддерживает аналогичное соглашение. На самом деле, Silverlight в настоящее время не поддерживает `{x:Type}` в своей языковой поддержке XAML и не принимает `{x:Type}` использования за пределами нескольких обстоятельств, предназначенных для поддержки миграции XAML WPF-Silverlight. Таким образом, поведение типа "имя-строка" встроено во все вычисления собственного свойства Silverlight, где <xref:System.Type> является значением.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 обеспечивает дополнительную поддержку для универсальных типов и изменяет поведение функций `x:TypeArguments` и `x:Type` для предоставления этой поддержки.  
  
- `x:TypeArguments` и связанный объектный элемент для создания экземпляра универсального объекта может находиться в элементах, отличных от корневого. Дополнительные сведения см. в разделе "XAML 2009" [директивы x:TypeArguments](x-typearguments-directive.md).  
  
- XAML 2009 поддерживает синтаксис для указания ограничения универсального типа в разметке. Это может быть использовано `x:TypeArguments`, `x:Type`или двумя функциями в сочетании.  
  
- Реализация XAML в WPF при обработке XAML 2009 для загрузки также добавляет эту возможность в поведение неявного преобразования типов для определенных свойств инфраструктуры, использующих тип <xref:System.Type>.  
  
 В WPF можно использовать функции XAML 2009, но только для свободного XAML (XAML, не компилируемого разметкой). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Style>
- [Стилизация и использование шаблонов](../wpf/controls/styling-and-templating.md)
- [Общие сведения о языке XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
