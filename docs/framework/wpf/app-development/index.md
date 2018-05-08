---
title: Разработка приложений
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: 7ee6eeab32dc4221354714781598f2445c94e662
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="application-development"></a>Разработка приложений
<a name="introduction"></a> Windows Presentation Foundation (WPF) — это платформа представления, который может использоваться для разработки следующих типов приложений:  
  
-   автономные приложения (традиционные приложения [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)], созданные как исполняемые сборки, которые устанавливаются и запускаются с клиентского компьютера);  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] (приложения, состоящие из страниц навигации, созданных как исполняемые сборки, которые размещаются в веб-браузерах, таких как [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] и Mozilla Firefox);  
  
-   пользовательские библиотеки элементов управления (неисполняемые сборки, содержащие многократно используемые элементы управления);  
  
-   библиотеки классов (неисполняемые сборки, содержащие многократно используемые классы).  
  
> [!NOTE]
>  Использование типов WPF в службе Windows настоятельно не рекомендуется. При попытке использовать эти возможности в службе Windows они могут не работать должным образом.  
  
 Для создания этого набора приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] реализует множество служб. Этот раздел предоставляет обзор этих служб и место, где искать дополнительные сведения.  
  

  
<a name="Application_Management"></a>   
## <a name="application-management"></a>Управление приложениями  
 Исполняемые приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] часто требуют основной набор функциональных возможностей, включающий следующее:  
  
-   создание и управление общей инфраструктурой приложений (включая создание метода точки входа и цикл обработки сообщений Windows для получения системных и входящих сообщений);  
  
-   отслеживание и взаимодействие со временем существования приложения;  
  
-   извлечение и обработка параметров командной строки;  
  
-   совместное использование свойств области приложения и ресурсов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)];  
  
-   обнаружение и обработка необработанных исключений;  
  
-   возврат кодов завершения;  
  
-   управление окнами в автономных приложениях;  
  
-   отслеживание переходов в [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] и отдельных приложениях с окнами переходов и фреймами.  
  
 Эти возможности реализуются с помощью класса <xref:System.Windows.Application>, который добавляется в приложения с помощью *определения приложения*.  
  
 Дополнительные сведения см. в разделе [Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md).  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## <a name="wpf-application-resource-content-and-data-files"></a>Ресурсы, Содержимое и Файлы данных WPF-приложения  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] расширяет поддержку основных компонентов в Microsoft .NET Framework для внедренных ресурсов с поддержкой для трех типов данных не является исполняемым файлам: ресурсов, содержимого и данных. Дополнительные сведения см. в разделе [Файлы ресурсов, содержимого и данных WPF-приложения](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Ключевым компонентом поддержки неисполняемых файлов данных WPF является возможность их идентификации и загрузки с помощью уникального [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]. Дополнительные сведения см. в разделе [URI типа "pack" в WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## <a name="windows-and-dialog-boxes"></a>Окна и диалоговые окна  
 Пользователи взаимодействуют с автономными приложениями [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] через окна. Предназначением окна является размещение содержимого приложения и предоставление функциональных возможностей приложения, которые обычно позволяют пользователям взаимодействовать с содержимым. В [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] окна инкапсулируются классом <xref:System.Windows.Window>, который поддерживает следующие возможности:  
  
-   создание и отображение окон;  
  
-   установка отношений владельца/собственного окна;  
  
-   настройка внешнего вида окна (например, размер, расположение, значки, текст заголовка, границы);  
  
