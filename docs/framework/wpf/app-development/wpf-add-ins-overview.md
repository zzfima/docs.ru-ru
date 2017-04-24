---
title: "Общие сведения о надстройках WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "модель надстроек платформы .NET Framework [WPF]"
  - "надстройки [WPF], архитектура"
  - "надстройки [WPF], преимущества"
  - "надстройки [WPF], ограничения"
  - "надстройки [WPF], производительность"
  - "надстройки [WPF], пользовательский интерфейс"
  - "надстройки и пользовательский интерфейс [WPF]"
  - "надстройки и приложения браузера XAML [WPF]"
  - "общие сведения о надстройках [WPF]"
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 35
---
# Общие сведения о надстройках WPF
<a name="Introduction"></a> Компонент [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] включает модель надстройки, которою разработчики могут использовать для создания приложений, поддерживающих расширяемость надстроек.  Эта модель надстройки позволяет интегрировать надстройки и расширять функциональные возможности приложения.  В некоторых скриптах приложения также должны отображать несколько пользовательских интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], предоставляемых надстройками.  В этом разделе рассматривается порядок добавления модели надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] приложением [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для поддержки таких сценариев, а также лежащая в основе этого порядка архитектура, ее преимущества и ограничения.  
  
   
  
<a name="Requirements"></a>   
## Предварительные требования  
 Знакомство с моделью надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] является обязательным.  Дополнительные сведения см. в разделе [Надстройки и расширения среды](../../../../ml/index.xml) \("Общие сведения о надстройках"\).  
  
<a name="AddInsOverview"></a>   
## Общие сведения о надстройках  
 Чтобы избежать сложности перекомпиляции и повторного развертывания приложения для внедрения новых функциональный возможностей, в приложениях реализуются механизмы расширяемости, позволяющие разработчикам \(основным и сторонним производителям\) создавать приложения, поддерживающие интеграцию с предыдущим приложением.  Наиболее распространенным способом поддержки этого типа расширяемости является внутреннее использование надстроек \(также называемых встроенными компонентами или подключаемыми модулями\).  Ниже приведены примеры реальных приложений, которые обеспечивают расширяемость с помощью надстроек.  
  
-   Встроенные компоненты Internet Explorer.  
  
-   Подключаемые модули проигрывателя Windows Media.  
  
-   Надстройки Visual Studio.  
  
 Например, модель надстройки проигрывателя Windows Media позволяет сторонним разработчикам реализовать подключаемые модули, которые различными способами расширяют проигрыватель, включая создание декодеров и кодировщиков для форматов мультимедиа, изначально не поддерживаемых проигрывателем Windows Media \(например DVD, MP3\), звуковые эффекты и обложки.  Каждая модель надстройки встраивается для предоставления функциональных возможностей, уникальных для приложения, хотя существует несколько элементов и поведений, общих для всех моделей надстроек.  
  
 К основным трем элементам типичных решений расширяемости надстроек относятся *контракты*, *надстройки* и *ведущие приложения*.  Контракты определяют порядок интеграции надстройки с ведущим приложением следующими двумя способами.  
  
-   Надстройки интегрируются с функциональными возможностями, реализуемыми ведущими приложениями.  
  
-   Ведущие приложения предоставляют функциональные возможности для интеграции с надстройками.  
  
 Чтобы использовать надстройки, ведущие приложения должны найти их и загрузить во время выполнения.  Поэтому приложения, поддерживающие надстройки, имеют следующие дополнительные обязанности.  
  
-   **Обнаружение**: поиск надстроек, которые соответствуют контрактам, поддерживаемым приложениями.  
  
-   **активация** — загрузка, запуск и установка соединения с надстройками;  
  
-   **изоляция** — использование доменов или процессов приложений для установления границ изоляции, защищающих приложения от потенциальных проблем безопасности и неполадок выполнения в надстройках;  
  
-   **связь** — разрешение надстройкам и ведущим приложениям взаимодействовать друг с другом через границы изоляции, путем вызова методов и передачи данных;  
  
-   **управление временем существования** — загрузка и выгрузка доменов и процессов приложений ясным, прогнозируемым способом \(см. раздел [Домены приложений](../../../../docs/framework/app-domains/application-domains.md)\);  
  
