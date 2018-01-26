---
title: "Развертывание приложений WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF applications [WPF], deployment
- deployment [WPF], applications
ms.assetid: 12cadca0-b32c-4064-9a56-e6a306dcc76d
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7cf0c5383728648d46427ce8fe2f5a97a736ab00
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="deploying-a-wpf-application-wpf"></a>Развертывание приложений WPF
После сборки приложений [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] их необходимо развернуть. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] поддерживают несколько технологий развертывания. Технология развертывания, используемая для развертывания приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], зависит от типа приложения. Этот раздел содержит краткое описание каждой из технологий развертывания и их использования в сочетании с требованиями к развертыванию для каждого типа приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
   
<a name="Deployment_Technologies"></a>   
## <a name="deployment-technologies"></a>Технологии развертывания  
 В [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] имеется несколько технологий развертывания, том числе следующие:  
  
-   развертывание с помощью XCopy;  
  
-   развертывание с помощью [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)];  
  
-   развертывание с помощью [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)].  
  
<a name="XCopy_Deployment"></a>   
### <a name="xcopy-deployment"></a>Развертывание с помощью XCopy  
 Развертывание с помощью XCopy означает использование программы командной строки XCopy для копирования файлов из одного расположения в другое. Развертывание с помощью XСopy подходит для указанных ниже случаев.  
  
-   Приложение является самодостаточным. Для его запуска не требуется обновлять клиент.  
  
