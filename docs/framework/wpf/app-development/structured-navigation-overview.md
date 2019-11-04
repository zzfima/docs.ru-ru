---
title: Общие сведения о структурной навигации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- structured navigation [WPF]
ms.assetid: 025d30ef-fec5-436d-ad7a-5d5483331c26
ms.openlocfilehash: 09c3c57f3ac1009416a5c67b37c035fe30cd5b5e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425331"
---
# <a name="structured-navigation-overview"></a>Общие сведения о структурной навигации

Содержимое, которое может размещаться в приложении браузера XAML (XBAP), <xref:System.Windows.Controls.Frame>или <xref:System.Windows.Navigation.NavigationWindow> состоит из страниц, которые можно идентифицировать по гиперссылкам в виде пакетов URI. Структура страниц и способы навигации по ним с помощью гиперссылок называется топологией навигации. Такая топология подходит для различных типов приложений, особенно тех, в которых необходим переход по документам. В таких приложениях пользователь может перемещаться с одной страницы на другую даже при отсутствии связи между ними.

Тем не менее другие типы приложений содержат страницы, которым необходимо ссылаться друг на друга. Например, рассмотрим приложение управления персоналом, в котором есть одна страница со списком всех сотрудников организации — страница "Список сотрудников". На этой странице пользователи также могут добавить нового сотрудника, щелкнув гиперссылку. При ее щелчке открывается новая страница "Добавить сотрудника", на которой собираются сведения о новом сотруднике и возвращаются на страницу "Список сотрудников". При этом создается новый сотрудник и обновляется список. Этот стиль навигации аналогичен вызову метода для выполнения обработки и возврата значения, который называется структурным программированием. Таким образом, этот стиль навигации называется *структурной навигацией*.

Класс <xref:System.Windows.Controls.Page> не реализует поддержку структурированной навигации. Вместо этого класс <xref:System.Windows.Navigation.PageFunction%601> является производным от <xref:System.Windows.Controls.Page> и расширяет его базовыми конструкциями, необходимыми для структурированной навигации. В этом разделе показано, как установить структурированную навигацию с помощью <xref:System.Windows.Navigation.PageFunction%601>.

<a name="Structured_Navigation"></a>

## <a name="structured-navigation"></a>Структурная навигация

Когда одна страница вызывает другую в структурной навигации, необходимы некоторые или все из следующих видов поведения.

- Переход выполняется с вызывающей страницы на вызываемую. При этом могут передаваться параметры, необходимые вызываемой странице.

- Когда пользователь завершает работу с вызывающей страницей, вызванная страница может возвращать вызывающей странице следующее:

  - Возврат информации о состоянии, которая описывает, как была завершена работа с вызывающей страницей (например, пользователь нажал кнопку "ОК" или "Отмена").

  - Возврат данных, которые были получены от пользователя (например, сведения о новом сотруднике).

- Когда вызывающая страница возвращается к вызываемой, вызванная страница удаляется из журнала навигации, чтобы изолировать один экземпляр вызываемой страницы от другого.

Эти поведения показаны на следующем рисунке:

![На снимке экрана показан поток между вызывающей и вызываемой страницами.](./media/structured-navigation-overview/flow-between-calling-page-called-page.png)

Эти поведения можно реализовать с помощью <xref:System.Windows.Navigation.PageFunction%601> в качестве вызываемой страницы.

<a name="Structured_Navigation_with_PageFunction"></a>

## <a name="structured-navigation-with-pagefunction"></a>Структурная навигация с помощью PageFunction

В этом разделе показано, как реализовать базовый механизм структурированной навигации с использованием одного <xref:System.Windows.Navigation.PageFunction%601>. В этом примере <xref:System.Windows.Controls.Page> вызывает <xref:System.Windows.Navigation.PageFunction%601>, чтобы получить значение <xref:System.String> от пользователя и вернуть его.

### <a name="creating-a-calling-page"></a>Создание вызывающей страницы

Страница, вызывающая <xref:System.Windows.Navigation.PageFunction%601>, может быть либо <xref:System.Windows.Controls.Page>, либо <xref:System.Windows.Navigation.PageFunction%601>. В этом примере это <xref:System.Windows.Controls.Page>, как показано в следующем коде.

