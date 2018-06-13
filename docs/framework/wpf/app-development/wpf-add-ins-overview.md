---
title: Общие сведения о надстройках WPF
ms.date: 03/30/2017
helpviewer_keywords:
- add-ins and XAML browser applications [WPF]
- add-ins overview [WPF]
- add-ins [WPF], performance
- add-ins [WPF], benefits
- .NET Framework add-in model [WPF]
- add-ins [WPF], user interface
- add-ins and the user interface [WPF]
- add-ins [WPF], architecture
- add-ins [WPF], limitations
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
ms.openlocfilehash: 942f5706a83a9f9e9cd969701ed5625c57b76f83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557866"
---
# <a name="wpf-add-ins-overview"></a>Общие сведения о надстройках WPF
<a name="Introduction"></a> [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] включает модель надстроек, которую разработчики могут использовать для создания приложений, поддерживающих расширения среды с использованием надстроек. Эта модель позволяет создавать надстройки, которые интегрируются с функциональностью приложения и расширяют ее. В некоторых сценариях приложения также должны отображать [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], которые предоставляются надстройками. В данном разделе показано, как [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для поддержки этих сценариев, описаны ее архитектура, преимущества и ограничения.  
  

  
<a name="Requirements"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Необходимо ознакомиться с моделью надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Дополнительные сведения см. в разделе [Надстройки и расширяемость](../../../../docs/framework/add-ins/index.md).  
  
<a name="AddInsOverview"></a>   
## <a name="add-ins-overview"></a>Общие сведения о надстройках  
 Чтобы избежать сложностей повторной компиляции и развертывания приложений для включения новых функциональных возможностей, приложения реализуют механизмы расширяемости, которые позволяют разработчикам (как собственным, так и сторонним) создавать другие приложения с поддержкой интеграции. Наиболее распространенным способом поддержки этого типа расширяемости является использование надстроек (также называемых "подключаемыми модулями"). Примеры реальных приложений, которые обеспечивают расширяемость с помощью надстроек:  
  
-   Надстройки Internet Explorer.  
  
-   Надстройки проигрывателя Windows Media.  
  
-   Надстройки Visual Studio.  
  
 Например, модель надстроек проигрывателя Windows Media позволяет сторонним разработчикам реализовать "подключаемые модули", расширяющие возможности проигрывателя Windows Media различными способами, включая создание декодеров и кодировщиков для форматов мультимедиа, изначально не поддерживаемых проигрывателем Windows Media (например: DVD, MP3), а также звуковых эффектов и обложек. Каждая модель надстройки создается для предоставления функций, уникальных для приложения, хотя существует несколько элементов и поведений, общих для всех моделей.  
  
 Тремя основными сущностями типичных решений расширяемости являются *контракты*, *надстройки* и *ведущие приложения*. Контракты определяют интеграцию надстроек с ведущими приложениями двумя способами:  
  
-   Надстройки интегрируются с функциональными возможностями, реализуемыми ведущими приложениями.  
  
-   Ведущие приложения предоставляют функциональные возможности для надстроек, с которыми интегрируются.  
  
 Чтобы использовать надстройки, ведущие приложения должны найти их и загрузить во время выполнения. Следовательно, приложения, поддерживающие надстройки, имеют следующие дополнительные обязанности:  
  
-   **Обнаружение**: поиск надстроек, которые соответствуют контрактам, поддерживаемым ведущими приложениями.  
  
-   **Активация**: загрузка, запуск и установка связи с надстройками.  
  
-   **Изоляция**: использование доменов приложений или процессов для установления границ изоляции, защищающих приложения от потенциальных проблем безопасности и выполнения, связанных с надстройками.  
  
-   **Обмен данными**: разрешение надстройкам и ведущим приложениям взаимодействовать друг с другом через границы изоляции путем вызова методов и передачи данных.  
  
-   **Управление жизненным циклом объекта**: загрузка и выгрузка доменов приложений и процессов ясным, прогнозируемым способом (см. [Домены приложений](../../../../docs/framework/app-domains/application-domains.md)).  
  
-   **Управление версиями**: гарантия возможности взаимодействия ведущих приложений и надстроек после создания их новых версий.  
  
 В конечном счете разработка надежной модели надстройки является нетривиальный задачей. По этой причине [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] обеспечивает инфраструктуру для создания моделей надстроек.  
  
> [!NOTE]
>  Более подробные сведения о надстройках см. в разделе [Надстройки и расширения среды](../../../../docs/framework/add-ins/index.md).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>Общие сведения о модели надстроек платформы .NET Framework  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Добавить в модель, находящаяся в <xref:System.AddIn> имен, содержит набор типов, которые предназначены для упрощения разработки расширяемости надстроек. Основной единицей модели надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] является *контракт*, который определяет, как ведущее приложение и надстройка взаимодействуют друг с другом. Контракт предоставляется ведущему приложению с помощью специфичного для ведущего приложения *представления* контракта. Аналогичным образом надстройке предоставляется специфичное для нее *представление* контракта. *Адаптер* позволяет ведущему приложению и надстройке обмениваться данными между соответствующими представлениями контракта. Контракты, представления и адаптеры называются сегментами, а набор связанных сегментов составляет *конвейер*. Конвейеры — это основа, на базе которой модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] поддерживает обнаружение, активацию, изоляцию в целях безопасности, изоляцию выполнения (используя как домены приложений, так и процессы), обмен данными, управление жизненным циклом и управление версиями.  
  
 Эта поддержка в целом позволяет разработчикам создавать надстройки, которые интегрируются с функциональностью ведущего приложения. Однако в некоторых сценариях требуется, чтобы ведущее приложение отображало [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], предоставляемое надстройками. Поскольку каждая технология представления в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] имеет свою собственную модель реализации [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] не поддерживает какую-либо определенную технологию представления. Вместо этого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] с помощью поддержки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для надстроек.  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>Надстройки WPF  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в сочетании с моделью надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] позволяет обращаться к широкому спектру сценариев, необходимых ведущим приложениям для отображения [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] из надстроек. В частности, эти сценарии реализуются в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] с помощью следующих двух моделей программирования.  
  
