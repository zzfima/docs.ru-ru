---
title: Типы, перенесенные из WPF в System.Xaml
ms.date: 03/30/2017
helpviewer_keywords:
- WPF XAML [XAML Services], migration to System.Xaml
- XAML [XAML Services], System.Xaml and WPF
- System.Xaml [XAML Services], types migrated from WPF
ms.assetid: d79dabf5-a2ec-4e8d-a37a-67c4ba8a2b91
ms.openlocfilehash: 5aa2d8a39be47d9affb97c3b60e53c4722c63cce
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249816"
---
# <a name="types-migrated-from-wpf-to-systemxaml"></a>Типы мигрировали из WPF в System.Xaml

В .NET Framework 3.5 и .NET Framework 3.0 как Фонд презентации Windows (WPF), так и Фонд рабочего процесса Windows включали реализацию языка XAML. Многие из открытых типов, которые обеспечивают расширение для реализации XAML в WPF, существовали в сборках WindowsBase PresentationCore и PresentationFramework. Аналогичным образом, общедоступные типы, которые обеспечивали размноженность для Windows Workflow Foundation XAML, существовали в сборке System.Workflow.ComponentModel. В рамках .NET 4 некоторые типы, связанные с XAML, были перенесены в сборку System.Xaml. Обычная реализация языковых служб XAML Framework.NET Framework позволяет многим сценариям к распределению XAML, которые первоначально были определены реализацией XAML конкретной платформы, но теперь являются частью общей поддержки языка .NET Framework 4 XAML. В этой статье перечислены типы, которые были перенесены, и обсуждаются вопросы, связанные с миграцией.

## <a name="assemblies-and-namespaces"></a>Сборки и пространства имен

В .NET Framework 3.5 и .NET Framework 3.0 типы, реализованные WPF для поддержки XAML, как правило, находились в пространстве <xref:System.Windows.Markup> имен. Большинство из них были включены в сборку WindowsBase.

В .NET Framework 4 есть <xref:System.Xaml> новое пространство имен и новая сборка System.Xaml. Многие типы, которые первоначально были реализованы для XAML WPF, теперь предоставляются в виде точек расширения или служб для любой реализации XAML. Чтобы сделать типы доступными для более общих сценариев, они были перенесены из исходной сборки WPF в сборку System.Xaml. Это позволяет создавать сценарии экстраенционируемости XAML без необходимости включения в них сборки других инфраструктур (таких как WPF и Windows Workflow Foundation).

Большинство типов перенесенных типов остались в пространстве имен <xref:System.Windows.Markup> . Частично это было вызвано желанием избежать нарушения сопоставлений пространств имен среды CLR в существующих реализациях для каждого файла. В результате в <xref:System.Windows.Markup> пространстве имен в .NET Framework 4 содержится смесь общих типов поддержки языка XAML (от сборки System.Xaml) и типов, характерных для реализации WPF XAML (от WindowsBase и других сборок WPF). Любой тип, который был перенесены в сборку System.Xaml, но ранее существовал в сборке WPF, поддерживает перенаправление типов в 4 версии сборки WPF.

### <a name="workflow-xaml-support-types"></a>Типы поддержки XAML рабочего процесса

Фонд Windows Workflow также предоставил типы поддержки XAML, и во многих случаях они имели одинаковые короткие имена эквивалента WPF. Ниже приводится список типов поддержки Windows Workflow Flow Foundation XAML:

- <xref:System.Workflow.ComponentModel.Serialization.ContentPropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.RuntimeNamePropertyAttribute>

- <xref:System.Workflow.ComponentModel.Serialization.XmlnsPrefixAttribute>

Эти типы поддержки по-прежнему существуют в сборках Фонда рабочего процесса Windows для .NET Framework 4 и могут по-прежнему использоваться для конкретных приложений Фонда рабочего процесса Windows; однако на них не должны ссылаться приложения или фреймворки, не использовавающие Фонд рабочего процесса Windows.

## <a name="markupextension"></a>MarkupExtension

В .NET Framework 3.5 и .NET Framework <xref:System.Windows.Markup.MarkupExtension> 3.0 класс WPF находился в сборке WindowsBase. Параллельный класс для Windows <xref:System.Workflow.ComponentModel.Serialization.MarkupExtension>Workflow Foundation, существовал в сборке System.Workflow.ComponentModel. В системе .NET 4 <xref:System.Windows.Markup.MarkupExtension> класс переносится на сборку System.Xaml. В .NET Framework <xref:System.Windows.Markup.MarkupExtension> 4 предназначен для любого сценария повышения доступности XAML, который использует услуги .NET XAML, а не только для тех, которые основывается на конкретных инфраструктурах. Если это возможно, определенные платформы или пользовательский код в платформе также должны использовать класс <xref:System.Windows.Markup.MarkupExtension> для расширения XAML.

## <a name="markupextension-supporting-service-classes"></a>Вспомогательные классы службы MarkupExtension

.NET Framework 3.5 и .NET Framework 3.0 для WPF предоставили несколько услуг, которые были доступны <xref:System.Windows.Markup.MarkupExtension> для исполнителей и <xref:System.ComponentModel.TypeConverter> реализаций для поддержки использования типа/собственности в XAML. Вот эти службы.

- <xref:System.Windows.Markup.IProvideValueTarget>

- <xref:System.Windows.Markup.IUriContext>

- <xref:System.Windows.Markup.IXamlTypeResolver>