[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup1)]
[!code-xaml[StructuredNavigationSample#CallingPageDefaultMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#callingpagedefaultmarkup2)]

[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind1)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind1)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind2)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind2)]
[!code-csharp[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#callingpagedefaultcodebehind3)]
[!code-vb[StructuredNavigationSample#CallingPageDefaultCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#callingpagedefaultcodebehind3)]

### <a name="creating-a-page-function-to-call"></a>Создание страничной функции для вызова

Так как вызывающая страница может использовать вызываемую страницу для получения и возврата данных от пользователя, <xref:System.Windows.Navigation.PageFunction%601> реализуется как универсальный класс, аргумент типа которого указывает тип значения, возвращаемого вызываемой страницей. В следующем коде показана Начальная реализация вызываемой страницы с использованием <xref:System.Windows.Navigation.PageFunction%601>, которая возвращает <xref:System.String>.

[!code-xaml[StructuredNavigationSample#CalledPageFunctionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml#calledpagefunctionmarkup)]

[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind1)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind1)]
[!code-csharp[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#calledpagefunctioncodebehind2)]
[!code-vb[StructuredNavigationSample#CalledPageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#calledpagefunctioncodebehind2)]

Объявление <xref:System.Windows.Navigation.PageFunction%601> аналогично объявлению <xref:System.Windows.Controls.Page> с добавлением аргументов типа. Как видно из примера кода, аргументы типа указаны и в разметке [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] с помощью атрибута `x:TypeArguments`, и в коде программной части с помощью стандартного синтаксиса аргумента универсального типа.

Не нужно использовать .NET Framework классы в качестве аргументов типа. Можно вызвать <xref:System.Windows.Navigation.PageFunction%601> для сбора данных, относящихся к домену и абстрактных как пользовательский тип. В следующем коде показано, как использовать пользовательский тип в качестве аргумента типа для <xref:System.Windows.Navigation.PageFunction%601>.

[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode1)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode1)]
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomType.cs#customtypecode2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypeCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomType.vb#customtypecode2)]

[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup1)]
[!code-xaml[CustomTypePageFunctionSnippets#CustomTypePageFunctionMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml#customtypepagefunctionmarkup2)]

[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind1)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind1)]
[!code-csharp[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/CSharp/CustomTypePageFunction.xaml.cs#customtypepagefunctioncodebehind2)]
[!code-vb[CustomTypePageFunctionSnippets#CustomTypePageFunctionCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CustomTypePageFunctionSnippets/VisualBasic/CustomTypePageFunction.xaml.vb#customtypepagefunctioncodebehind2)]

Аргументы типа для <xref:System.Windows.Navigation.PageFunction%601> обеспечивают основу для обмена данными между вызывающей и вызываемой страницей, которые обсуждаются в следующих разделах.

Как вы увидите, тип, идентифицированный с помощью объявления <xref:System.Windows.Navigation.PageFunction%601> играет важную роль в возврате данных из <xref:System.Windows.Navigation.PageFunction%601> на вызывающую страницу.

### <a name="calling-a-pagefunction-and-passing-parameters"></a>Вызов PageFunction и передача параметров

Чтобы вызвать страницу, вызывающая страница должна создать экземпляр вызываемой страницы и выполнить переход к ней с помощью метода <xref:System.Windows.Navigation.NavigationService.Navigate%2A>. Это позволяет вызывающей странице передавать вызываемой начальные данные, например, значения по умолчанию для данных, собираемых вызываемой страницей.

В следующем коде показана вызываемая страница с конструктором без параметров для приема параметров из вызывающей страницы.

[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind1)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind2)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind3)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind3)]
[!code-csharp[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#acceptsinitialdatacodebehind4)]
[!code-vb[StructuredNavigationSample#AcceptsInitialDataCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#acceptsinitialdatacodebehind4)]

В следующем коде показана вызывающая страница, обрабатывающая событие <xref:System.Windows.Documents.Hyperlink.Click> <xref:System.Windows.Documents.Hyperlink>, чтобы создать экземпляр вызываемой страницы и передать ей начальное строковое значение.

[!code-xaml[StructuredNavigationSample#PassingDataMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml#passingdatamarkup2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind1)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind1)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind2)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind2)]
[!code-csharp[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#passingdatacodebehind3)]
[!code-vb[StructuredNavigationSample#PassingDataCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#passingdatacodebehind3)]

Необязательно передавать параметры вызываемой странице. Вместо этого можно сделать следующее.

- Из вызывающей страницы:

  1. Создайте экземпляр вызываемого <xref:System.Windows.Navigation.PageFunction%601> с помощью конструктора без параметров.

  2. Сохраните параметры в <xref:System.Windows.Application.Properties%2A>.

  3. Перейдите к вызываемой <xref:System.Windows.Navigation.PageFunction%601>.

- Из вызываемого <xref:System.Windows.Navigation.PageFunction%601>:

  - Получение и использование параметров, хранимых в <xref:System.Windows.Application.Properties%2A>.

Однако вскоре вы увидите, что и в этом случае потребуется код для создания экземпляра и перехода к вызываемой странице для сбора данных, возвращаемых вызываемой страницей. По этой причине <xref:System.Windows.Navigation.PageFunction%601> необходимо поддерживать в активном состоянии. в противном случае при следующем переходе к <xref:System.Windows.Navigation.PageFunction%601>[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] создает экземпляр <xref:System.Windows.Navigation.PageFunction%601> с помощью конструктора без параметров.

Однако до возврата вызываемой страницы она должна вернуть данные, которые могут быть получены вызывающей страницей.

### <a name="returning-task-result-and-task-data-from-a-task-to-a-calling-page"></a>Возврат результата и данных задачи из задачи на вызывающую страницу

Когда пользователь закончит использовать вызываемую страницу (в данном примере он нажимает кнопку "ОК" или "Отмена"), необходим возврат вызываемой страницы. Поскольку вызывающая страница использовала вызываемую для сбора данных от пользователя, вызывающей странице необходимо два типа информации:

1. Отменил ли пользователь вызываемую страницу (нажав кнопку "ОК" или "Отмена" в этом примере). Это позволяет вызывающей странице определить, следует ли обрабатывать данные, собранные вызывающей страницей от пользователя.

2. Данные, предоставленные пользователем.

Чтобы получить сведения, <xref:System.Windows.Navigation.PageFunction%601> реализует метод <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>. В следующем коде показан его вызов.

[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind1)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind1)]
[!code-csharp[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CalledPageFunction.xaml.cs#returncodebehind2)]
[!code-vb[StructuredNavigationSample#ReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CalledPageFunction.xaml.vb#returncodebehind2)]

В этом примере, если пользователь нажимает кнопку "Отмена", значение `null` возвращается вызывающей странице. Если нажата кнопка "ОК", возвращается строковый параметр, предоставленный пользователем. <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> — это метод `protected virtual`, который вызывается для возврата данных на вызывающую страницу. Данные должны быть упакованы в экземпляр универсального типа <xref:System.Windows.Navigation.ReturnEventArgs%601>, аргумент типа которого указывает тип значения, которое <xref:System.Windows.Navigation.ReturnEventArgs%601.Result%2A> возвращает. Таким образом, при объявлении <xref:System.Windows.Navigation.PageFunction%601> с определенным аргументом типа вы указываете, что <xref:System.Windows.Navigation.PageFunction%601> будет возвращать экземпляр типа, заданный аргументом типа. В этом примере аргумент типа и, следовательно, возвращаемое значение имеет тип <xref:System.String>.

При вызове <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> вызывающей странице требуется какой-то способ получения возвращаемого значения <xref:System.Windows.Navigation.PageFunction%601>. По этой причине <xref:System.Windows.Navigation.PageFunction%601> реализует событие <xref:System.Windows.Navigation.PageFunction%601.Return> для вызова обрабатываемых страниц. При вызове <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> вызывается <xref:System.Windows.Navigation.PageFunction%601.Return>, поэтому вызывающая страница может зарегистрироваться в <xref:System.Windows.Navigation.PageFunction%601.Return>, чтобы получить уведомление.

[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind1)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind1)]
[!code-csharp[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/StructuredNavigationSample/CSharp/CallingPage.xaml.cs#processresultcodebehind2)]
[!code-vb[StructuredNavigationSample#ProcessResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StructuredNavigationSample/VisualBasic/CallingPage.xaml.vb#processresultcodebehind2)]

### <a name="removing-task-pages-when-a-task-completes"></a>Удаление страниц задачи после завершения задачи

Когда вызываемая страница возвращается и пользователь не отменяет ее, вызывающая страница будет обрабатывать данные, предоставленные пользователем и возвращенные вызываемой страницей. Сбор данных таким способом, как правило, является изолированным действием. Когда возвращается вызываемая страница, вызывающей странице необходимо создать новую вызывающую страницу и перейти к ней для сбора дополнительных данных.

Однако, если вызываемая страница не удалена из журнала, пользователь сможет перейти обратно к предыдущему экземпляру вызывающей страницы. Будет ли <xref:System.Windows.Navigation.PageFunction%601> храниться в журнале, определяется свойством <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A>. По умолчанию функция страницы автоматически удаляется при вызове <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A>, так как <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> имеет значение `true`. Для сохранения функции страницы в журнале переходов после вызова <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> задайте для <xref:System.Windows.Navigation.PageFunctionBase.RemoveFromJournal%2A> значение `false`.

<a name="Other_Types_of_Structured_Navigation"></a>

## <a name="other-types-of-structured-navigation"></a>Другие типы структурной навигации

В этом разделе показано базовое использование <xref:System.Windows.Navigation.PageFunction%601> для поддержки структурированной навигации по вызовам и возврату. На этой основе можно создавать более сложные типы структурной навигации.

Например, иногда вызывающей странице требуется несколько страниц для сбора достаточного количества данных от пользователя или выполнения задачи. Использование нескольких страниц называется "мастер".

В других случаях для эффективной работы приложения могут иметь сложные топологии переходов, зависящие от структурной навигации. Дополнительную информацию см. в разделе [Общие сведения о топологиях навигации](navigation-topologies-overview.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [Общие сведения о топологиях навигации](navigation-topologies-overview.md)
