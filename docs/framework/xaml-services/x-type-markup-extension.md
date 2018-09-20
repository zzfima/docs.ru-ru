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
ms.openlocfilehash: e4d56c5b5deda0bd1df8827020e0b76cc6276c1c
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46471240"
---
# <a name="xtype-markup-extension"></a>Расширение разметки x:Type
Среда CLR предоставляет <xref:System.Type> объект, который является базовым типом для указанного типа XAML.  
  
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
|`prefix`|Необязательный. Префикс, который сопоставляет пространство имен XAML не по умолчанию. Указание префикса часто не является обязательным. См. заметки.|  
|`typeNameValue`|Обязательно. Имя типа, которое разрешается до текущего пространства имен XAML по умолчанию; или указанного сопоставленного префикса, если `prefix` предоставляется.|  
  
## <a name="remarks"></a>Примечания  
 `x:Type` Расширение разметки имеет ту же функцию `typeof()` оператор в C# или `GetType` оператор в Microsoft Visual Basic.  
  
 `x:Type` Расширение разметки предоставляет поведение преобразования из строки для свойства, принимающие тип <xref:System.Type>. Входные данные — это тип XAML. Связь между тип входных данных XAML и выходных данных среды CLR <xref:System.Type> том, что выходные данные <xref:System.Type> — <xref:System.Xaml.XamlType.UnderlyingType%2A> входного <xref:System.Xaml.XamlType>, после поиска необходимого <xref:System.Xaml.XamlType> на основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver>предоставляет контекст службы.  
  
 В службах XAML .NET Framework, обработка данного расширения разметки определяется <xref:System.Windows.Markup.TypeExtension> класса.  
  
 В реализациях конкретной платформы, некоторые свойства, которые принимают <xref:System.Type> как значение может принимать имя типа напрямую (строковое значение типа `Name`). Тем не менее при реализации этого поведения является сложным сценарием. Примеры см. в следующем разделе «Примечания об использовании WPF».  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `x:Type`, присваивается в качестве значения <xref:System.Windows.Markup.TypeExtension.TypeName%2A> соответствующего класса расширения <xref:System.Windows.Markup.TypeExtension>. В разделе контекста схемы XAML по умолчанию для служб XAML .NET Framework, основанная на типах CLR, значение этого атрибута является <xref:System.Reflection.MemberInfo.Name%2A> требуемого типа, или содержит, <xref:System.Reflection.MemberInfo.Name%2A> предшествует префикс для пространства имен XAML не по умолчанию сопоставление.  
  
 `x:Type` Расширение разметки может использоваться в синтаксисе элемента объекта. В этом случае укажите значение параметра <xref:System.Windows.Markup.TypeExtension.TypeName%2A> свойство необходимо для правильной инициализации расширения.  
  
 `x:Type` Расширения разметки также может использоваться как атрибут verbose; Однако такое использование не является типичным: `<object property="{x:Type TypeName=typeNameValue}" .../>`  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Пространство имен XAML и сопоставление типов по умолчанию  
 Пространство имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, что нужно для типичных сценариев XAML; Таким образом вы можете избежать префиксы, ссылаясь на значения типа XAML. Может потребоваться сопоставить префикс в том случае, если ссылка на тип из пользовательской сборки, а также для типов, которые существуют в сборке WPF, но из пространства имен CLR, который не был сопоставлен с пространством имен XAML по умолчанию. Дополнительные сведения о префиксы пространств имен XAML и сопоставление пространств имен CLR, см. в разделе [пространства имен XAML и сопоставление пространств имен для WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Введите свойства этой поддержки Typename-as-String  
 WPF поддерживает методы, позволяющие указывать значения некоторых свойств типа <xref:System.Type> без необходимости `x:Type` использование расширения разметки. Вместо этого можно указать значение как строка с именем типа. Примером <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> и <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Такое поведение не поддерживается через преобразователи типов или расширения разметки. Вместо этого, это поведение отсрочки реализуется через <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight поддерживает действует похожее соглашение. На самом деле, Silverlight не поддерживает `{x:Type}` поддержка языка XAML и не принимает `{x:Type}` данные об использовании за пределами в некоторых случаях, которые предназначены для поддержки миграции XAML WPF Silverlight. Таким образом, поведение typename as string встроено в все оценки встроенного свойства Silverlight где <xref:System.Type> -значение.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 обеспечивает дополнительную поддержку для универсальных типов и изменяет поведение функции `x:TypeArguments` и `x:Type` предоставить эту поддержку.  
  
-   `x:TypeArguments` и элемент связанного объекта для создания экземпляра универсального объекта могут быть в элементах, отличном от корневого. Дополнительные сведения см. в разделе «XAML 2009» в статье [x: TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 поддерживает синтаксис для указания ограничения универсального типа в разметке. Это может использоваться `x:TypeArguments`, по `x:Type`, или в сочетании двух функций.  
  
-   Реализации WPF XAML при обработке XAML 2009 г. для загрузки также добавляет эту возможность для неявного преобразования типов для определенных свойств платформы, использующие тип <xref:System.Type>.  
  
 В WPF можно использовать возможности XAML 2009, но только для свободного XAML (XAML, который не является компилированной разметкой). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Style>  
 [Стилизация и использование шаблонов](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Общие сведения о языке XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Расширения разметки и XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
