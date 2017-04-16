---
title: "Разработка приложений | Microsoft Docs"
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
  - "разработка приложений [WPF], сведения"
  - "WPF, о разработке приложений"
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# Разработка приложений
<a name="introduction"></a> [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] — это платформа представления, которую можно использовать для разработки приложений следующих типов.  
  
-   Автономные приложения \(традиционные приложения [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], построенные как исполняемые сборки, которые устанавливаются и запускаются с клиентского компьютера\).  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] \(приложения, состоящие из страниц навигации, построенных как исполняемые сборки, которые размещаются в веб\-браузерах, таких как [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] и Mozilla Firefox\).  
  
-   Пользовательские библиотеки элементов управления \(неисполняемые сборки, содержащие многократно используемые элементы управления\).  
  
-   Библиотеки классов \(неисполняемые сборки, содержащие многократно используемые классы\).  
  
> [!NOTE]
>  Крайне нежелательно использовать типы WPF в службе Windows.  Если попытаться использовать эти средства в службе Windows, они могут работать не так, как ожидается.  
  
 Для построения этого набора приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] реализует множество служб.  Этот раздел предоставляет обзор этих служб и место, где искать дополнительные сведения.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Application_Management"></a>   
## Управление приложениями  
 Исполняемые приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] часто требуют основной набор функциональных возможностей, включающий следующее.  
  
-   Создание и управление общей инфраструктурой приложений \(включая создание метода точки входа и цикл обработки сообщений Windows для получения системных и входящих сообщений\).  
  
-   Отслеживание и взаимодействие со временем жизни приложения.  
  
-   Извлечение и обработка параметров командной строки.  
  
-   Совместное использование свойств области приложения и ресурсов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   Обнаружение и обработка необработанных исключений.  
  
-   Возврат кодов завершения.  
  
-   Управление окнами в автономных приложениях.  
  