-   **Управление версиями**: проверка того, что ведущие приложения и надстройки могут взаимодействовать после их обновления.  
  
 В конечно счете, разработка надежной модели надстройки является нетривиальный задачей.  По этой причине компонент [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] обеспечивает инфраструктуру для построения моделей надстроек.  
  
> [!NOTE]
>  Более подробные сведения о надстройках см. в разделе [Надстройки и расширения среды](../../../../ml/index.xml).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## Общие сведения о моделях надстроек платформы .NET Framework  
 Модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], находящаяся в пространстве имен <xref:System.AddIn>, содержит набор типов, которые предназначены для упрощения развития расширяемости надстроек.  Базовым модулем модели надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] является *контракт*, который определяет порядок взаимодействия ведущего приложения и надстройки.  Контракт отображается в ведущем приложении с помощью отдельного *представления* контракта для ведущего представления.  Таким же образом, отдельное *представление* контракта для надстройки отображается в надстройке.  Для связи между ведущим приложением и надстройкой и соответствующими представлениями контракта используется *адаптер*.  Контракты, представления и адаптеры относятся к сегментам, и набор связанных сегментов составляет *конвейер*.  Модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] использует конвейеры как основу для поддержки обнаружения, активации, изоляции безопасности, изоляции выполнения \(с помощью доменов приложений и процессов\), связи, управления временем жизни и управления версиями.  
  
 Суммарно эта поддержка позволяет разработчикам создавать надстройки, интегрируемые с функциональными возможностями ведущего приложения.  Однако в некоторых скриптах ведущее приложение должно отображать несколько пользовательских интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], предоставляемых надстройками.  Поскольку каждая технология представления в компоненте [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] имеет собственную модель реализации [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], модель надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] не поддерживает какую\-либо отдельную технологию представления.  Вместо этого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет модель надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] посредством поддержки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для надстроек.  
  
<a name="WPFAddInModel"></a>   
## Надстройки WPF  
 Приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в сочетании с моделью надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] позволяет реализовать широкий ряд сценариев, требующих от ведущих приложений отобразить [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] из надстроек.  В частности, эти сценарии реализованы посредством [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] со следующими двумя моделями программирования.  
  
1.  **Надстройка возвращает пользовательский интерфейс**.  Надстройка возвращает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущему приложению с помощью вызова метода, как определено в контракте.  Этот скрипт используется в следующих случаях.  
  
    -   Внешний вид [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который возвращается надстройкой, зависит от данных или состояния во время выполнения, например — динамически созданные отчеты.  
  
    -   Компонент [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для служб, предоставляемых какой\-либо надстройкой, отличается от компонента [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущих приложений, которые могут использовать данную надстройку.  
  
    -   Надстройка, в первую очередь, выполняет службу для ведущего приложения и создает для него отчет о состоянии с помощью [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
2.  **Надстройка является пользовательским интерфейсом**.  Надстройка является пользовательским интерфейсом [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], как определено в контракте.  Этот скрипт используется в следующих случаях.  
  
    -   Надстройка не предоставляет служб, кроме тех, которые отображаются, такие как объявление.  
  
    -   Пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] для служб, предоставляемых надстройкой, является общим для всех ведущих приложений, которые могут использовать эту надстройку, например калькулятор или палитра цветов.  
  
 Эти сценарии требуют, чтобы объекты [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] могли передаваться между ведущими приложениями и доменами приложений надстроек.  Поскольку модель надстроек [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] использует удаленное взаимодействие между доменами приложений, передаваемые между ними объекты должны поддерживать удаленный режим работы.  
  
 Удаленный объект является экземпляром класса, который относится к следующим процессам.  
  
-   Является производным класса <xref:System.MarshalByRefObject>.  
  
-   Реализует интерфейс <xref:System.Runtime.Serialization.ISerializable>.  
  
-   К нему применяется атрибут <xref:System.SerializableAttribute>.  
  
> [!NOTE]
>  Дополнительные сведения о создании удаленных объектов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] см. в разделе [Making Objects Remotable](http://msdn.microsoft.com/ru-ru/01197253-3f13-43b7-894d-9683e431192a).  
  
 Типы пользовательского интерфейса [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] не поддерживают удаленное взаимодействие.  Чтобы решить проблему, приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет модель надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], чтобы включить пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], созданный надстройками для отображения из ведущих приложений.  Эта поддержка обеспечивается приложением [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] посредством двух типов: интерфейсом <xref:System.AddIn.Contract.INativeHandleContract> и двумя статическими методами, реализованными классом <xref:System.AddIn.Pipeline.FrameworkElementAdapters>: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> и <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  На высоком уровне эти типы и методы используются следующим образом.  
  
1.  Приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] требует, чтобы несколько пользовательских интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], предоставляемых надстройками, были прямо или косвенно производными классами таких объектов <xref:System.Windows.FrameworkElement>, как фигуры, элементы управления, пользовательские элементы управления, панели макетов и страницы.  
  