> [!NOTE]
> Другой службой от .NET Framework 3.5, связанной <xref:System.Windows.Markup.IReceiveMarkupExtension> с расширением разметки, является интерфейс. <xref:System.Windows.Markup.IReceiveMarkupExtension>не мигрировали и `[Obsolete]` отмечендля для .NET Framework 4. Сценарии, в которых ранее использовался <xref:System.Windows.Markup.IReceiveMarkupExtension> , следует применять обратные вызовы <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute> с атрибутами. <xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute> также помечен как `[Obsolete]`.

## <a name="xaml-language-features"></a>Возможности языка XAML

Некоторые возможности и компоненты языка XAML для WPF были доступны ранее в сборке PresentationFramework. Они были реализованы как подкласс <xref:System.Windows.Markup.MarkupExtension> для предоставления расширений разметки в XAML-разметке. В .NET Framework 4 они существуют в сборке System.Xaml, так что проекты, не включающие сборки WPF, могут использовать эти функции на языковом уровне XAML. WPF использует эти же реализации для приложений .NET Framework 4. Как в других случаях, перечисленных в этом разделе, поддерживающие типы по-прежнему размещены в пространстве имен <xref:System.Windows.Markup> , чтобы избежать повреждения прежних ссылок.

Следующая таблица содержит список классов поддержки XAML, определенных в сборке System.Xaml.

|Возможность языка XAML|Использование|
|---------------------------|-----------|
|<xref:System.Windows.Markup.ArrayExtension>|`<x:Array ...>`|
|<xref:System.Windows.Markup.NullExtension>|`{x:Null}`|
|<xref:System.Windows.Markup.StaticExtension>|`{x:Static ...}`|
|<xref:System.Windows.Markup.TypeExtension>|`{x:Type ...}`|

Хотя в сборке System.Xaml могут отсутствовать конкретные классы поддержки, общая логика обработки возможностей языка XAML теперь находится в сборке System.Xaml и реализованных средствах чтения и записи XAML. Например, `x:TypeArguments` — это атрибут, который обрабатывается средствами чтения и записи XAML из реализаций System.XAML. Как можно заметить, в потоке узлов XAML предусмотрена обработка в контексте схемы XAML по умолчанию (на основе CLR), представление системы типов XAML и т. д. В результате справочная документация для всех функций языкового уровня XAML является подтоп-темой для [служб XAML](../../../desktop-wpf/xaml-services/index.md) в [Настольном руководстве для Фонда презентации Windows (WPF).](../../../desktop-wpf/overview/index.md)

## <a name="valueserializer-and-supporting-classes"></a>ValueSerializer и классы поддержки

Класс <xref:System.Windows.Markup.ValueSerializer> поддерживает преобразование типов в строку, в частности для сериализации XAML, для которой может потребоваться несколько режимов или узлов в выходных данных. В .NET Framework 3.5 и .NET <xref:System.Windows.Markup.ValueSerializer> Framework 3.0, для WPF был в сборке WindowsBase. В .NET Framework 4 <xref:System.Windows.Markup.ValueSerializer> класс находится в System.Xaml и предназначен для любого сценария повышения доступности XAML, а не только для тех, которые основывается на WPF. <xref:System.Windows.Markup.IValueSerializerContext> (поддерживающая служба) и <xref:System.Windows.Markup.DateTimeValueSerializer> (конкретный подкласс) также перенесены в сборку System.Xaml.

## <a name="xaml-related-attributes"></a>Атрибуты, связанные с XAML

XAML в WPF содержал несколько атрибутов, которые можно было применять к типам CLR, чтобы указать что-то об их поведении в XAML. Ниже приводится список атрибутов, существовавших в сборках WPF в .NET Framework 3.5 и .NET Framework 3.0. Эти атрибуты переносятся на System.Xaml в .NET Framework 4.

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

## <a name="miscellaneous-classes"></a>Различные классы

Интерфейс <xref:System.Windows.Markup.IComponentConnector> существовал в WindowsBase в .NET Framework 3.5 и .NET Framework 3.0, но существует в System.Xaml в .NET Framework 4. <xref:System.Windows.Markup.IComponentConnector> в основном предназначен для поддержки инструментария и компиляторов разметки XAML.

Интерфейс <xref:System.Windows.Markup.INameScope> существовал в WindowsBase в .NET Framework 3.5 и .NET Framework 3.0, но существует в System.Xaml в .NET Framework 4. <xref:System.Windows.Markup.INameScope> определяет базовые операции для пространства имен XAML.

## <a name="xaml-related-classes-with-shared-names-that-exist-in-wpf-and-systemxaml"></a>Классы с общими именами, связанные с XAML, которые существуют в WPF и System.Xaml

Следующие классы существуют как в сборках WPF, так и в сборке System.Xaml в .NET Framework 4:

`XamlReader`

`XamlWriter`

`XamlParseException`

Реализация WPF находится в пространстве имен <xref:System.Windows.Markup> и в сборке PresentationFramework. Реализация System.Xaml находится в пространстве имен <xref:System.Xaml> . Если вы используете типы WPF или создаете производные типы от типов WPF, следует использовать реализации <xref:System.Windows.Markup.XamlReader> и <xref:System.Windows.Markup.XamlWriter> WPF вместо реализаций System.Xaml. Подробнее см. в разделе "Замечания" в <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> и <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>.

Если вы указываете ссылки на сборки WPF и System.Xaml и используете операторы `include` для пространств имен <xref:System.Windows.Markup> и <xref:System.Xaml> , вам может понадобиться полностью определить вызовы этих API, чтобы однозначно разрешить эти типы.