-   Отслеживание переходов в [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и в отдельных приложениях с окнами переходов и фреймами.  
  
 Эти возможности реализуются с помощью класса <xref:System.Windows.Application>, который добавляется в приложения с использованием *определения приложения*.  
  
 Дополнительные сведения см. в разделе [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## Ресурсы, Содержимое и Файлы данных WPF\-приложения  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет основную поддержку внедренных ресурсов в [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], обеспечивая поддержку трех типов неисполняемых файлов данных: ресурсов, содержимого и данных. Дополнительные сведения см. в разделе [Ресурсы, Содержимое и Файлы данных WPF\-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Ключевым компонентом поддержки неисполняемых файлов данных WPF является возможность их идентификации и загрузки с помощью уникального [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Дополнительные сведения см. в разделе [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## Окна и диалоговые окна  
 Пользователи взаимодействуют с отдельными [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-приложениями при помощи окон.  Предназначением окна является размещение содержимого приложения и предоставляют функциональных возможностей приложения, которые обычно позволяют пользователям взаимодействовать с содержимым.  В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] окна инкапсулируются классом <xref:System.Windows.Window>, который поддерживает следующее.  
  
-   Создание и отображение окон.  
  
-   Установка отношений владельца\/собственного окна.  
  
-   Настройка внешнего вида окна \(например, размер, расположение, значки, текст заголовка, границы\).  
  
-   Отслеживание и взаимодействие со временем жизни окна.  
  
 Дополнительные сведения см. в разделе [Общие сведения об окнах WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
 <xref:System.Windows.Window> поддерживает возможность создания особого типа окна, называемого диалоговым окном.  Могут быть созданы модальные и немодальные типы диалоговых окон.  
  
 Для удобства и получения выгоды от повторного использования и согласованного пользовательского интерфейса между приложениями [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет три общих диалоговых окна [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)]: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog> и <xref:System.Windows.Controls.PrintDialog>.  
  
 Окно сообщения представляет собой особый тип диалогового окна для отображения важной текстовой информации для пользователей и для простых ответов \(да\/нет\/ОК\/Отмена\) на вопросы.  Для создания и отображения окон сообщений, вы используете класс <xref:System.Windows.MessageBox>.  
  
 Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
<a name="Navigation"></a>   
## Навигация  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддерживает навигацию в стиле Web с помощью страниц \(<xref:System.Windows.Controls.Page>\) и гиперссылок \(<xref:System.Windows.Documents.Hyperlink>\).  Навигация может быть реализована разнообразными способами, включая следующее.  
  
-   Автономные страницы, размещенные в веб\-браузере.  
  
-   Страницы, скомпилированные в приложение [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], которое размещается в веб\-браузере.  
  
-   Страницы компилируются в автономное приложение и размещаются с помощью окна навигации \(<xref:System.Windows.Navigation.NavigationWindow>\).  
  
-   Страницы, размещенные с помощью фрейма \(<xref:System.Windows.Controls.Frame>\), который может размещаться в отдельной странице, или странице которая компилируется либо в [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], либо в автономное приложение.  
  
 Для облегчения навигации [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] реализует следующее:  
  
-   <xref:System.Windows.Navigation.NavigationService>, совместно используемый обработчик переходов для обработки запросов перемещения, которые используются <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow> и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] для поддержки переходов внутри приложения.  
  
-   Методы навигации для инициирования навигации.  
  
-   События переходов для отслеживания и взаимодействия со временем жизни навигации.  
  
-   Запоминание переходов назад и вперед, используя журнал, который может быть проверен и обработан.  
  
 Сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] также поддерживает специальный тип навигации, известный как структурированная навигация.  Структурированная навигация может быть использована для вызова одной или нескольких страниц, которые возвращают данные структурированным и предсказуемым способом, согласованным с вызывающими функциями.  Эта возможность зависит от класса <xref:System.Windows.Navigation.PageFunction%601>, который описан далее в разделе [Общие сведения о структурной навигации](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md).  <xref:System.Windows.Navigation.PageFunction%601> также служит для упрощения создания сложных топологий переходов, которые описаны в разделе [Общие сведения о топологии переходов](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md).  
  
<a name="Hosting"></a>   
## Размещение  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] может размещаться в браузере [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] или Firefox.  Каждая модель размещения имеет свой собственный набор разрешений и ограничений, которые рассматриваются в разделе [Размещение](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md).  
  
<a name="Build_and_Deploy"></a>   
## Построение и Развертывание  
 Хотя простые приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] могут быть построены из командной строки с помощью компиляторов командной строки, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] интегрируется с [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] для обеспечения дополнительной поддержки, которая упрощает процесс разработки и построения.  Дополнительные сведения см. в разделе [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
 В зависимости от типа приложения вы можете выбрать один или несколько параметров развертывания.  Дополнительные сведения см. в разделе [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
<a name="related_topics"></a>   
## Связанные разделы  
  
|Заголовок|Описание|  
|---------------|--------------|  
|[Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md)|Общие сведения о классе <xref:System.Windows.Application>, включая управление временем существования приложения, окнами, ресурсами приложений и навигацией.|  
|[Windows в WPF](../../../../docs/framework/wpf/app-development/windows-in-wpf-applications.md)|Сведения об управлении окнами в приложении, включая способы использования класса <xref:System.Windows.Window> и диалоговых окон.|  
|[Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md)|Общие сведения об управлении навигацией по страницам приложения.|  
|[Размещение](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md)|Общие сведения о [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].|  
|[Построение и Развертывание](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md)|Описание процесса построения и развертывания приложения WPF.|  
|[Введение в WPF в Visual Studio 2015](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)|Описание основных возможностей WPF.|  
|[Пошаговое руководство. Начало работы с WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|Пошаговое руководство, в котором демонстрируется создание приложения WPF с использованием навигации по страницам, макета, элементов управления, изображений, стилей и привязок.|