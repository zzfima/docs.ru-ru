---
title: "Развертывание приложений WPF | Microsoft Docs"
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
  - "развертывание [WPF], приложения"
  - "приложения WPF, развертывание"
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Развертывание приложений WPF
После построения приложений [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] необходимо их развернуть.  [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] поддерживают несколько технологий развертывания.  Технология развертывания, используемая для развертывания приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], зависит от типа приложения.  Данный раздел содержит краткое описание каждой из технологий развертывания и их использование в сочетании с требованиями развертывания для каждого типа приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
   
  
<a name="Deployment_Technologies"></a>   
## Технологии развертывания  
 В [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] имеется несколько технологий развертывания, том числе следующие.  
  
-   Развертывание XCopy.  
  
-   Развертывание [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].  
  
-   Развертывание [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)].  
  
<a name="XCopy_Deployment"></a>   
### Развертывание XСopy.  
 Развертывание XCopy означает использование программой командной строки XCopy для копирования файлов из одного расположения в другое.  Развертывание XСopy подходит для следующих случаев:  
  
-   Приложение является самодостаточным.  Для его запуска не требуется обновлять клиент.  
  
-   Файлы приложения должны быть перемещены из одного расположения в другое, например, из места построения \(локальный диск, общая папка [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] и т. д.\) в публикуемую директорию \(веб\-узел, общая папка [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] и т. д.\).  
  
-   Для приложения не требуется интегрирование в оболочку \(добавление значка в меню "Пуск", на рабочий стол и т. д.\).  
  
 Хотя технология Xcopy подходит для простых скриптов развертывания, ее недостаточно когда требуется выполнить более сложное развертывание.  В частности, при использовании XCopy могут возникать дополнительные затраты на создание, выполнение и поддержку скриптов для надежного управления развертыванием.  Кроме того XCopy не поддерживает управление версиями, удаление или откат.  
  
