---
title: Типы, перенесенные из WPF в System.Xaml
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 943cdb2a21cbf2f95ef7fe2feefe6c0e71f57be4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939680"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Типы, перенесенные из WPF в System.Xaml
В .NET Framework 3,5 и .NET Framework 3,0 как, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] так и Windows Workflow Foundation включала реализацию языка XAML. Многие из открытых типов, которые обеспечивают расширение для реализации XAML в WPF, существовали в сборках WindowsBase PresentationCore и PresentationFramework. Аналогичным образом, открытые типы, которые обеспечивают расширяемость для Windows Workflow Foundation XAML, существовали в сборке System. Workflow. ComponentModel. В .NET Framework 4 некоторые из типов, связанных с XAML, переносятся в сборку System. XAML. Распространенная реализация .NET Framework языковых служб XAML позволяет реализовать многие сценарии расширения XAML, которые изначально были определены реализацией XAML конкретной платформы, но теперь являются частью общей .NET Framework 4-языковой поддержки языка XAML. В этом разделе перечислены перенесенные типы и обсуждаются вопросы, относящиеся к миграции.  
  
<a name="assemblies_and_namespaces"></a>   
## <a name="assemblies-and-namespaces"></a>Сборки и пространства имен  
 В .NET Framework 3,5 и .NET Framework 3,0 типы, реализованные в WPF для поддержки XAML, обычно находятся в <xref:System.Windows.Markup> пространстве имен. Большинство из них были включены в сборку WindowsBase.  
  
 В .NET Framework 4 имеется новое <xref:System.Xaml> пространство имен и новая сборка System. XAML. Многие типы, которые первоначально были реализованы для XAML WPF, теперь предоставляются в виде точек расширения или служб для любой реализации XAML. Чтобы сделать типы доступными для более общих сценариев, они были перенесены из исходной сборки WPF в сборку System.Xaml. Это позволяет использовать сценарии расширяемости XAML без необходимости включать сборки других платформ (например, WPF и Windows Workflow Foundation).  
  
 Большинство типов перенесенных типов остались в пространстве имен <xref:System.Windows.Markup> . Частично это было вызвано желанием избежать нарушения сопоставлений пространств имен среды CLR в существующих реализациях для каждого файла. В результате <xref:System.Windows.Markup> пространство имен в .NET Framework 4 содержит сочетание общих типов поддержки языка XAML (из сборки System. XAML) и типов, характерных для реализации XAML в WPF (из WindowsBase и других сборок WPF). Любой тип, который был перенесены в сборку System.Xaml, но ранее существовал в сборке WPF, поддерживает перенаправление типов в 4 версии сборки WPF.  
  
### <a name="workflow-xaml-support-types"></a>Типы поддержки XAML рабочего процесса  
 Windows Workflow Foundation также предоставлены типы поддержки XAML, и во многих случаях они имели одинаковые короткие имена для эквивалента WPF. Ниже приведен список типов поддержки Windows Workflow Foundation XAML.  
  
- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>  
  
- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>  
  
 Эти типы поддержки по-прежнему существуют в сборках Windows Workflow Foundation для .NET Framework 4 и по-прежнему могут использоваться для конкретных приложений Windows Workflow Foundation; Однако на них не должны ссылаться приложения или платформы, не использующие Windows Workflow Foundation.  
  
<a name="markupextension"></a>   
## <a name="markupextension"></a>MarkupExtension  
 В .NET Framework 3,5 и .NET Framework 3,0 <xref:System.Windows.Markup.MarkupExtension> класс для WPF находился в сборке WindowsBase. Параллельный класс для Windows Workflow Foundation <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>,, существовал в сборке System. Workflow. ComponentModel. В .NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> класс переносится в сборку System. XAML. В .NET Framework 4 <xref:System.Windows.Markup.MarkupExtension> предназначен для любого сценария расширения XAML, использующего .NET Framework служб XAML, а не только для тех, которые построены на конкретных платформах. Если это возможно, определенные платформы или пользовательский код в платформе также должны использовать класс <xref:System.Windows.Markup.MarkupExtension> для расширения XAML.  
  
<a name="markupextension_supporting_service_classes"></a>   
## <a name="markupextension-supporting-service-classes"></a>Вспомогательные классы службы MarkupExtension  
 .NET Framework 3,5 и .NET Framework 3,0 для WPF предоставил несколько служб, которые были доступны <xref:System.Windows.Markup.MarkupExtension> для разработчиков и <xref:System.ComponentModel.TypeConverter> реализаций для поддержки использования типа/свойства в XAML. Вот эти службы.  
  
- <xref:System.Windows.Markup.IProvideValueTarget>  
  