1.  **Надстройка возвращает пользовательский интерфейс**. Надстройка возвращает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущему приложению с помощью вызова метода, как это определено контрактом. Этот сценарий используется в следующих случаях.  
  
    -   Внешний вид [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], возвращаемого надстройкой, зависит от данных или условий, которые существуют только во время выполнения, например динамически создаваемые отчеты.  
  
    -   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для служб, предоставляемых надстройкой, отличается от [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущих приложений, которые могут использовать надстройку.  
  
    -   Надстройка исполняет службу для ведущего приложения и сообщает ведущему приложению о статусе с помощью [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
2.  **Надстройка — это пользовательский интерфейс**. Надстройка — это [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], как определено в контракте. Этот сценарий используется в следующих случаях.  
  
    -   Надстройка не предоставляет службы помимо отображения, например рекламного объявления.  
  
    -   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для служб, предоставляемых надстройкой, является общим для всех ведущих приложений, которые могут использовать эту надстройку, например калькулятор или палитру.  
  
 Эти сценарии требуют возможности передачи объектов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] между доменами ведущих приложений и приложений надстроек. Поскольку модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] основана на удаленном взаимодействии между доменами приложений, передаваемые между ними объекты должны поддерживать удаленную обработку.  
  
 Объект, поддерживающий удаленную обработку, является экземпляром класса, который выполняет одну или несколько из следующих функций:  
  
-   Является производным от <xref:System.MarshalByRefObject> класса.  
  
-   Реализует интерфейс <xref:System.Runtime.Serialization.ISerializable>.  
  
-   Имеет <xref:System.SerializableAttribute> применен атрибут.  
  
> [!NOTE]
>  Дополнительные сведения о создании удаленных объектов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] см. в разделе [Обеспечение поддержки удаленного взаимодействия с объектами](http://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a).  
  
 Типы [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] не поддерживают удаленное взаимодействие. Для решения этой проблемы [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], чтобы разрешить отображение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], созданных надстройками, из ведущих приложений. Эта поддержка обеспечивается [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] двух типов: <xref:System.AddIn.Contract.INativeHandleContract> интерфейс и два статических методов, реализованных <xref:System.AddIn.Pipeline.FrameworkElementAdapters> класса: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> и <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. На высоком уровне эти типы и методы используются следующим образом:  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] требуется [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] , предоставляемые надстройки — это классы, прямо или косвенно наследующие от <xref:System.Windows.FrameworkElement>, таких как фигуры, элементы управления, пользовательские элементы управления, панели макета и страниц.  
  
