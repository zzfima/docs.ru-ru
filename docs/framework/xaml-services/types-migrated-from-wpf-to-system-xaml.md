---
title: Типы, перенесенные из WPF в System.Xaml
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: c5e1c1ad838440419024a2abb44f86f6bce01061
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457041"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Типы, перенесенные из WPF в System.Xaml
В [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] и [!INCLUDE[net_v30_long](../../../includes/net-v30-long-md.md)], оба [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] и Windows Workflow Foundation содержат реализацию языка XAML. Многие из открытых типов, которые обеспечивают расширение для реализации XAML в WPF, существовали в сборках WindowsBase PresentationCore и PresentationFramework. Аналогично открытые типы, которые обеспечивают расширение для Windows Workflow Foundation XAML существовал в сборке System.Workflow.ComponentModel. В [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]некоторые типы, связанные с XAML, перенесены в сборку System.Xaml. Общая реализация .NET Framework служб языка XAML поддерживает многие сценарии расширения XAML, которые первоначально определялись реализацией XAML конкретной платформы но теперь являются частью общей поддержке языка .NET Framework 4 XAML. В этом разделе перечислены перенесенные типы и обсуждаются вопросы, относящиеся к миграции.  
  
<a name="assemblies_and_namespaces"></a>   
## <a name="assemblies-and-namespaces"></a>Сборки и пространства имен  
 В [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]типы, которые реализованы в WPF для поддержки XAML, обычно находились в пространстве имен <xref:System.Windows.Markup> . Большинство из них были включены в сборку WindowsBase.  
  
 В .NET Framework 4 доступна новая <xref:System.Xaml> пространства имен и новая сборка System.Xaml. Многие типы, которые первоначально были реализованы для XAML WPF, теперь предоставляются в виде точек расширения или служб для любой реализации XAML. Чтобы сделать типы доступными для более общих сценариев, они были перенесены из исходной сборки WPF в сборку System.Xaml. Это позволяет реализовать сценарии расширения XAML без включения сборок других платформ (например, WPF и Windows Workflow Foundation).  
  
 Большинство типов перенесенных типов остались в пространстве имен <xref:System.Windows.Markup> . Частично это было вызвано желанием избежать нарушения сопоставлений пространств имен среды CLR в существующих реализациях для каждого файла. В результате <xref:System.Windows.Markup> пространства имен в .NET Framework 4 содержит смесь общих типов поддержки языка XAML (из сборки System.Xaml) и типы, относящиеся к реализации WPF XAML (из WindowsBase и других сборок WPF). Любой тип, который был перенесены в сборку System.Xaml, но ранее существовал в сборке WPF, поддерживает перенаправление типов в 4 версии сборки WPF.  
  
### <a name="workflow-xaml-support-types"></a>Типы поддержки XAML рабочего процесса  
 Windows Workflow Foundation также предоставляемые типы поддержки XAML, и во многих случаях они имели идентичные короткие имена эквивалентов в WPF. Ниже приведен список типов поддержки Windows Workflow Foundation XAML:  
  
- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>  
  
 Поддержки типов по-прежнему существуют в сборках Windows Workflow Foundation для .NET Framework 4 и по-прежнему можно использовать для конкретных приложений Windows Workflow Foundation; Тем не менее они должны не должны ссылаться приложения и платформы, не использующие Windows Workflow Foundation.  
  
<a name="markupextension"></a>   
## <a name="markupextension"></a>MarkupExtension  
 В [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]класс <xref:System.Windows.Markup.MarkupExtension> для WPF находился в сборке WindowsBase. Параллельный класс для Windows Workflow Foundation, <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>, размещался в сборке System.Workflow.ComponentModel. В .NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> класс перенесен в сборку System.Xaml. В .NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> предназначен для любого сценария расширения XAML, который использует служб XAML .NET Framework, не только для тех, которые с конкретными платформами. Если это возможно, определенные платформы или пользовательский код в платформе также должны использовать класс <xref:System.Windows.Markup.MarkupExtension> для расширения XAML.  
  
<a name="markupextension_supporting_service_classes"></a>   
## <a name="markupextension-supporting-service-classes"></a>Вспомогательные классы службы MarkupExtension  
 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)] для WPF предоставляли ряд служб, доступных для реализаций <xref:System.Windows.Markup.MarkupExtension> и <xref:System.ComponentModel.TypeConverter> , для поддержки использования типа или свойства в XAML. Вот эти службы.  
  
- <xref:System.Windows.Markup.IProvideValueTarget>  
  
- <xref:System.Windows.Markup.IUriContext>  
  
- <xref:System.Windows.Markup.IXamlTypeResolver>  
  
> [!NOTE]
>  Другая служба из [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] , связанная с расширениями разметки, — это интерфейс <xref:System.Windows.Markup.IReceiveMarkupExtension> . <xref:System.Windows.Markup.IReceiveMarkupExtension> не был перенесен и помечен `[Obsolete]` для .NET Framework 4. Сценарии, в которых ранее использовался <xref:System.Windows.Markup.IReceiveMarkupExtension> , следует применять обратные вызовы <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> с атрибутами. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> также помечен как `[Obsolete]`.  
  