- <xref:System.Windows.Markup.IUriContext>  
  
- <xref:System.Windows.Markup.IXamlTypeResolver>  
  
> [!NOTE]
> Другой службой из .NET Framework 3,5, которая связана с расширениями разметки <xref:System.Windows.Markup.IReceiveMarkupExtension> , является интерфейс. <xref:System.Windows.Markup.IReceiveMarkupExtension>не был перенесен и помечен `[Obsolete]` для .NET Framework 4. Сценарии, в которых ранее использовался <xref:System.Windows.Markup.IReceiveMarkupExtension> , следует применять обратные вызовы <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> с атрибутами. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> также помечен как `[Obsolete]`.  
  
<a name="xaml_language_features"></a>   
## <a name="xaml-language-features"></a>Возможности языка XAML  
 Некоторые возможности и компоненты языка XAML для WPF были доступны ранее в сборке PresentationFramework. Они были реализованы как подкласс <xref:System.Windows.Markup.MarkupExtension> для предоставления расширений разметки в XAML-разметке. В .NET Framework 4 они существуют в сборке System. XAML, чтобы проекты, которые не содержат сборки WPF, могли использовать эти функции на уровне языка XAML. WPF использует те же реализации для приложений .NET Framework 4. Как в других случаях, перечисленных в этом разделе, поддерживающие типы по-прежнему размещены в пространстве имен <xref:System.Windows.Markup> , чтобы избежать повреждения прежних ссылок.  
  
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
 Класс <xref:System.Windows.Markup.ValueSerializer> поддерживает преобразование типов в строку, в частности для сериализации XAML, для которой может потребоваться несколько режимов или узлов в выходных данных. В .NET Framework 3,5 и .NET Framework 3,0, <xref:System.Windows.Markup.ValueSerializer> для WPF находилась в сборке WindowsBase. В .NET Framework 4 <xref:System.Windows.Markup.ValueSerializer> класс находится в System. XAML и предназначен для любого сценария расширения XAML, а не только для тех, которые построены на WPF. <xref:System.Windows.Markup.IValueSerializerContext> (поддерживающая служба) и <xref:System.Windows.Markup.DateTimeValueSerializer> (конкретный подкласс) также перенесены в сборку System.Xaml.  
  
<a name="xamlrelated_attributes"></a>   
## <a name="xaml-related-attributes"></a>Атрибуты, связанные с XAML  
 XAML в WPF содержал несколько атрибутов, которые можно было применять к типам CLR, чтобы указать что-то об их поведении в XAML. Ниже приведен список атрибутов, которые существовали в сборках WPF в .NET Framework 3,5 и .NET Framework 3,0. Эти атрибуты переносятся в System. XAML в .NET Framework 4.  
  
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
 <xref:System.Windows.Markup.IComponentConnector> Интерфейс существовал в WindowsBase .NET Framework 3,5 и .NET Framework 3,0, но существует в System. XAML в .NET Framework 4. <xref:System.Windows.Markup.IComponentConnector> в основном предназначен для поддержки инструментария и компиляторов разметки XAML.  
  
 <xref:System.Windows.Markup.INameScope> Интерфейс существовал в WindowsBase .NET Framework 3,5 и .NET Framework 3,0, но существует в System. XAML в .NET Framework 4. <xref:System.Windows.Markup.INameScope> определяет базовые операции для пространства имен XAML.  
  
<a name="xamlrelated_classes_with_shared_names_that_exist_in_wpf_and_systemxaml"></a>   
## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>Классы с общими именами, связанные с XAML, которые существуют в WPF и System.Xaml  
 Следующие классы существуют как в сборках WPF, так и в сборке System. XAML в .NET Framework 4:  
  
 `XamlReader`  
  
 `XamlWriter`  
  
 `XamlParseException`  
  
 Реализация WPF находится в пространстве имен <xref:System.Windows.Markup> и в сборке PresentationFramework. Реализация System.Xaml находится в пространстве имен <xref:System.Xaml> . Если вы используете типы WPF или создаете производные типы от типов WPF, следует использовать реализации <xref:System.Windows.Markup.XamlReader> и <xref:System.Windows.Markup.XamlWriter> WPF вместо реализаций System.Xaml. Подробнее см. в разделе "Замечания" в <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> и <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.  
  
 Если вы указываете ссылки на сборки WPF и System.Xaml и используете операторы `include` для пространств имен <xref:System.Windows.Markup> и <xref:System.Xaml> , вам может понадобиться полностью определить вызовы этих API, чтобы однозначно разрешить эти типы.  
  
## <a name="see-also"></a>См. также

- [Службы XAML](index.md)