2.  Везде, где контракт объявляет, что пользовательский интерфейс будет передан между надстройкой и ведущим приложением, он должен быть объявлен как объект <xref:System.AddIn.Contract.INativeHandleContract> \(не объект <xref:System.Windows.FrameworkElement>\); объект <xref:System.AddIn.Contract.INativeHandleContract> является удаленным представлением пользовательского интерфейса [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, который может быть передан через границы изоляции.  
  
3.  Перед передачей из домена приложения надстройки объект <xref:System.Windows.FrameworkElement> упаковывается как <xref:System.AddIn.Contract.INativeHandleContract> путем вызова метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  После передачи в домен ведущего приложения объект <xref:System.AddIn.Contract.INativeHandleContract> должен быть распакован как <xref:System.Windows.FrameworkElement> путем вызова метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Порядок использования объекта <xref:System.AddIn.Contract.INativeHandleContract> и метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> и <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> зависит от конкретного скрипта.  В следующих разделах содержатся сведения для каждой модели программирования.  
  
<a name="ReturnUIFromAddInContract"></a>   
## Надстройка возвращает интерфейс пользователя  
 Чтобы надстройка возвратила [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущему приложению, требуются следующие условия.  
  
1.  Ведущее приложение, надстройка и конвейер должны быть созданы, как описано в документации [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [Надстройки и расширения среды](../../../../ml/index.xml).  
  
2.  Контракт должен реализовывать объект <xref:System.AddIn.Contract.IContract>, и чтобы вернуть [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], контракт должен объявить метод с возвращаемым значением типа<xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  Пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который передается между надстройкой и ведущим приложением, должен быть прямо или косвенно производным объекта <xref:System.Windows.FrameworkElement>.  
  
4.  Пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], возвращаемый надстройкой, перед пересечением границы изоляции должен быть преобразован из объекта <xref:System.Windows.FrameworkElement> в объект <xref:System.AddIn.Contract.INativeHandleContract>.  
  
5.  После пересечения границы изоляции возвращаемый пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] должен быть преобразован из объекта <xref:System.AddIn.Contract.INativeHandleContract> в объект <xref:System.Windows.FrameworkElement>.  
  
6.  Ведущее приложение отображает возвращаемый объект <xref:System.Windows.FrameworkElement>.  
  
 Пример, демонстрирующий реализацию надстройки, которая возвращает пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], см. в разделе [Создание надстройки, возвращающей пользовательский интерфейс](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## Надстройка является интерфейсом пользователя  
 Если надстройкой является [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], необходимы следующие условия.  
  
1.  Ведущее приложение, надстройка и конвейер должны быть созданы, как описано в документации [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] [Надстройки и расширения среды](../../../../ml/index.xml).  
  
2.  Интерфейс контракта для надстройки должен реализовывать <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  Надстройка, которая передается в ведущее приложение, должна быть прямо или косвенно производной объекта <xref:System.Windows.FrameworkElement>.  
  
4.  Перед пересечением границы изоляции надстройка должна быть преобразована из объекта <xref:System.Windows.FrameworkElement> в объект <xref:System.AddIn.Contract.INativeHandleContract>.  
  
5.  После пересечения границы изоляции надстройка должна быть преобразована из объекта <xref:System.AddIn.Contract.INativeHandleContract> в объект <xref:System.Windows.FrameworkElement>.  
  
6.  Ведущее приложение отображает возвращаемый объект <xref:System.Windows.FrameworkElement>.  
  
 Пример, демонстрирующий реализацию надстройки, которая является [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], см. в разделе [Создание надстройки, являющейся пользовательским интерфейсом](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## Возвращение нескольких пользовательских интерфейсов из надстройки  
 Надстройки часто предоставляют несколько пользовательских интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] для отображения в ведущих приложениях.  Например, рассмотрим надстройку, являющуюся пользовательским интерфейсом [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], которая предоставляет сведения о состоянии ведущему приложению также под именем [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Подобная надстройка может быть реализована путем сочетания технологии их обеих моделей [Надстройка возвращает пользовательский интерфейс](#ReturnUIFromAddInContract) и [Надстройка является пользовательским интерфейсом](#AddInIsAUI).  
  
<a name="AddInsAndXBAPs"></a>   
## Надстройки и приложения браузера XAML  
 До сих пор в примерах рассматривалось автономно установленное ведущее приложение.  Однако надстройки также может размещать приложение [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] со следующими дополнительными требованиями к построению и реализации.  
  
-   Манифест приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] должен быть настроен отдельно для загрузки конвейера \(папок и сборок\) и сборки надстройки в кэш приложения [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] на клиентском компьютере, в той же папке, в которой находится приложение [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   Код [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] для обнаружения и загрузки надстроек должен использовать для приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] кэш приложения [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] в качестве местоположения конвейера и надстройки.  
  
-   Приложение [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] должно загружать надстройку в отдельный контекст безопасности, если надстройка ссылается на свободные файлы, которые находятся на узле источника; при размещении приложением [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] надстройки могут только ссылаться на свободные файлы, находящиеся на узле источника ведущего приложения.  
  
 Эти задачи описаны в следующих подразделах.  
  
### Настройка конвейера и надстройки для развертывания ClickOnce  
 Приложения [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] загружаются в безопасную папку и запускаются из нее в кэше развертывания [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)].  Для размещения надстройки приложением [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] сборка конвейера и надстройки должна также загружаться в безопасную папку.  Для этого необходимо настроить манифест приложения, чтобы включить сборку конвейера и надстройки для загрузки.  Наиболее просто это можно сделать в приложении [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], хотя сборка конвейера и надстройки должна находиться в корневой папке проекта ведущего приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], чтобы приложение [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] могло обнаружить сборки конвейера.  
  
 Поэтому первым шагом является построение сборки конвейера и надстройки в корне проекта [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] с помощью задания вывода построения каждого проекта сборки конвейера и надстройки.  В следующей таблице показаны пути вывода построения для проектов сборки конвейера и проекта сборки надстройки, которые находятся в том же решении и корневой папке, что и проект ведущего приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
 Таблица 1. Пути вывода построения для сборок конвейера, размещаемых приложением XBAP  
  
