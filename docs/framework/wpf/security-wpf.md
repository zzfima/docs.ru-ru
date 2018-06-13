---
title: Безопасность (WPF)
ms.date: 03/30/2017
helpviewer_keywords:
- XAML files [WPF], sandbox behavior
- browser-hosted application security [WPF]
- application security [WPF]
- navigation security [WPF]
- loose XAML files [WPF], sandbox behavior
- WPF security [WPF]
- WebBrowser control [WPF], security
- feature controls [WPF], security
- XBAP security [WPF]
- Internet Explorer security settings [WPF]
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
ms.openlocfilehash: 7b58368539ed1e41c1367e0cd1da7e4181a8af7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565929"
---
# <a name="security-wpf"></a>Безопасность (WPF)
<a name="introduction"></a> При разработке Windows Presentation Foundation (WPF) автономных приложений и приложений, размещенных в веб-браузере, необходимо учитывать модели безопасности. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] Автономные приложения выполняются с неограниченными разрешениями ( [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **FullTrust** набор разрешений) независимо от способа развертывания с помощью установщика Windows (.msi) XCopy, или [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]. Развертывание автономных приложений WPF с частичным доверием с помощью ClickOnce не поддерживается. Тем не менее, ведущее приложение с полным доверием можно создать с частичным доверием <xref:System.AppDomain> с помощью модели надстроек .NET Framework. Дополнительные сведения см. в разделе [Общие сведения о надстройках WPF](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] размещенные приложения, размещенные в браузере на [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] или Firefox, и может быть как [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] или свободно [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] документы, Дополнительные сведения см. в разделе [Обзор приложений браузера XAML WPF](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] выполнение приложений веб-браузера в песочнице с частичным уровнем доверия по умолчанию, который ограничен по умолчанию [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] **Internet** набора разрешений зоны. Это эффективно изолирует [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] от клиентского компьютера таким же образом, можно ожидать обычные веб-приложения, чтобы изолировать приложения, размещенные в браузере. Приложение XBAP может повысить привилегии вплоть до полного доверия в зависимости от зоны безопасности URL-адреса развертывания и конфигурации безопасности клиента. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
 Здесь описывается модель безопасности для Windows Presentation Foundation (WPF) автономных приложений и приложений, размещенных в веб-браузере.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Безопасная навигация](#SafeTopLevelNavigation)  
  
-   [Параметры безопасности программного обеспечения для просмотра веб-страниц](#InternetExplorerSecuritySettings)  
  
-   [Элемент управления WebBrowser и элементы управления функциями](#webbrowser_control_and_feature_controls)  
  
-   [Отключение сборок APTCA для клиентских приложений с частичным доверием](#APTCA)  
  
-   [Режим песочницы для свободных файлов XAML](#LooseContentSandboxing)  
  
-   [Ресурсы для разработки приложений WPF, обеспечивающих безопасность](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## <a name="safe-navigation"></a>Безопасная навигация  
 Для [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] различает два типа переходов: приложение и браузера.  
  
 *Навигация в приложении* — это навигация между элементами содержимого в пределах приложения, размещенного в браузере. *Навигация в браузере* — это навигация, изменяющая содержимое и URL-адрес расположения самого браузера. Связь между навигации приложения (обычно XAML) и переход в браузере (как правило, HTML) показана на следующем рисунке:
  
 ![Схема навигации](../../../docs/framework/wpf/media/safetoplevelnavigationfigure.png "SafeTopLevelNavigationFigure")  
  
 Тип содержимого, которое считается безопасным для [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] для перехода к главным образом определяется использование переход в приложении или в браузере.  
  
<a name="Application_Navigation_Security"></a>   
### <a name="application-navigation-security"></a>Безопасность навигации в приложениях  
 Переход в приложении считается безопасным, если его можно с помощью пакета [!INCLUDE[TLA2#tla_uri](../../../includes/tla2sharptla-uri-md.md)], который поддерживает четыре типа содержимого:  
  
|Тип содержимого|Описание|Пример URI|  
|------------------|-----------------|-----------------|  
|Ресурс|Файлы, добавленные в проект с типом построения **ресурсов**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Content|Файлы, добавленные в проект с типом построения **содержимого**.|`pack://application:,,,/MyContentFile.xaml`|  
|Исходный веб-сайт|Файлы, добавленные в проект с типом построения **нет**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Код приложения|Ресурсы XAML, имеющие скомпилированный код программной части.<br /><br /> - или -<br /><br /> XAML-файлов, которые были добавлены в проект с типом построения **страницы**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
>  Дополнительные сведения о файлах данных и пакет [!INCLUDE[TLA2#tla_uri#plural](../../../includes/tla2sharptla-urisharpplural-md.md)], в разделе [ресурса приложения WPF, содержимое и файлы данных](../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 Файлы этих типов содержимого поддерживают навигацию, выполняемую пользователем или программно.  
  
-   **Навигация, выполняемая пользователем**. Пользователь переходит, щелкнув <xref:System.Windows.Documents.Hyperlink> элемента.  
  
-   **Программная навигация**. Приложение может выполнить переход без участия пользователя, например, установив <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> свойство.  
  
<a name="Browser_Navigation_Security"></a>   
### <a name="browser-navigation-security"></a>Безопасность навигации в браузере  
 Навигация в браузере считается безопасной только при выполнении следующих условий.  
  
-   **Навигация, выполняемая пользователем**. Пользователь переходит, нажав кнопку <xref:System.Windows.Documents.Hyperlink> элемент, расположенный в главном <xref:System.Windows.Navigation.NavigationWindow>, но не во вложенных <xref:System.Windows.Controls.Frame>.  
  
-   **Зона**. Содержимое, к которому выполняется переход, находится в Интернете или в локальной интрасети.  
  
-   **Протокол**. Используемый протокол является либо **http**, **https**, **файл**, или **mailto**.  
  
 Если [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] пытается перейти к содержимому таким способом, который не соответствует этим условиям, <xref:System.Security.SecurityException> возникает исключение.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## <a name="web-browsing-software-security-settings"></a>Параметры безопасности программного обеспечения для просмотра веб-страниц  
 Параметры безопасности компьютера определяют уровень доступа, который предоставляется программному обеспечению для просмотра веб-страниц. Веб-обозреватель включает все приложение или компонент, который использует [WinINet](http://go.microsoft.com/fwlink/?LinkId=179379) или [UrlMon](http://go.microsoft.com/fwlink/?LinkId=179383) API, в том числе Internet Explorer и PresentationHost.exe.  
  
 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] предоставляет механизм, с помощью которого можно настроить функциональные возможности которого может выполняться в [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)], включая следующие:  
  
-   .NET framework относящиеся компоненты  
  
-   элементы управления ActiveX и подключаемые модули;  
  
-   Загрузки  
  
-   Скрипты  
  
-   проверка подлинности пользователя.  
  
 Коллекция функциональных возможностей, которые могут быть защищены таким образом настраивается отдельно для каждой зоны для **Internet**, **интрасети**, **надежных узлов**, и  **Ограниченные узлы** зоны. Ниже приведена процедура для настройки параметров безопасности.  
  
1.  Откройте **панель управления**.  
  
2.  Нажмите кнопку **сеть и Интернет** и нажмите кнопку **обозревателя**.  
  
     Откроется диалоговое окно «Свойства веб-обозревателя».  
  
3.  На **безопасности** выберите зону для настройки параметров безопасности.  
  
4.  Нажмите кнопку **другой** кнопки.  
  
     **Параметры безопасности** откроется диалоговое окно, и можно настроить параметры безопасности для выбранной зоны.  
  
     ![Диалоговое окно "Параметры безопасности"](../../../docs/framework/wpf/media/wpfsecurityfigure1.PNG "WPFSecurityFigure1")  
  
> [!NOTE]
>  К диалоговому окну "Свойства обозревателя" можно также перейти из Internet Explorer. Нажмите кнопку **средства** и нажмите кнопку **обозревателя**.  
  
 Начиная с [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)], включены следующие параметры безопасности специально для .NET Framework:  
  
-   **Свободный XAML**. Элементы управления ли [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] можно перейти, отменив [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлов. (Варианты: "Включить", "Отключить" и "Запрашивать".)  
  
-   **XAML-приложения браузера**. Элементы управления ли [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] можно переходить к и запустить [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]. (Варианты: "Включить", "Отключить" и "Запрашивать".)  
  
 По умолчанию эти параметры все включены для **Internet**, **Местная интрасеть**, и **надежные сайты** зоны и отключен для **Ограниченные узлы**  зоны.  
  
<a name="Security_Settings_for_IE6_and_Below"></a>   
### <a name="security-related-wpf-registry-settings"></a>Параметры реестра WPF, связанные с безопасностью  
 Помимо параметров безопасности, доступных в окне "Свойства обозревателя", для избирательного отключения некоторых функций WPF, влияющих на безопасность, предусмотрены перечисленные далее значения реестра. Значения определяются в следующем разделе.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 В таблице ниже перечислены возможные задаваемые значения.  
  
|Имя значения|Тип значения|Данные значения|  
|----------------|----------------|----------------|  
|XBAPDisallow|REG_DWORD|1, чтобы запретить; 0, чтобы разрешить.|  
|LooseXamlDisallow|REG_DWORD|1, чтобы запретить; 0, чтобы разрешить.|  
|WebBrowserDisallow|REG_DWORD|1, чтобы запретить; 0, чтобы разрешить.|  
|MediaAudioDisallow|REG_DWORD|1, чтобы запретить; 0, чтобы разрешить.|  
|MediaImageDisallow|REG_DWORD|1, чтобы запретить; 0, чтобы разрешить.|  
|MediaVideoDisallow|REG_DWORD|1, чтобы запретить; 0, чтобы разрешить.|  
|ScriptInteropDisallow|REG_DWORD|1, чтобы запретить; 0, чтобы разрешить.|  
  
<a name="webbrowser_control_and_feature_controls"></a>   
## <a name="webbrowser-control-and-feature-controls"></a>Элемент управления WebBrowser и элементы управления функциями  
 WPF <xref:System.Windows.Controls.WebBrowser> элемент управления может использоваться для размещения веб-содержимого. WPF <xref:System.Windows.Controls.WebBrowser> перенос управления базового элемента управления WebBrowser ActiveX. WPF предоставляет некоторую поддержку для обеспечения безопасности приложения при использовании WPF <xref:System.Windows.Controls.WebBrowser> управления для размещения ненадежных веб-содержимого. Тем не менее, некоторые функции безопасности должны применяться непосредственно приложением с помощью <xref:System.Windows.Controls.WebBrowser> элемента управления. Дополнительные сведения об элементе управления WebBrowser ActiveX см. в разделе [Обзор элемента управления WebBrowser и учебники по](http://go.microsoft.com/fwlink/?LinkId=179388).  
  
> [!NOTE]
>  Этот раздел также относится к <xref:System.Windows.Controls.Frame> управления, поскольку он использует <xref:System.Windows.Controls.WebBrowser> для перехода к HTML-содержимого.  
  
 Если WPF <xref:System.Windows.Controls.WebBrowser> управления используется для размещения ненадежного веб-содержимого, в приложении следует использовать с частичным доверием <xref:System.AppDomain> для изоляции кода приложения от потенциально вредоносного кода HTML-скриптов. Это особенно важно в том случае, если приложение взаимодействует с размещенным скриптом с помощью <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> метод и <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> свойства. Дополнительные сведения см. в разделе [Общие сведения о надстройках WPF](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Если приложение использует WPF <xref:System.Windows.Controls.WebBrowser> является еще одним способом повышения уровня безопасности и снизить угрозу атак управление, чтобы включить элементы управления функциями Internet Explorer. Функции элементов управления являются дополнениями к Internet Explorer, позволяют администраторам и разработчикам настраивать функции Internet Explorer и приложений, в которых размещается элемент управления WebBrowser ActiveX, который WPF <xref:System.Windows.Controls.WebBrowser> формирует оболочку для элемента управления. Функции элементов управления можно настроить с помощью [CoInternetSetFeatureEnabled](http://go.microsoft.com/fwlink/?LinkId=179394) функцию или путем изменения значения в реестре. Дополнительные сведения о функции элементов управления см. в разделе [Знакомство с элементами управления компонент](http://go.microsoft.com/fwlink/?LinkId=179390) и [элементы управления функциями Internet](http://go.microsoft.com/fwlink/?LinkId=179392).  
  
 Если вы разрабатываете автономного приложения WPF, в котором используется WPF <xref:System.Windows.Controls.WebBrowser> управления WPF автоматически включает следующие элементы управления функциями для вашего приложения.  
  
|Элемент управления функцией|  
|---------------------|  
|FEATURE_MIME_HANDLING|  
|FEATURE_MIME_SNIFFING|  
|FEATURE_OBJECT_CACHING|  
|FEATURE_SAFE_BINDTOOBJECT|  
|FEATURE_WINDOW_RESTRICTIONS|  
|FEATURE_ZONE_ELEVATION|  
|FEATURE_RESTRICT_FILEDOWNLOAD|  
|FEATURE_RESTRICT_ACTIVEXINSTALL|  
|FEATURE_ADDON_MANAGEMENT|  
|FEATURE_HTTP_USERNAME_PASSWORD_DISABLE|  
|FEATURE_SECURITYBAND|  
|FEATURE_UNC_SAVEDFILECHECK|  
|FEATURE_VALIDATE_NAVIGATE_URL|  
|FEATURE_DISABLE_TELNET_PROTOCOL|  
|FEATURE_WEBOC_POPUPMANAGEMENT|  
|FEATURE_DISABLE_LEGACY_COMPRESSION|  
|FEATURE_SSLUX|  
  
 Поскольку эти элементы управления функциями включаются безусловно, они могут нарушать работу приложения с полным доверием. В этом случае, если нет риска безопасности для конкретного приложения и содержимого, размещенного в нем, можно отключить соответствующий элемент управления функцией.  
  
 Элементы управления функциями применяются процессом создания экземпляра объекта WebBrowser ActiveX. Таким образом, при создании автономного приложения, которое может переходить к ненадежному содержимому, следует рассмотреть возможность включения дополнительных элементов управления функциями.  
  
> [!NOTE]
>  Эта рекомендация основана на общих рекомендациях по безопасности узлов MSHTML и SHDOCVW. Дополнительные сведения см. в разделе [узла безопасности MSHTML часто задаваемые вопросы об: первая из II](http://go.microsoft.com/fwlink/?LinkId=179396) и [узла безопасности MSHTML часто задаваемые вопросы об: часть II II](http://go.microsoft.com/fwlink/?LinkId=179415).  
  
 Для исполняемого файла можно включить следующие элементы управления функциями путем установки значения реестра равным 1.  
  
|Элемент управления функцией|  
|---------------------|  
|FEATURE_ACTIVEX_REPURPOSEDETECTION|  
|FEATURE_BLOCK_LMZ_IMG|  
|FEATURE_BLOCK_LMZ_OBJECT|  
|FEATURE_BLOCK_LMZ_SCRIPT|  
|FEATURE_RESTRICT_RES_TO_LMZ|  
|FEATURE_RESTRICT_ABOUT_PROTOCOL_IE7|  
|FEATURE_SHOW_APP_PROTOCOL_WARN_DIALOG|  
|FEATURE_LOCALMACHINE_LOCKDOWN|  
|FEATURE_FORCE_ADDR_AND_STATUS|  
|FEATURE_RESTRICTED_ZONE_WHEN_FILE_NOT_FOUND|  
  
 Для исполняемого файла можно отключить следующие элементы управления функциями путем установки значения реестра равным 0.  
  
|Элемент управления функцией|  
|---------------------|  
|FEATURE_ENABLE_SCRIPT_PASTE_URLACTION_IF_PROMPT|  
  
 При выполнении с частичным доверием [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] , включающего WPF <xref:System.Windows.Controls.WebBrowser> управления [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)], WPF размещает элемент управления WebBrowser ActiveX в адресном пространстве процесса Internet Explorer. Поскольку элемент управления WebBrowser ActiveX размещается в [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] процесса, все элементы управления функциями для Internet Explorer также включены для элемента управления WebBrowser ActiveX.  
  
 XBAP-приложения, выполняющиеся в Internet Explorer, также получают более высокий уровень безопасности по сравнению с обычными автономными приложениями. — Этот повышенный уровень безопасности, так как Internet Explorer и, следовательно, элемент управления WebBrowser ActiveX, выполняется в защищенном режиме по умолчанию на [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] и [!INCLUDE[win7](../../../includes/win7-md.md)]. Дополнительные сведения о защищенном режиме см. в разделе [понимании и работе в защищенный режим Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=179393).  
  
> [!NOTE]
>  При попытке запуска XBAP, содержащего WPF <xref:System.Windows.Controls.WebBrowser> управления в Firefox в зоне Интернета <xref:System.Security.SecurityException> будет создано. Это связано с политикой безопасности WPF.  
  
<a name="APTCA"></a>   
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Отключение сборок APTCA для клиентских приложений с частичным доверием  
 При установке в управляемых сборках [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)], они становятся полностью доверенных, так как пользователь должен предоставить явное разрешение на их установку. Поскольку они пользуются полным доверием, их могут использовать только полностью доверенные управляемые клиентские приложения. Чтобы разрешить частично доверенным приложениям использовать их, они должны быть отмечены <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA). Этим атрибутом могут быть помечены только сборки, которые были протестированы для подтверждения безопасности при выполнении в режиме частичного доверия.  
  
 Тем не менее, существует возможность уязвимости безопасности сборки APTCA после установки в [!INCLUDE[TLA2#tla_gac](../../../includes/tla2sharptla-gac-md.md)]. После обнаружения уязвимости безопасности издатели сборок могут создавать обновления безопасности для решения проблем существующих установок и защиты установок, которые могут выполняться после выявления проблемы. Одним из вариантов обновления является удаление сборки, хотя это может нарушить работу других полностью доверенных клиентских приложений, использующих сборку.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] предоставляет механизм, с помощью которого можно отключить сборку APTCA, для частично доверенных [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] без удаления сборки APTCA.  
  
 Чтобы отключить сборку APTCA, необходимо создать специальный раздел реестра.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Пример приведен ниже.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Этот раздел содержит запись для сборки APTCA. Вам также потребуется создать значение в этом разделе, включающее или отключающее сборку. Ниже приведены сведения об этом значении.  
  
-   Имя параметра: **APTCA_FLAG**.  
  
-   Тип значения: **REG_DWORD**.  
  
-   Данные значения: **1** для отключения; **0** для включения.  
  
 Если сборку необходимо отключить для клиентских приложений с частичным доверием, можно написать обновление, создающее раздел реестра и значение.  
  
> [!NOTE]
>  Базовые сборки .NET Framework не затрагивается отключения их таким образом, так как они необходимы для запуска управляемых приложений. Поддержка отключения сборок APTCA в основном ориентирована на сторонние приложения.  
  
<a name="LooseContentSandboxing"></a>   
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Режим песочницы для свободных файлов XAML  
 Свободные [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлы являются только разметку XAML-файлов, которые не зависят от любого кода, обработчик событий или сборка конкретного приложения. Когда переход к свободным [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлов осуществляется непосредственно из браузера, они загружаются в изолированной среде безопасности, в зависимости от набора разрешений зоны Интернета по умолчанию.  
  
 Тем не менее, поведение безопасности изменяется при свободные [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлов осуществляется либо из <xref:System.Windows.Navigation.NavigationWindow> или <xref:System.Windows.Controls.Frame> в автономном приложении.  
  
 В обоих случаях свободный [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файла, к которому осуществляется переход, наследует разрешения от главного приложения. Однако такое поведение может быть нежелательно с точки зрения безопасности, особенно в том случае, если свободный [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файл был создан с помощью объекта, который является доверенным или неизвестное. Этот тип содержимого известен как *внешнее содержимое*и оба <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow> можно настроить, чтобы изолировать его при переходе. Изоляция достигается путем установки **SandboxExternalContent** для свойства значение true, как показано в следующих примерах для <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow>:  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Этот параметр позволяет загружать внешнее содержимое в процесс, который отделен от процесса, содержащего приложение. Этот процесс ограничен набором разрешений зоны Интернета по умолчанию, что эффективно изолирует его от ведущего приложения и клиентского компьютера.  
  
> [!NOTE]
>  Несмотря на то что переход к свободным файлам [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлов из любого <xref:System.Windows.Navigation.NavigationWindow> или <xref:System.Windows.Controls.Frame> в автономном приложении реализован на основе обозревателя WPF, размещающая инфраструктура, включающий процесс PresentationHost, уровень безопасности при немного меньше, чем при загрузке содержимого непосредственно в Internet Explorer на [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] и [!INCLUDE[win7](../../../includes/win7-md.md)] (которая все равно выполняется через процесс PresentationHost). Это обусловлено тем, что автономное приложение WPF, использующее веб-браузер, не предоставляет дополнительную функцию безопасности "Защищенный режим" Internet Explorer.  
  
<a name="BestPractices"></a>   
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Ресурсы для разработки приложений WPF, обеспечивающих безопасность  
 Ниже приведены некоторые дополнительные ресурсы, помогающие при разработке [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] приложений, обеспечивающих безопасность:  
  
|Область|Ресурс|  
|----------|--------------|  
|Управляемый код|[Шаблоны и рекомендации по обеспечению безопасности приложений](http://go.microsoft.com/fwlink/?LinkId=117426)|  
|[!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]|[Управление доступом для кода](../../../docs/framework/misc/code-access-security.md)|  
|[!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]|[Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[Безопасность частичного доверия в WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>См. также  
 [Безопасность частичного доверия в WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)  
 [Стратегия безопасности WPF — безопасность платформы](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)  
 [Стратегия безопасности WPF — проектирование безопасности](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)  
 [Шаблоны и рекомендации по обеспечению безопасности приложений](http://go.microsoft.com/fwlink/?LinkId=117426)  
 [Управление доступом для кода](../../../docs/framework/misc/code-access-security.md)  
 [Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)  
 [Общие сведения о языке XAML (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