2.  Везде, где контракт объявляет, что пользовательский Интерфейс будет передаваться между надстройкой и ведущим приложением, должен быть объявлен как <xref:System.AddIn.Contract.INativeHandleContract> (не <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> является удаленным представлением надстройки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] могут передаваться через границы изоляции.  
  
3.  Перед передачей из надстройки в домен приложения <xref:System.Windows.FrameworkElement> упаковывается в виде <xref:System.AddIn.Contract.INativeHandleContract> путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  После передачи домен приложения ведущего приложения, <xref:System.AddIn.Contract.INativeHandleContract> нужно упаковать в <xref:System.Windows.FrameworkElement> путем вызова <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Как <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, и <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> используются зависит от конкретного сценария. В следующих разделах содержатся сведения о каждой модели программирования.  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>Надстройка возвращает пользовательский интерфейс  
 Чтобы надстройка возвращала [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в ведущее приложение, необходимо выполнить следующее.  
  
1.  Ведущее приложение, надстройка и конвейер должны быть созданы в соответствии с документацией [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [Надстройки и расширения среды](../../../../docs/framework/add-ins/index.md).  
  
2.  Контракт должен реализовать <xref:System.AddIn.Contract.IContract> и для возврата [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], контракт должен объявить метод с возвращаемым значением типа <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , Передаваемого между надстройкой и узлом приложения должен прямо или косвенно наследовать <xref:System.Windows.FrameworkElement>.  
  
4.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] , Возвращаемый надстройка должна быть преобразована из <xref:System.Windows.FrameworkElement> для <xref:System.AddIn.Contract.INativeHandleContract> до пересечения границы изоляции.  
  
5.  [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Возвращается должна быть преобразована из <xref:System.AddIn.Contract.INativeHandleContract> для <xref:System.Windows.FrameworkElement> после пересечения границы изоляции.  
  
6.  Ведущее приложение отображает возвращаемый <xref:System.Windows.FrameworkElement>.  
  
 Пример, который демонстрирует реализацию надстройки, возвращающей [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], см. в разделе [Создание надстройки, возвращающей пользовательский интерфейс](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>Надстройка является пользовательским интерфейсом  
 Если надстройка является [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], необходимо выполнение следующих условий.  
  
1.  Ведущее приложение, надстройка и конвейер должны быть созданы в соответствии с документацией [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [Надстройки и расширения среды](../../../../docs/framework/add-ins/index.md).  
  
2.  Необходимо реализовать интерфейс контракта для надстройки <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  Надстройки, которая передается в ведущее приложение должно прямо или косвенно наследовать <xref:System.Windows.FrameworkElement>.  
  
4.  Надстройка должна быть преобразована из <xref:System.Windows.FrameworkElement> для <xref:System.AddIn.Contract.INativeHandleContract> до пересечения границы изоляции.  
  
5.  Надстройка должна быть преобразована из <xref:System.AddIn.Contract.INativeHandleContract> для <xref:System.Windows.FrameworkElement> после пересечения границы изоляции.  
  
6.  Ведущее приложение отображает возвращаемый <xref:System.Windows.FrameworkElement>.  
  
 Пример реализации надстройки, которая является [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], см. в разделе [Создание надстройки, являющейся пользовательским интерфейсом](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>Возвращение нескольких пользовательских интерфейсов из надстройки  
 Надстройки часто предоставляют несколько [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] для отображения ведущими приложениями. Например, рассмотрим надстройку, являющуюся [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], которая также предоставляет ведущему приложению сведения о состоянии, аналогично [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Такие надстройки можно реализовать с помощью сочетания методов из моделей [Надстройка возвращает пользовательский интерфейс](#ReturnUIFromAddInContract) и [Надстройка является пользовательским интерфейсом](#AddInIsAUI).  
  
<a name="AddInsAndXBAPs"></a>   
## <a name="add-ins-and-xaml-browser-applications"></a>Надстройки и приложения браузера XAML  
 В приведенных примерах ведущее приложение было установленным автономным приложением. Однако [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] также может размещать надстройки, хотя при этом применяются следующие дополнительные требования к сборке и реализации.  
  
-   Манифест приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] должен быть настроен специально для загрузки конвейера (папок и сборок) и сборки надстройки в кэш приложения [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] на клиентской машине в той же папке, где находится [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   Код [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] для обнаружения и загрузки надстроек должен использовать кэш приложения [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] для [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] в качестве расположения конвейера и надстройки.  
  
-   [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] должен загрузить надстройку в специальный контекст безопасности, если надстройка ссылается на свободные файлы, расположенные на исходном узле. Если они размещаются в [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)], надстройки могут ссылаться только на свободные файлы, расположенные на исходном узле ведущего приложения.  
  
 Эти задачи подробно описаны в следующих подразделах.  
  
### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>Настройка конвейера и надстройки для развертывания ClickOnce  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] загружается в безопасную папку в [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] кэше развертывания и запускается из нее. Для размещения надстройки в [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] конвейер и сборка надстройки также должны быть загружены в безопасную папку. Для этого нужно настроить манифест приложения для включения и конвейера и сборки надстройки для загрузки. Проще всего это сделать в [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], хотя сборка конвейера и надстройки должна находиться в корневой папке проекта [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], чтобы [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] мог обнаружить сборочные узлы конвейера.  
  
 Следовательно, первый шаг — создать сборку конвейера и надстройки в корне проекта [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], настроив выходные данные построения для каждого проекта сборки конвейера и сборки надстройки. В следующей таблице показаны выходные пути построения для проектов сборки конвейера и проекта сборки надстройки, которые находятся в том же решении и корневой папке, что и проект ведущего приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
 Таблица 1. Создание выходных путей построения для сборок конвейера, размещаемых в XBAP  
  
|Проект сборки конвейера|Выходной путь сборки|  
|-------------------------------|-----------------------|  
|Контракт|`..\HostXBAP\Contracts\`|  
|Представление надстройки|`..\HostXBAP\AddInViews\`|  
|Адаптер надстройки|`..\HostXBAP\AddInSideAdapters\`|  
|Адаптер приложения|`..\HostXBAP\HostSideAdapters\`|  
|Надстройка|`..\HostXBAP\AddIns\WPFAddIn1`|  
  
 Следующим шагом является указание сборок конвейера и сборки надстройки как файлов содержимого [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] в [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] следующим образом.  
  
1.  Включение сборки конвейера и надстройки в проект. Для этого следует щелкнуть правой кнопкой мыши каждую папку конвейера в обозревателе решений и выбрать вариант **Включить в проект**.  
  
2.  Установка для **Действия при построении** для каждой сборки конвейера и надстройки значения **Содержимое** в окне **Свойства**.  
  
 Последним шагом является настройка манифеста приложения для включения файлов сборки конвейера и файла сборки надстройки для загрузки. Файлы должны располагаться в папках в корне папки в кэше [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], занимаемом приложением [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Эта конфигурация может реализовываться в [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] следующим образом:  
  
1.  Щелкните правой кнопкой мыши проект [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], выберите **Свойства**, **Публиковать**, а затем нажмите кнопку **Файлы приложения**.  
  
2.  В диалоговом окне **Файлы приложения** установите для параметра **Состояния публикации** каждой DLL конвейера и надстройки значение **Включить (авто)**, а для **Группы загрузки** для каждой DLL конвейера и надстройки — значение **(обязательно)**.  
  
### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>Использование конвейера и надстройки из базовой папки приложения  
 Если конвейер и надстройка настроены для развертывания [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], они загружаются в ту же папку кэша [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], что и [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Чтобы использовать конвейер и надстройку из [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], код [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] должен получить их из базовой папки приложения. Различные типы и элементы модели надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для использования конвейеров и надстроек обеспечивают специальную поддержку этого сценария. Во-первых, путь определяется по <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> значение перечисления. Это значение используется при перегрузках соответствующих элементов надстройки для использования конвейеров, которые включают следующее:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>Доступ к исходному узлу ведущего приложения  
 Чтобы надстройка могла ссылаться на файлы с исходного узла, она должна быть загружена с изоляцией безопасности, эквивалентной ведущему приложению. Этот уровень безопасности определяется <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> значение перечисления и передается <xref:System.AddIn.Hosting.AddInToken.Activate%2A> метод при активизации add-in.  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>Архитектура надстроек WPF  
 На высоком уровне как мы увидели, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] надстройки для реализации [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] (прямо или косвенно, производные от <xref:System.Windows.FrameworkElement>) с помощью <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> и <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Результат заключается в том, что ведущее приложение возвращается <xref:System.Windows.FrameworkElement> , берется из [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в ведущем приложении.  
  
 Для простых сценариев надстройки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] этих сведений достаточно для разработчиков. В более сложных сценариях, в частности тех, где предпринимается попытка использовать дополнительные службы [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], такие как макет, ресурсы и привязки данных, для понимания всех преимуществ и ограничений нужны более подробные сведения о том, как [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет модель надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] с помощью поддержки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 По существу, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] не передает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] из надстройки в ведущее приложение. Вместо этого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] передает дескриптор окна Win32 для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], используя взаимодействие [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Таким образом, когда [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] из надстройки передается в ведущее приложение, происходит следующее.  
  
-   На стороне надстройки [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] получает дескриптор окна для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который будет отображаться ведущим приложением. Дескриптор окна инкапсулируется внутренним [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] класс, производный от <xref:System.Windows.Interop.HwndSource> и реализует <xref:System.AddIn.Contract.INativeHandleContract>. Экземпляр этого класса возвращается с <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> и маршалируется из надстройки в домен приложения в домен приложения ведущего приложения.  
  
-   На стороне ведущего приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] переупаковывает <xref:System.Windows.Interop.HwndSource> как внутренний [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] класс, производный от <xref:System.Windows.Interop.HwndHost> и использует <xref:System.AddIn.Contract.INativeHandleContract>. Экземпляр этого класса возвращается с <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> в ведущее приложение.  
  
 <xref:System.Windows.Interop.HwndHost> существует для отображения [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], определенные с дескрипторами окон из [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]. Более подробную информацию см. в разделе [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
 Таким образом <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, и <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> , позволяющие дескриптор окна для [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] должен передаваться из надстройки в ведущее приложение, где он инкапсулируется <xref:System.Windows.Interop.HwndHost> и отображается в узле приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
> [!NOTE]
>  Поскольку ведущее приложение получает <xref:System.Windows.Interop.HwndHost>, ведущее приложение не может преобразовать объект, возвращаемый <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> в тип реализуется как надстройки (например, <xref:System.Windows.Controls.UserControl>).  
  
 По своей природе <xref:System.Windows.Interop.HwndHost> имеет определенные ограничения, которые влияют на то, как ведущие приложения могут их использовать. Тем не менее [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет <xref:System.Windows.Interop.HwndHost> несколькими возможностями для сценариев надстройки. Эти преимущества и ограничения описаны ниже.  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>Преимущества надстройки WPF  
 Поскольку [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] надстройки [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] отображаются из ведущих приложений, используя внутренний класс, производный от <xref:System.Windows.Interop.HwndHost>, в которых [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] ограниченные возможности <xref:System.Windows.Interop.HwndHost> по отношению к [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] службы, такие как макет, подготовки к просмотру, привязка данных, стили, шаблоны и ресурсы. Тем не менее [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] дополняет свой внутренний <xref:System.Windows.Interop.HwndHost> подкласс с дополнительными возможностями, которые включают следующее:  
  
-   Переход между [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущего приложения и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки. Обратите внимание, что «надстройка — это [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]"модель программирования требует адаптера стороне надстройки для переопределения <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> Включение переходов, надстройка полное доверие или с частичным доверием.  
  
-   Выполнение требований к поддержке специальных возможностей для [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстройки, отображаемых из ведущего приложения [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)].  
  
-   Поддержка безопасного выполнения приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в нескольких сценариях домена приложений.  
  
-   Предотвращение незаконного доступа к дескрипторам окон [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, когда надстройки выполняются в режиме изоляции безопасности (то есть находятся в частично доверенной изолированной среде безопасности). Вызов <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> гарантирует безопасности:  
  
    -   Для «Надстройка возвращает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]"модель программирования, единственный способ передачи дескриптор окна для добавления в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] через изоляцию границ заключается в вызове <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    -   Для «надстройка — это [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]"программирования модели, переопределение <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> для адаптера на стороне надстройки, а вызов метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (как показано в предыдущих примерах) является обязательным, как при вызове адаптера на стороне надстройки `QueryContract` реализации из адаптера узла.  
  
-   Предоставление защиты выполнения нескольких доменов приложений. Из-за ограничений, связанных с доменами приложений, необработанные исключения, которые появляются в доменах приложений надстроек, вызывают сбой всего приложения, несмотря на наличие границы изоляции. Тем не менее [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и модель [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] надстройки предоставляют простой способ решения этой проблемы и повышают стабильность работы приложения. Объект [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] надстройки, отображающий [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] создает <xref:System.Windows.Threading.Dispatcher> потока, который выполняется в домене приложения, если хост-приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] приложения. Можно обнаружить все необработанные исключения, возникающие в домене приложения, обрабатывая <xref:System.Windows.Threading.Dispatcher.UnhandledException> событие [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] надстройки <xref:System.Windows.Threading.Dispatcher>. Вы можете получить <xref:System.Windows.Threading.Dispatcher> из <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> свойство.  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>Ограничения надстройки WPF  
 Кроме преимуществ, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] добавляет к поведению по умолчанию, предоставляемые <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>и дескрипторами окна, существуют также ограничения для надстройки [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] , которые отображаются из ведущих приложений:  
  
-   [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстройки, отображаемый из ведущего приложения, не учитывает поведение ведущего приложения при обрезке.  
  
-   Концепция *свободного пространства* в сценариях взаимодействия также применяется к надстройкам (см. [Общие сведения о технологических областях](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)).  
  
-   Службы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущих приложений, такие как наследование ресурса, привязка данных и команды, недоступны автоматически для [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстройки. Чтобы предоставить эти службы для надстройки, необходимо обновить конвейер.  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки нельзя поворачивать, масштабировать, отклонять или преобразовывать иным образом (см. [Общие сведения о преобразованиях](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)).  
  
-   Содержимое внутри надстройки [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] , визуализируется рисования из <xref:System.Drawing> пространство имен может включать альфа-смешение. Однако как [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, так и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущего приложения, которое его содержит, должны быть полностью непрозрачными. Другими словами, для их свойства `Opacity` должно быть установлено значение 1.  
  
-   Если <xref:System.Windows.Window.AllowsTransparency%2A> свойства окна в ведущем приложении, содержащий add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] имеет значение `true`, надстройка невидим. Это верно даже в том случае, если [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки полностью непрозрачно (то есть свойство `Opacity` имеет значение 1).  
  
-   [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки должно появляться поверх других элементов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в том же окне верхнего уровня.  
  
-   Часть надстройки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] может осуществляться с помощью <xref:System.Windows.Media.VisualBrush>. Вместо этого надстройка может сделать моментальный снимок созданного [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], чтобы создать растровое изображение, которое может быть передано ведущему приложению с использованием методов, определенных в контракте.  
  
-   Невозможно воспроизвести файлы мультимедиа из <xref:System.Windows.Controls.MediaElement> в надстройке [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   События мыши, созданные для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, не получаются и не вызываются ведущим приложением, а свойство `IsMouseOver` для ведущего приложения [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] имеет значение `false`.  
  
-   Когда фокус смещается между элементами управления в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, `GotFocus` и `LostFocus` события не получаются и не вызываются ведущим приложением.  
  
-   Часть ведущего приложения, содержащая [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, выглядит пустой при печати.  
  
-   Все диспетчеры (см. <xref:System.Windows.Threading.Dispatcher>) созданные надстройки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] должна быть завершена вручную перед надстройки владельца выгрузкой Если ведущее приложение продолжает выполнение. Контракт может реализовывать методы, которые позволяют ведущему приложению сигнализировать надстройке до того, как надстройка будет выгружена, тем самым позволяя [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки закрыть свои диспетчеры.  
  
-   Если надстройка [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] — <xref:System.Windows.Controls.InkCanvas> или содержит <xref:System.Windows.Controls.InkCanvas>, не удается выгрузить надстройку.  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>Оптимизация производительности  
 По умолчанию при использовании нескольких доменов приложений различные сборки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], необходимые для каждого приложения, загружаются в домен приложения. В результате время, необходимое для создания новых доменов приложений и запуска приложений в них, может повлиять на производительность. Однако [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] предоставляет способ сократить время запуска, передавая приложениям инструкции по совместному использованию сборок всеми доменами приложений, если они уже загружены. Это делается с помощью <xref:System.LoaderOptimizationAttribute> атрибут, который необходимо применить к методу точки входа (`Main`). В данном случае необходимо использовать только код для реализации определения приложения (см. [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md)).  
  
## <a name="see-also"></a>См. также  
 <xref:System.LoaderOptimizationAttribute>  
 [Надстройки и расширения среды](../../../../docs/framework/add-ins/index.md)  
 [Домены приложений](../../../../docs/framework/app-domains/application-domains.md)  
 [Обзор удаленного взаимодействия .NET framework](http://msdn.microsoft.com/library/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)  
 [Создание удаленных объектов](http://msdn.microsoft.com/library/01197253-3f13-43b7-894d-9683e431192a)  
 [Разделы практического руководства](../../../../docs/framework/wpf/app-development/how-to-topics.md)