-   отслеживание и взаимодействие со временем существования окна.  
  
 Дополнительные сведения см. в разделе [Общие сведения об окнах WPF](../../../../docs/framework/wpf/app-development/wpf-windows-overview.md).  
  
 <xref:System.Windows.Window> поддерживает возможность создать особый тип окна, известный как диалоговое окно. Можно создавать модальные и немодальные типы диалоговых окон.  
  
 Для удобства и преимущества возможность повторного использования и согласованного пользовательского интерфейса между приложениями [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет три общих диалоговых окон Windows: <xref:Microsoft.Win32.OpenFileDialog>, <xref:Microsoft.Win32.SaveFileDialog>, и <xref:System.Windows.Controls.PrintDialog>.  
  
 Окно сообщения представляет собой особый тип диалогового окна для отображения важной текстовой информации для пользователей и задания простых вопросов (да, нет, ОК, отмена). Класс <xref:System.Windows.MessageBox> используется для создания и отображения окон сообщений.  
  
 Дополнительные сведения см. в разделе [Общие сведения о диалоговых окнах](../../../../docs/framework/wpf/app-development/dialog-boxes-overview.md).  
  
<a name="Navigation"></a>   
## <a name="navigation"></a>Навигация  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддерживает навигацию в стиле веб, реализуя страницы (<xref:System.Windows.Controls.Page>) и гиперссылки (<xref:System.Windows.Documents.Hyperlink>). Навигация может быть реализована разнообразными способами, включая следующие:  
  
-   автономные страницы, размещенные в веб-браузере;  
  
-   страницы, скомпилированные в приложение [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], которое размещается в веб-браузере;  
  
-   страницы, скомпилированные в автономном приложении и размещенные в окне навигации (<xref:System.Windows.Navigation.NavigationWindow>);  
  
-   страницы, размещенные во фрейме (<xref:System.Windows.Controls.Frame>), который может размещаться на отдельной странице или на странице, скомпилированной в [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] или в автономное приложение.  
  
 Для облегчения навигации [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] реализует следующее:  
  
-   совместно используемый обработчик переходов <xref:System.Windows.Navigation.NavigationService> для обработки запросов перемещения, который используют <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Navigation.NavigationWindow> и [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] для поддержки переходов внутри приложения;  
  
-   методы навигации для инициирования навигации;  
  
-   события переходов для отслеживания и взаимодействия со временем существования перехода;  
  
-   запоминание переходов назад и вперед с использованием журнала, который может быть проверен и обработан.  
  
 Сведения см. в разделе [Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] также поддерживает специальный тип навигации, известный как структурированная навигация. Структурированная навигация может использоваться для вызова одной или нескольких страниц, которые возвращают данные структурированным и предсказуемым способом, согласованным с вызывающими функциями. Эта возможность зависит от класса <xref:System.Windows.Navigation.PageFunction%601>, который описан далее в разделе [Общие сведения о структурной навигации](../../../../docs/framework/wpf/app-development/structured-navigation-overview.md). <xref:System.Windows.Navigation.PageFunction%601> также позволяет упростить создание сложных топологий переходов, которые описаны в разделе [Общие сведения о топологии переходов](../../../../docs/framework/wpf/app-development/navigation-topologies-overview.md).  
  
<a name="Hosting"></a>   
## <a name="hosting"></a>Размещение  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] может размещаться в браузере [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] или Firefox. Каждая модель размещения имеет свой собственный набор разрешений и ограничений, которые рассматриваются в разделе [Размещение](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md).  
  
<a name="Build_and_Deploy"></a>   
## <a name="build-and-deploy"></a>Построение и Развертывание  
 Хотя простые приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] могут быть собраны из командной строки с помощью компиляторов командной строки, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] интегрируется с [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] для обеспечения дополнительной поддержки, которая упрощает процесс разработки и сборки. Дополнительные сведения см. в разделе [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
 В зависимости от типа приложения вы можете выбрать один или несколько параметров развертывания. Дополнительные сведения см. в разделе [Развертывание приложений WPF](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md).  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание|  
|-----------|-----------------|  
|[Общие сведения об управлении приложением](../../../../docs/framework/wpf/app-development/application-management-overview.md)|Общие сведения о классе <xref:System.Windows.Application>, включая управление временем существования приложения, окнами, ресурсами приложений и навигацией.|  
|[Windows в WPF](../../../../docs/framework/wpf/app-development/windows-in-wpf-applications.md)|Сведения об управлении окнами в приложении, включая способы использования класса <xref:System.Windows.Window> и диалоговых окон.|  
|[Общие сведения о переходах](../../../../docs/framework/wpf/app-development/navigation-overview.md)|Общие сведения об управлении навигацией по страницам приложения.|  
|[Размещение](../../../../docs/framework/wpf/app-development/hosting-wpf-applications.md)|Предоставляет общие сведения о [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].|  
|[Сборка и развертывание](../../../../docs/framework/wpf/app-development/building-and-deploying-wpf-applications.md)|Описание процесса сборки и развертывания приложения WPF.|  
|[Введение в WPF в Visual Studio](../../../../docs/framework/wpf/getting-started/introduction-to-wpf-in-vs.md)|Описание основных возможностей WPF.|  
|[Пошаговое руководство. Создание первого классического приложения WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)|Пошаговое руководство, в котором демонстрируется создание приложения WPF с использованием навигации по страницам, макета, элементов управления, изображений, стилей и привязок.|