<a name="xaml_language_features"></a>   
## <a name="xaml-language-features"></a>Возможности языка XAML  
 Некоторые возможности и компоненты языка XAML для WPF были доступны ранее в сборке PresentationFramework. Они были реализованы как подкласс <xref:System.Windows.Markup.MarkupExtension> для предоставления расширений разметки в XAML-разметке. В .NET Framework 4 они находятся в сборке System.Xaml, проекты, которые не включают сборки WPF можно использовать эти возможности уровня языка XAML. WPF использует те же реализации для приложений .NET Framework 4. Как в других случаях, перечисленных в этом разделе, поддерживающие типы по-прежнему размещены в пространстве имен <xref:System.Windows.Markup> , чтобы избежать повреждения прежних ссылок.  
  
 Следующая таблица содержит список классов поддержки XAML, определенных в сборке System.Xaml.  
  
|Возможность языка XAML|Использование|  
|---------------------------|-----------|  
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|  
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|  
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|  
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|  
  
 Хотя в сборке System.Xaml могут отсутствовать конкретные классы поддержки, общая логика обработки возможностей языка XAML теперь находится в сборке System.Xaml и реализованных средствах чтения и записи XAML. Например, `x:TypeArguments` — это атрибут, который обрабатывается средствами чтения и записи XAML из реализаций System.XAML. Как можно заметить, в потоке узлов XAML предусмотрена обработка в контексте схемы XAML по умолчанию (на основе CLR), представление системы типов XAML и т. д. В результате справочная документацию для всех компонентов языка XAML представляет собой подраздел для [XAML Services](index.md) и соответствующего общего набора документации по платформе .NET Framework, а не часть набора документации WPF в виде подраздела [Дополнительно (Windows Presentation Foundation)](../wpf/advanced/index.md) (как в наборах документации версии 3.5).  
  
<a name="valueserializer_and_supporting_classes"></a>   
## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer и классы поддержки  
 Класс <xref:System.Windows.Markup.ValueSerializer> поддерживает преобразование типов в строку, в частности для сериализации XAML, для которой может потребоваться несколько режимов или узлов в выходных данных. В [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]класс <xref:System.Windows.Markup.ValueSerializer> для WPF находился в сборке WindowsBase. В .NET Framework 4 <xref:System.Windows.Markup.ValueSerializer> класс находится в System.Xaml и предназначен для любого сценария расширения XAML, не только для сценариев на основе WPF. <xref:System.Windows.Markup.IValueSerializerContext> (поддерживающая служба) и <xref:System.Windows.Markup.DateTimeValueSerializer> (конкретный подкласс) также перенесены в сборку System.Xaml.  
  
<a name="xamlrelated_attributes"></a>   
## <a name="xaml-related-attributes"></a>Атрибуты, связанные с XAML  
 XAML в WPF содержал несколько атрибутов, которые можно было применять к типам CLR, чтобы указать что-то об их поведении в XAML. Ниже приведен список атрибутов, которые существовали в сборках WPF в [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)]. Они перенесены в System.Xaml в .NET Framework 4.  
  
- <xref:System.Windows.Markup.AmbientAttribute>  
  
- <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
- <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
- <xref:System.Windows.Markup.DependsOnAttribute>  
  
- <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
- <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
- <xref:System.Windows.Markup.RootNamespaceAttribute>  
  
- <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
- <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
- <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
- <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
- <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
- <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
- <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
- <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
<a name="miscellaneous_classes"></a>   
## <a name="miscellaneous-classes"></a>Различные классы  
 <xref:System.Windows.Markup.IComponentConnector> Интерфейс существовал в WindowsBase в [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)], но размещен в System.Xaml в .NET Framework 4. <xref:System.Windows.Markup.IComponentConnector> в основном предназначен для поддержки инструментария и компиляторов разметки XAML.  
  
 <xref:System.Windows.Markup.INameScope> Интерфейс существовал в WindowsBase в [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] и [!INCLUDE[net_v30_short](../../../includes/net-v30-short-md.md)], но размещен в System.Xaml в .NET Framework 4. <xref:System.Windows.Markup.INameScope> определяет базовые операции для пространства имен XAML.  
  
<a name="xamlrelated_classes_with_shared_names_that_exist_in_wpf_and_systemxaml"></a>   
## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>Классы с общими именами, связанные с XAML, которые существуют в WPF и System.Xaml  
 Следующие классы существуют в сборках WPF и в сборке System.Xaml в .NET Framework 4:  
  
 `XamlReader`  
  
 `XamlWriter`  
  
 `XamlParseException`  
  
 Реализация WPF находится в пространстве имен <xref:System.Windows.Markup> и в сборке PresentationFramework. Реализация System.Xaml находится в пространстве имен <xref:System.Xaml> . Если вы используете типы WPF или создаете производные типы от типов WPF, следует использовать реализации <xref:System.Windows.Markup.XamlReader> и <xref:System.Windows.Markup.XamlWriter> WPF вместо реализаций System.Xaml. Подробнее см. в разделе "Замечания" в <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> и <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.  
  
 Если вы указываете ссылки на сборки WPF и System.Xaml и используете операторы `include` для пространств имен <xref:System.Windows.Markup> и <xref:System.Xaml> , вам может понадобиться полностью определить вызовы этих API, чтобы однозначно разрешить эти типы.  
  
## <a name="see-also"></a>См. также

- [Службы XAML](index.md)