|Проект сборки конвейера|Выходной путь построения|  
|-----------------------------|------------------------------|  
|Контракт|`..  \HostXBAP\Contracts\`|  
|Представление надстройки|`..  \HostXBAP\AddInViews\`|  
|Адаптер на стороне надстройки|`..  \HostXBAP\AddInSideAdapters\`|  
|Адаптер на стороне узла|`..  \HostXBAP\HostSideAdapters\`|  
|Надстройка|`..  \HostXBAP\AddIns\WPFAddIn1`|  
  
 Следующим шагом является определение сборок конвейеров и сборки надстройки в качестве файлов содержимого [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] в приложении [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] посредством следующих действий.  
  
1.  Включите сборку конвейера и надстройки в проекте — для этого щелкните правой кнопкой каждую папку конвейера в обозревателе решений и выберите **Включить в проект**.  
  
2.  В окне **Свойства** установите для параметра **Действие при построении** каждой сборки конвейера и надстройки значение **Содержимое**.  
  
 Заключительным шагом является настройка манифеста приложения, чтобы включить файлы сборки конвейера и файл сборки надстройки для загрузки.  Файлы должны находиться в папках в корневом каталоге в кэше [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], который занимает приложение [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Настройку в приложении [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] можно выполнить посредством следующих действий.  
  
1.  Щелкните правой кнопкой мыши проект [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], выберите **Свойства**, **Публикация** и затем — **Файлы приложений**.  
  
2.  В диалоговом окне **Файлы приложений** установите для параметра **Состояние публикации** каждого конвейера и библиотеки DLL надстройки значение **Включить \(Авто\)** и для параметра **Группа загрузки** каждого конвейера и библиотеки DLL — значение **\(обязательный\)**.  
  
### Использование конвейера и надстройки из базовой папки приложения  
 Если конвейер и надстройка настроены для развертывания [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], они загружаются в ту же папку кэша [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], что и [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Для того чтобы использовать конвейер и надстройку из приложения [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], код [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] должен получить их из базовой папки приложения.  Различные типы и члены модели надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] предоставляют отдельную поддержку этого скрипта для использования конвейеров и надстроек.  Сначала путь определяется значением перечисления <xref:System.AddIn.Hosting.PipelineStoreLocation>.  Используйте это значение с перегрузками соответствующих членов надстройки для использования конвейеров, которые включают следующие члены:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
-   [AddInStore.FindAddIns\(Type, PipelineStoreLocation, String\<xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=fullName>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
### Доступ к узлу источника  
 Чтобы убедиться, что надстройка может ссылаться на файлы узла источника, она должна быть загружена с изоляцией безопасности, которая соответствует ведущему приложению.  Этот уровень безопасности определяется значением перечисления <xref:System.AddIn.Hosting.AddInSecurityLevel?displayProperty=fullName> и передается методу <xref:System.AddIn.Hosting.AddInToken.Activate%2A> при активации надстройки.  
  
<a name="WPFAddInModelArchitecture"></a>   
## Архитектура надстройки WPF  
 Как видно, на самом высоком уровне [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет надстройкам [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] реализовать несколько пользовательских интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] \(которые являются прямо или косвенно производными от объекта <xref:System.Windows.FrameworkElement>\) посредством объекта <xref:System.AddIn.Contract.INativeHandleContract> и методов <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> и <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  В результате, ведущее приложение возвращает объект <xref:System.Windows.FrameworkElement>, который отображается из пользовательского интерфейса [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в ведущем приложении.  
  
 Для простых скриптов надстройки [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] эти сведения достаточны для требований разработчика.  Что касается более сложных сценариев, в частности, тех, в которых предпринимается попытка использовать дополнительные службы [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], например макет, ресурсы и привязку данных, для понимания их преимуществ и ограничений необходимы более подробные сведения о том, как [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет модель надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] с поддержкой [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 В действительности приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] не передает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] из надстройки в ведущее приложение; вместо этого [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] передает дескриптор окна Win32 для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], используя взаимодействие [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  По существу, когда [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] передается из надстройки в ведущее приложение, происходит следующее.  
  
-   На стороне надстройки приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] получает дескриптор окна для пользовательского интерфейса [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], который будет отображен ведущим приложением.  Дескриптор окна инкапсулируется внутренним классом [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], производным от объекта <xref:System.Windows.Interop.HwndSource>, и реализует объект <xref:System.AddIn.Contract.INativeHandleContract>.  Экземпляр этого класса возвращается с помощью метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> и маршалируется из домена приложения надстройки в домен ведущего приложения.  
  
-   На стороне ведущего приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] повторно пакетирует объект <xref:System.Windows.Interop.HwndSource> как внутренний класс [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], производный от объекта <xref:System.Windows.Interop.HwndHost>, и принимает класс <xref:System.AddIn.Contract.INativeHandleContract>.  Экземпляр этого класса возвращается в ведущее приложение посредством метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Класс <xref:System.Windows.Interop.HwndHost> существует для отображения нескольких пользовательских интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], определенных дескриптором окна, из интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Дополнительные сведения см. в разделе [Взаимодействие WPF и Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
 Таким образом, объект <xref:System.AddIn.Contract.INativeHandleContract> и методы <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> и <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> существуют для того, чтобы разрешить дескриптору окна передать пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] из надстройки в ведущее приложение, где он инкапсулируется объектом <xref:System.Windows.Interop.HwndHost> и отображает пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущего приложения.  
  
> [!NOTE]
>  Поскольку ведущее приложение получает объект <xref:System.Windows.Interop.HwndHost>, оно не может объект, возвращаемый с помощью метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, преобразовать в тип, в котором он реализуется надстройкой \(например, <xref:System.Windows.Controls.UserControl>\).  
  
 По своему типу, объект <xref:System.Windows.Interop.HwndHost> имеет определенные ограничения, которые влияют на то, как ведущие приложения могут их использовать.  Тем не менее приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет объект <xref:System.Windows.Interop.HwndHost> несколькими возможностями для сценариев надстройки.  Эти преимущества и ограничения описаны ниже.  
  
<a name="WPFAddInModelBenefits"></a>   
## Преимущества надстроек WPF  
 Поскольку пользовательские интерфейсы [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстройки [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] отображаются из ведущих приложений посредством внутреннего класса, производного от объекта <xref:System.Windows.Interop.HwndHost>, эти интерфейсы [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] ограничены возможностями объекта <xref:System.Windows.Interop.HwndHost> по отношению к таким службам [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], как макет, отрисовка, привязка данных, стили, шаблоны и ресурсы.  Однако [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] дополняет свой внутренний подкласс <xref:System.Windows.Interop.HwndHost> вспомогательными возможностями, включая следующие.  
  
-   Переход между компонентом [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущего приложения и компонентом [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки.  Обратите внимание, что для модели программирования "надстройка является [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]", требуется адаптер на стороне надстройки для переопределения метода <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A>, чтобы включить переход с учетом того, обладает ли надстройка полным или частичным доверием.  
  
-   Соблюдение требований к специальным возможностям для пользовательских интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстройки, отображаемых из [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] ведущего приложения.  
  
-   Включение приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] для безопасной работы в нескольких скриптах домена приложений.  
  
-   Предотвращение незаконного доступа к дескрипторам окна [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, когда надстройка запущена в режиме изоляции безопасности \(то есть в режиме безопасности с частичным доверием "песочница"\).  Вызов метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> гарантирует следующую безопасность.  
  
    -   Для модели программирования "надстройка возвращает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" единственным способом передачи дескриптора окна для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки через границу изоляции является вызов метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    -   Для модели программирования "надстройка является [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" требуется переопределение метода <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> в адаптере на стороне надстройки и вызов метода <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> \(как показано в предыдущем примере\), как при вызове реализации `QueryContract` адаптера на стороне надстройки из адаптера на стороне узла.  
  
-   Предоставление множественной защиты выполнения домена приложения.  Вследствие ограничений доменов приложений, необработанные исключения, которые создаются в надстройке доменов приложений, вызывают сбой всего приложения, даже если существует граница изоляции.  Однако [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и модель надстройки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] предоставляют простой способ для решения этой проблемы и повышения стабильности работы приложения.  Надстройка [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], которая отображает [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], создает объект <xref:System.Windows.Threading.Dispatcher> для потока, в котором выполняется домен приложения, если ведущим приложением является приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Можно обнаружить все необработанные исключения, возникающие в домене приложения, обрабатывая событие <xref:System.Windows.Threading.Dispatcher.UnhandledException> объекта <xref:System.Windows.Threading.Dispatcher> надстройки [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Объект <xref:System.Windows.Threading.Dispatcher> можно получить из свойства <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>.  
  
<a name="WPFAddInModelLimitations"></a>   
## Ограничения надстройки WPF  
 Кроме преимуществ, которые приложение [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] добавляет к поведению по умолчанию, обеспечиваемому объектами <xref:System.Windows.Interop.HwndSource> и <xref:System.Windows.Interop.HwndHost> и дескрипторами окна, имеются также следующие ограничения для нескольких интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстройки, которые отображаются из ведущих приложений.  
  
-   Несколько пользовательских интерфейсов [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстройки, отображаемых из ведущего приложения, не используют ограничения поведения ведущего приложения.  
  
-   Концепция *airspace* в скриптах взаимодействия также применяется к надстройкам \(см. [Общие сведения об областях применения технологий](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)\).  
  
-   Службы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущего приложения, такие как наследование ресурса, привязка данных и команды, недоступны автоматически для [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстроек.  Чтобы предоставить эти службы надстройке, необходимо обновить конвейер.  
  
-   Пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки не может быть повернут, масштабирован, наклонен или преобразован иным способом \(см. [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)\).  
  
-   Содержимое внутри [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] надстройки, которое отображено посредством рисования из пространства имен <xref:System.Drawing>, может включать альфа\-смешение.  Однако [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущего приложения, которое содержит этот интерфейс, должны быть на 100 % непрозрачны; другими словами, свойство `Opacity` обоих пользовательских интерфейсов должно иметь значение 1.  
  
-   Если свойство <xref:System.Windows.Window.AllowsTransparency%2A> окна в ведущем приложении, которое содержит [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, имеет значение `true`, надстройка будет невидимой.  Это верно даже в том случае, если пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки на 100% непрозрачен \(то есть свойство `Opacity` имеет значение 1\).  
  
-   Пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки должен отображаться в верхней части других элементов [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] в том же окне верхнего уровня.  
  
-   Никакая часть пользовательского интерфейса [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки не может быть отображена с посредством объекта <xref:System.Windows.Media.VisualBrush>.  Вместо этого, надстройка может сделать снимок сгенерированного [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], чтобы создать точечный рисунок, который может быть передан в ведущее приложение с помощью методов, определенных контрактом.  
  
-   Файлы мультимедиа невозможно воспроизвести из объекта <xref:System.Windows.Controls.MediaElement> в [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки.  
  
-   События мыши, созданные для [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, не могут быть получены или вызваны ведущим приложением, и свойство `IsMouseOver` для пользовательского интерфейса [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ведущего приложения имеет значение `false`.  
  
-   При перемещении фокуса между элементами управления в пользовательском интерфейсе [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки событий `GotFocus` и `LostFocus` не могут быть получены или вызваны ведущим приложением.  
  
-   Часть ведущего приложения, которая содержит [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, будет пустым пространством при печати.  
  
-   Все диспетчеры \(см. <xref:System.Windows.Threading.Dispatcher>\), созданные пользовательским интерфейсом [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки, должны быть вручную отключены, перед тем как надстройка владельца будет отправлена, если ведущее приложение продолжает выполняться.  Контракт может реализовать методы, позволяющие ведущему приложению оповещать надстройку, перед тем как надстройка будет отправлена, тем самым позволяя [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки завершить работу своих диспетчеров.  
  
-   Если пользовательский интерфейс [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] надстройки является объектом <xref:System.Windows.Controls.InkCanvas> или содержит объект <xref:System.Windows.Controls.InkCanvas>, разгрузка надстройки невозможна.  
  
<a name="PerformanceOptimization"></a>   
## Оптимизация производительности  
 По умолчанию, при использовании нескольких доменов приложений, все сборки [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], необходимые для каждого приложения, загружаются в домен приложения.  В результате, время, необходимое для создания новых доменов приложений и запуска в них приложений, может влиять на производительность.  Однако компонент [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] предоставляет способ сократить время запуска посредством инструктирования приложений для совместного использования сборок доменами приложений, если они уже загружены.  Это можно выполнить с помощью атрибута <xref:System.LoaderOptimizationAttribute>, который должен быть применен к методу точки входа \(`Main`\).  В этом случае, необходимо использовать только код для реализации определения приложения \(см. [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md)\).  
  
## См. также  
 <xref:System.LoaderOptimizationAttribute>   
 [Надстройки и расширения среды](../../../../ml/index.xml)   
 [Домены приложений](../../../../docs/framework/app-domains/application-domains.md)   
 [.NET Framework Remoting Overview](http://msdn.microsoft.com/ru-ru/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)   
 [Making Objects Remotable](http://msdn.microsoft.com/ru-ru/01197253-3f13-43b7-894d-9683e431192a)   
 [Практические руководства](../../../../docs/framework/wpf/app-development/how-to-topics.md)