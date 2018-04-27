---
title: Расширение разметки x:Type
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 27
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db56c2bcdca14b87de320dfe19a6c364c76ecef7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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
 `x:Type` Расширение разметки получает аналогичные функции для `typeof()` оператором в C# или `GetType` оператор в Microsoft Visual Basic.  
  
 `x:Type` Расширение разметки предоставляет поведение преобразования из строки для свойств, которые принимают тип <xref:System.Type>. Входные данные — это тип XAML. Связь между тип входных данных XAML и выходных данных CLR <xref:System.Type> выводится, <xref:System.Type> — <xref:System.Xaml.XamlType.UnderlyingType%2A> входного <xref:System.Xaml.XamlType>, поиск необходимого <xref:System.Xaml.XamlType> на основе контекста схемы XAML и <xref:System.Windows.Markup.IXamlTypeResolver>предоставляет контекст службы.  
  
 В службах XAML .NET Framework, определяется обработка для данного расширения разметки <xref:System.Windows.Markup.TypeExtension> класса.  
  
 В реализациях конкретной платформы, некоторые свойства, принимающие <xref:System.Type> как значения можно принять имя типа напрямую (строковое значение типа `Name`). Тем не менее для реализации этого поведения является сложным сценарием. Примеры см. в следующем разделе «Примечания об использовании WPF».  
  
 Синтаксис атрибутов является наиболее распространенным синтаксисом, используемым с этим расширением разметки. Строковая лексема, указываемая после строки идентификатора `x:Type`, присваивается в качестве значения <xref:System.Windows.Markup.TypeExtension.TypeName%2A> соответствующего класса расширения <xref:System.Windows.Markup.TypeExtension>. В контексте схемы XAML по умолчанию для служб XAML .NET Framework, который основан на типах CLR, значение этого атрибута является <xref:System.Reflection.MemberInfo.Name%2A> нужного типа, или содержит, <xref:System.Reflection.MemberInfo.Name%2A> предшествует префикс для пространства имен XAML не по умолчанию сопоставление.  
  
 `x:Type` Расширения разметки может использоваться в синтаксисе элемента объекта. В этом случае укажите значение параметра <xref:System.Windows.Markup.TypeExtension.TypeName%2A> свойства, необходимые для правильной инициализации расширения.  
  
 `x:Type` Расширения разметки также может использоваться как атрибут verbose; Однако такое использование не является типичным: `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
  
### <a name="default-xaml-namespace-and-type-mapping"></a>Сопоставление типов и пространства имен XAML по умолчанию  
 Пространство имен XAML по умолчанию для программирования WPF содержит большинство типов XAML, что нужно для типовых сценариев XAML; Таким образом часто можно избежать префиксы при ссылке на значения типа XAML. Может потребоваться сопоставление префикса, если ссылка на тип из пользовательской сборки, а также для типов, существующих в сборке WPF, но из пространства имен CLR, которое не было сопоставлено пространству имен XAML по умолчанию. Дополнительные сведения о префиксы пространства имен языка XAML и сопоставление пространств имен CLR см. в разделе [пространства имен XAML и сопоставление пространства имен для WPF XAML](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).  
  
### <a name="type-properties-that-support-typename-as-string"></a>Свойства этой поддержки Typename как строки типа  
 WPF поддерживает методы, позволяющие указывать значения некоторых свойств типа <xref:System.Type> без необходимости `x:Type` использование расширения разметки. Вместо этого можно указать значение как строка с именем типа. Примером <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=nameWithType> и <xref:System.Windows.Style.TargetType%2A?displayProperty=nameWithType>. Поддержка этого поведения не обеспечивается через преобразователи типов или расширения разметки. Вместо этого это реализуется с помощью поведения отсрочки <xref:System.Windows.FrameworkElementFactory>.  
  
 Silverlight поддерживает аналогичные соглашения. На самом деле Silverlight не поддерживается `{x:Type}` в его поддержки языка XAML и не принимает `{x:Type}` варианты использования за пределами в некоторых случаях, которые предназначены для поддержки миграции XAML WPF Silverlight. Таким образом, поведение typename как строки встроенных все ознакомительную версию Silverlight встроенного свойства где <xref:System.Type> значение.  
  
## <a name="xaml-2009"></a>XAML 2009  
 XAML 2009 обеспечивает дополнительную поддержку для универсальные типы и изменяет поведение функции `x:TypeArguments` и `x:Type` поддержки.  
  
-   `x:TypeArguments` и элемент связанного объекта для создания экземпляра универсального объекта могут быть в элементах, отличные от корневого. Дополнительные сведения см. раздел «XAML 2009» [директива x: TypeArguments](../../../docs/framework/xaml-services/x-typearguments-directive.md).  
  
-   XAML 2009 поддерживает синтаксис для указания ограничения универсального типа в разметку. Это может использоваться `x:TypeArguments`, `x:Type`, или эти две функции в сочетании.  
  
-   Реализация WPF XAML при обработке XAML 2009 для загрузки также добавляет эту возможность неявного преобразования типов для определенных свойств платформы, которые используют тип <xref:System.Type>.  
  
 В WPF можно использовать возможности XAML 2009, но только для свободного XAML (XAML, который не является компилированной разметки). Скомпилированный с разметкой XAML и форма BAML кода XAML в настоящее время не поддерживают ключевые слова и компоненты XAML 2009.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Style>  
 [Стилизация и использование шаблонов](../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Общие сведения о языке XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Расширения разметки и XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