<a name="Windows_Installer"></a>   
### Установщик Windows  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] позволяет упаковывать приложения как самодостаточные исполняемые файлы, которые можно легко распространять среди клиентов и запускать.  Кроме того, [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] устанавливается вместе с [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и поддерживает интеграцию с рабочим столом, меню "Пуск" и элементом панели управления "Программы".  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] упрощает установку и удаление приложений, однако он не предоставляет средства, обеспечивающие обновление приложений до последней версии.  
  
 Дополнительные сведения о [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] см. в разделе [Windows Installer Deployment](http://msdn.microsoft.com/ru-ru/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
<a name="ClickOnce_Deployment"></a>   
### Развертывание ClickOnce  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] позволяет выполнять веб\-развертывание приложений, не являющихся веб\-приложениями. Приложения публикуются на веб\-серверах или файловых серверах и развертываются с них.  Развертывание [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] поддерживает не весь набор клиентских возможностей приложений, установленных с помощью [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Поддерживаются следующие возможности.  
  
-   Интеграция в меню "Пуск" и элемент панели управления "Программы".  
  
-   Управление версиями, откат и удаление.  
  
-   Режим интернет\-установки, в котором приложение всегда запускается из места развертывания.  
  
-   Автоматическое обновление при выходе новых версий.  
  
-   Регистрация расширений файлов.  
  
 Дополнительные сведения о [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] см. в разделе [Развертывание и безопасность технологии ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md).  
  
<a name="Deploying_WPF_Applications"></a>   
## Развертывание приложений WPF  
 Параметры развертывания для приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] зависят от типа приложения.  В отношении развертывания технология [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддерживает три основных типа приложений:  
  
-   Автономные приложения.  
  
-   Приложения, полностью состоящие из [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-кода разметки.  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
<a name="Deploying_Standalone_Applications"></a>   
### Развертывание автономных приложений  
 Автономные приложения развертываются с помощью [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] или [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].  В любом случае для запуска автономных приложений требуется полное доверие.  Полное доверие предоставляется приложениям, которые развертываются с помощью [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].  Автономные приложения, которые развертываются с помощью [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], не получают полного доверия автоматически.  Вместо этого [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] отображает диалоговое окно предупреждения безопасности, которое пользователь должен принять перед установкой автономного приложения.  Если предупреждение принято, автономное приложение устанавливается и ему предоставляется полное доверие.  В противном случае автономное приложение не устанавливается.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### Развертывание приложений XAML, содержащих только разметку  
 Страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащие только разметку, обычно публикуются на веб\-серверах, как и страницы [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], и их можно просматривать с помощью [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)].  Страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащие только разметку, запускаются в изолированной среде \(в режиме безопасности с частичным доверием\) с ограничениями, которые определяются набором разрешений зоны Интернета.  Это обеспечивает эквивалентный уровень безопасности для веб\-приложений [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  
  
 Дополнительные сведения о безопасности приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] см. в разделе [Безопасность](../../../../docs/framework/wpf/security-wpf.md).  
  
 Страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащие только разметку, можно устанавливать в локальной файловой системе с помощью XCopy или [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)].  Эти страницы можно просматривать с помощью [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] или [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
 Дополнительные сведения о XAML см. в разделе [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### Развертывание приложений браузера XAML  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] являются компилируемые приложения, для которых требуется развертывание следующих трех файлов:  
  
-   *имяПриложения*.exe: исполняемый файл приложения сборки.  
  
-   *имяПриложения*.xbap: манифест развертывания.  
  
-   *имяПриложения*.exe.manifest: манифест приложения.  
  
> [!NOTE]
>  Дополнительные сведения о манифестах развертывания и приложений см. в разделе [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
 Эти файлы создаются при построении [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения браузера WPF](http://msdn.microsoft.com/ru-ru/72ef4d90-e163-42a1-8df0-ea7ccfd1901f).  Подобно страницам [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащим только разметку, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] обычно публикуются на веб\-сервере и просматривается с помощью браузера [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)].  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] можно развертывать на клиентских компьютерах с помощью любых технологий развертывания.  Впрочем, рекомендуется использовать технологию [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)], поскольку она имеет следующие возможности.  
  
1.  Автоматическое обновление при публикации новой версии.  
  
2.  Повышенные привилегии при выполнении [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] в режиме полного доверия.  
  
 По умолчанию средство ClickOnce публикует файлы приложений с расширением DEPLOY.  Это поведение может привести к затруднениям, но его можно отключить.  Дополнительные сведения см. в разделе [Вопросы настройки сервера и клиента в развертываниях ClickOnce](../Topic/Server%20and%20Client%20Configuration%20Issues%20in%20ClickOnce%20Deployments.md).  
  
 Дополнительные сведения о развертывании [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] см. в разделе [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## Установка платформы .NET Framework  
 Для запуска приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] необходимо установить на клиент [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)].  [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] автоматически проверяет, установлена ли платформа [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] на клиентском компьютере при просмотре браузерных приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Если платформа [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] не установлена, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] предлагает пользователю установить ее.  
  
 Для проверки наличия [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] в браузере [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] содержится приложение загрузчика, который зарегистрирован в качестве резервного обработчика [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] для файлов содержимого со следующими расширениями: XAML, XPS, XBAP и APPLICATION.  Если при попытке открыть файлы данных типов платформа [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] не установлена на клиенте, приложение загрузчика запрашивает разрешение на ее установку.  Если разрешение не предоставляется, приложение [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] не устанавливается.  
  
 Если разрешение предоставлено, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] загружает и устанавливает [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] с помощью [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)].  После успешной установки [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] изначально запрошенный файл открывается в новом окне браузера.  
  
 Автоматическое обнаружение [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] доступно для клиентов [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)] и [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)], на которых установлен браузер [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] или более новый.  
  
 Дополнительные сведения см. в разделе [Развертывание .NET Framework и приложений](../../../../docs/framework/deployment/net-framework-and-applications.md).  
  
## См. также  
 [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [Безопасность](../../../../docs/framework/wpf/security-wpf.md)