-   Файлы приложения должны быть перемещены из одного расположения в другое, например из места сборки (локальный диск, общая папка [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] и т. д.) в место публикации (веб-сайт, общая папка [!INCLUDE[TLA2#tla_unc](../../../../includes/tla2sharptla-unc-md.md)] и т. д.).  
  
-   Для приложения не требуется интеграция в оболочку (добавление значка в меню "Пуск", на рабочий стол и т. д.).  
  
 Хотя технология XCopy подходит для простых сценариев развертывания, ее недостаточно, когда требуется выполнить более сложное развертывание. В частности, при использовании XCopy могут возникать дополнительные затраты на создание, выполнение и поддержку скриптов для надежного управления развертыванием. Кроме того, XCopy не поддерживает управление версиями, удаление или откат.  
  
<a name="Windows_Installer"></a>   
### <a name="windows-installer"></a>Установщик Windows  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] позволяет упаковывать приложения как самодостаточные исполняемые файлы, которые можно легко распространять на клиентах и запускать. Кроме того, [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] устанавливается вместе с [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] и поддерживает интеграцию с рабочим столом, меню "Пуск" и компонентом панели управления "Программы".  
  
 [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] упрощает установку и удаление приложений, однако не предоставляет средства, обеспечивающие обновление приложений до последней версии.  
  
 Дополнительные сведения о [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)] см. в разделе [Развертывание с помощью установщика Windows](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).  
  
<a name="ClickOnce_Deployment"></a>   
### <a name="clickonce-deployment"></a>развертывание ClickOnce  
 [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] позволяет выполнять веб-развертывание приложений, не являющихся веб-приложениями. Приложения публикуются на веб-серверах или файловых серверах и развертываются с них. Развертывание [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] поддерживает не весь набор клиентских возможностей приложений, установленных с помощью [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Поддерживаются следующие возможности:  
  
-   интеграция в меню "Пуск" и элемент панели управления "Программы";  
  
-   управление версиями, откат и удаление;  
  
-   режим интернет-установки, в котором приложение всегда запускается из места развертывания;  
  
-   автоматическое обновление при выходе новых версий;  
  
-   регистрация расширений файлов.  
  
 Дополнительные сведения о [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] см. в разделе [Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).  
  
<a name="Deploying_WPF_Applications"></a>   
## <a name="deploying-wpf-applications"></a>Развертывание приложений WPF  
 Параметры развертывания для приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] зависят от типа приложения. В плане развертывания технология [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] поддерживает три основных типа приложений:  
  
-   автономные приложения;  
  
-   приложения, полностью состоящие из кода [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] разметки;  
  
-   [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
<a name="Deploying_Standalone_Applications"></a>   
### <a name="deploying-standalone-applications"></a>Развертывание автономных приложений  
 Автономные приложения развертываются с помощью [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] или [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. В любом случае для запуска автономных приложений требуется полное доверие. Полное доверие автоматически предоставляется автономным приложениям, которые развертываются с помощью [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Автономные приложения, которые развертываются с помощью [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)], не получают полного доверия автоматически. Вместо этого [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] выводит диалоговое окно с предупреждением системы безопасности, которое пользователь должен подтвердить перед установкой автономного приложения. Если предупреждение принято, автономное приложение устанавливается и ему предоставляется полное доверие. В противном случае автономное приложение не устанавливается.  
  
<a name="Deploying_Markup_Only_XAML_Applications"></a>   
### <a name="deploying-markup-only-xaml-applications"></a>Развертывание приложений XAML, содержащих только разметку  
 Страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащие только разметку, обычно публикуются на веб-серверах, как и страницы [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)], и их можно просматривать с помощью [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)]. Страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащие только разметку, запускаются в изолированной среде (в режиме безопасности с частичным доверием) с ограничениями, которые определяются набором разрешений зоны Интернета. Это обеспечивает эквивалентный уровень безопасности для веб-приложений [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)].  
  
 Дополнительные сведения о безопасности приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] см. в разделе [Безопасность](../../../../docs/framework/wpf/security-wpf.md).  
  
 Страницы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащие только разметку, можно устанавливать в локальной файловой системе с помощью XCopy или [!INCLUDE[TLA2#tla_wininstall](../../../../includes/tla2sharptla-wininstall-md.md)]. Эти страницы можно просматривать с помощью [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)] или проводника [!INCLUDE[TLA2#tla_mswin](../../../../includes/tla2sharptla-mswin-md.md)].  
  
 Дополнительные сведения о XAML см. в разделе [Общие сведения о языке XAML](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md).  
  
<a name="Deploying_XAML_Browser_Applications"></a>   
### <a name="deploying-xaml-browser-applications"></a>Развертывание приложений браузера XAML  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] — это компилируемые приложения, для которых требуется развертывание следующих трех файлов:  
  
-   *имя_приложения*.exe — исполняемый файл приложения сборки;  
  
-   *имя_приложения*.xbap — манифест развертывания;  
  
-   *имя_приложения*.exe.manifest — манифест приложения.  
  
> [!NOTE]
>  Дополнительные сведения о манифестах развертывания и приложений см. в разделе [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
 Эти файлы создаются при сборке [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Дополнительные сведения см. в разделе [Практическое руководство. Создание нового проекта приложения обозревателя WPF](http://msdn.microsoft.com/library/72ef4d90-e163-42a1-8df0-ea7ccfd1901f). Подобно страницам [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], содержащим только разметку, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] обычно публикуются на веб-сервере и просматриваются с помощью браузера [!INCLUDE[TLA2#tla_iegeneric](../../../../includes/tla2sharptla-iegeneric-md.md)].  
  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] можно развертывать на клиентских компьютерах с помощью любых технологий развертывания. Однако рекомендуется использовать технологию [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)], так как она имеет следующие возможности:  
  
1.  автоматическое обновление при публикации новой версии;  
  
2.  повышенные привилегии при выполнении [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] в режиме полного доверия.  
  
 По умолчанию средство ClickOnce публикует файлы приложений с расширением DEPLOY. Это поведение может привести к затруднениям, но его можно отключить. Дополнительные сведения см. в разделе [Вопросы настройки сервера и клиента в развертываниях ClickOnce](/visualstudio/deployment/server-and-client-configuration-issues-in-clickonce-deployments).  
  
 Дополнительные сведения о развертывании [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] см. в разделе [Общие сведения о приложениях браузера WPF XAML](../../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
<a name="Installing__NET_Framework_3_0"></a>   
## <a name="installing-the-net-framework"></a>Установка .NET Framework  
 Для запуска приложения [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] необходимо установить на клиент платформу [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]. [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] автоматически проверяет, установлена ли платформа [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] на клиентском компьютере при просмотре браузерных приложений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. Если платформа [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] не установлена, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] предлагает пользователю установить ее.  
  
 Для проверки наличия [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] в браузере [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] содержится приложение начальной загрузки, которое зарегистрировано в качестве резервного обработчика [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)] для файлов содержимого со следующими расширениями: XAML, XPS, XBAP и APPLICATION. Если при попытке открыть файлы данных типов платформа [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] не установлена на клиенте, приложение начальной загрузки запрашивает разрешение на его установку. Если разрешение не предоставляется, платформа [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] и приложение не устанавливаются.  
  
 Если разрешение предоставлено, [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] скачивает и устанавливает [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] с помощью [!INCLUDE[TLA#tla_bits](../../../../includes/tlasharptla-bits-md.md)]. После успешной установки [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] изначально запрошенный файл открывается в новом окне браузера.  
  
 Автоматическое обнаружение [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] доступно для клиентов [!INCLUDE[TLA#tla_longhorn](../../../../includes/tlasharptla-longhorn-md.md)], [!INCLUDE[TLA#tla_winxpsp2](../../../../includes/tlasharptla-winxpsp2-md.md)] и [!INCLUDE[TLA#tla_winnetsvrfamsp1](../../../../includes/tlasharptla-winnetsvrfamsp1-md.md)], на которых установлен браузер [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] или более поздней версии.  
  
 Дополнительные сведения см. в разделе [Развертывание .NET Framework и приложений](../../../../docs/framework/deployment/index.md).  
  
## <a name="see-also"></a>См. также  
 [Построение приложения WPF](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [Безопасность](../../../../docs/framework/wpf/security-wpf.md)
