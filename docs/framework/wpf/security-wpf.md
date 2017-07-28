---
title: "Безопасность (WPF) | Microsoft Docs"
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
  - "безопасность приложений [WPF]"
  - "безопасность приложений, размещаемых в браузере [WPF]"
  - "элементы управления компонента [WPF], безопасность"
  - "параметры безопасности Internet Explorer [WPF]"
  - "файлы на свободном языке XAML [WPF], поведение изолированной среды"
  - "безопасность переходов [WPF]"
  - "WebBrowser - элемент управления [WPF], безопасность"
  - "безопасность WPF"
  - "XAML-файлы [WPF], поведение изолированной среды"
  - "XBAP - безопасность [WPF]"
ms.assetid: ee1baea0-3611-4e36-9ad6-fcd5205376fb
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 33
---
# Безопасность (WPF)
<a name="introduction"></a> При разработке приложений [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] \(как браузерных, так и автономных\) необходимо принимать во внимание модель безопасности. Автономные приложения [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] выполняются с неограниченными разрешениями \(набор разрешений **FullTrust** в [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]\) независимо от способа развертывания \(установщик Windows — MSI\-файл, средство XCopy или [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]\).  Развертывание автономных приложений WPF в режиме частичного доверия с помощью ClickOnce не поддерживается.  Впрочем, ведущее приложение с полным доверием может создать элемент <xref:System.AppDomain> с частичным доверием с помощью модели надстроек .NET Framework.  Дополнительные сведения см. в разделе [Общие сведения о надстройках WPF](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Браузерные приложения [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] выполняются в браузере [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] или Firefox и могут представлять собой либо приложения [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)], либо документы со свободным [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)]\-кодом. Дополнительные сведения см. в разделе [Общие сведения о приложениях браузера WPF XAML](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  
  
 Браузерные приложения [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] по умолчанию выполняются в изолированной среде безопасности с частичным доверием, которая ограничена набором разрешений [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] для зоны **Интернет** по умолчанию.  Это фактически изолирует браузерные приложения [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] от клиентского компьютера так же, как изолируются обычные веб\-приложения.  Модуль XBAP может повысить привилегии вплоть до полного доверия, в зависимости от зоны безопасности, в которой находится URL\-адрес развертывания, и конфигурации системы безопасности клиента.  Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
 В этом разделе рассматривается модель безопасности [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] автономных приложений и приложений, размещаемых в браузере.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Безопасный переход](#SafeTopLevelNavigation)  
  
-   [Параметры безопасности для ПО с функциями браузера](#InternetExplorerSecuritySettings)  
  
-   [Элемент управления WebBrowser и элементы управления функциями](#webbrowser_control_and_feature_controls)  
  
-   [Отключение сборок APTCA для приложений клиентов частичного доверия](#APTCA)  
  
-   [Поведение изолированной среды для свободных файлов XAML](#LooseContentSandboxing)  
  
-   [Ресурсы для разработки приложений WPF, обеспечивающих безопасность](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## Безопасный переход  
 В отношении модуля [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] среда [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] различает два типа переходов: в приложении и в браузере.  
  
 *Переход в приложении* — это переход между элементами содержимого в пределах приложения, выполняемого в браузере.  *Переход в браузере* — это переход, изменяющий URL\-адрес содержимого и расположения в самом браузере.  Связь между переходом в приложении \(как правило, XAML\) и переходом в браузере \(как правило, HTML\) показана на следующем рисунке.  
  
 ![Схема перехода](../../../docs/framework/wpf/media/safetoplevelnavigationfigure.png "SafeTopLevelNavigationFigure")  
  
 Тип содержимого, переход на которое считается безопасным для [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)], главным образом определяется по тому, какой переход происходит: в приложении или в браузере.  
  
<a name="Application_Navigation_Security"></a>   
### Безопасность перехода приложения  
 Переход в приложении считается безопасным, если он соответствует коду [!INCLUDE[TLA2#tla_uri](../../../includes/tla2sharptla-uri-md.md)] типа "pack", который поддерживает следующие четыре типа содержимого.  
  
|Тип содержимого|Описание|Пример URI|  
|---------------------|--------------|----------------|  
|Ресурс|Файлы, добавленные в проект с типом построения **Ресурс**.|`pack://application:,,,/MyResourceFile.xaml`|  
|Содержимое|Файлы, добавленные в проект с типом построения **Содержимое**.|`pack://application:,,,/MyContentFile.xaml`|  
|Исходный сайт|Файлы, добавленные в проект с типом построения **Нет**.|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Код приложения|Ресурсы XAML, имеющие скомпилированный код программной части.<br /><br /> \-или\-<br /><br /> XAML\-файлы, добавленные в проект с типом построения **Страница**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
>  Дополнительные сведения о файлах данных приложения и [!INCLUDE[TLA2#tla_uri#plural](../../../includes/tla2sharptla-urisharpplural-md.md)] типа "pack" содержатся в разделе [Ресурсы, Содержимое и Файлы данных WPF\-приложения](../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  
  
 К файлам этих типов содержимого разрешены переходы как программным способом, так и по команде пользователя.  
  
-   **Пользовательский переход**.  Пользователь может выполнить переход, щелкнув элемент <xref:System.Windows.Documents.Hyperlink>.  
  
-   **Программный переход**.  Приложение может выполнить переход без участия пользователя, например если задать свойство <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=fullName>.  
  
<a name="Browser_Navigation_Security"></a>   
### Безопасность перехода браузера  
 Переход в браузере считается безопасным только при выполнении следующих условий.  
  
-   **Пользовательский переход**.  Пользователь может выполнить переход, щелкнув элемент <xref:System.Windows.Documents.Hyperlink>, расположенный в главном окне <xref:System.Windows.Navigation.NavigationWindow>, но не во вложенном элементе <xref:System.Windows.Controls.Frame>.  
  
-   **Зона**.  Содержимое, к которому осуществляется переход, находится в Интернете или локальной сети.  
  
-   **Протокол**.  Используется один из следующих протоколов: **http**, **https**, **file** или **mailto**.  
  
 Если [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] пытается перейти к содержимому каким\-либо способом, не соответствующим этим условиям, генерируется исключение <xref:System.Security.SecurityException>.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## Параметры безопасности для ПО с функциями браузера  
 Параметры безопасности компьютера определяют права доступа, предоставляемые любому установленному на нем ПО с функциями веб\-браузера.  К ПО с функциями браузера относится любое приложение \(или компонент\), использующее API\-интерфейс [WinINet](http://go.microsoft.com/fwlink/?LinkId=179379) или [UrlMon](http://go.microsoft.com/fwlink/?LinkId=179383), в том числе Internet Explorer и PresentationHost.exe.  
  
 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] предоставляет механизм, с помощью которого можно настроить функциональные возможности, разрешенные для выполнения в [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)], в том числе следующие:  
  
-   Компоненты, основанные на [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)]  
  
-   Элементы управления ActiveX и подключаемые модули  
  
-   Загрузки  
  
-   Сценарии  
  
-   Проверка подлинности пользователя  
  
 Коллекция функциональных возможностей, обеспечиваемых таким образом, настраивается на уровне зон **Интернет**, **Интрасеть**, **Надежные сайты** и **Ненадежные сайты**.  Ниже приводятся указания о том, как настроить параметры безопасности.  
  
1.  Откройте **панель управления**.  
  
2.  Щелкните элемент **Сеть и Интернет** и выберите **Свойства браузера**.  
  
     Откроется диалоговое окно "Свойства браузера".  
  
3.  На вкладке **Безопасность** выберите зону, для которой требуется настроить параметры безопасности.  
  
4.  Нажмите кнопку **Другой**.  
  
     Откроется диалоговое окно **Параметры безопасности**, в котором можно настроить параметры безопасности для выбранной зоны.  
  
     ![Диалоговое окно “Параметры безопасности”](../../../docs/framework/wpf/media/wpfsecurityfigure1.PNG "WPFSecurityFigure1")  
  
> [!NOTE]
>  Диалоговое окно "Свойства браузера" также можно открыть через Internet Explorer.  Откройте меню **Сервис** и выберите пункт **Свойства браузера**.  
  
 В [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)] и более поздних версиях имеются следующие параметры безопасности, относящиеся только к [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)].  
  
-   **Свободные XAML**.  Управляет способностью [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] переходить к файлам [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] и освобождать их.  \(Параметры "Включить", "Отключить" и "Запрашивать"\).  
  
-   **Приложения браузера XAML**.  Управляет способностью [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] переходить к [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] и выполнять их.  \(Параметры "Включить", "Отключить" и "Запрашивать"\).  
  
 По умолчанию все эти параметры включены для зон **Интернет**, **Местная интрасеть** и **Надежные сайты** и отключены для зоны **Ненадежные сайты**.  
  
<a name="Security_Settings_for_IE6_and_Below"></a>   
### Параметры безопасности WPF в реестре  
 Помимо параметров безопасности в окне "Свойства браузера", для избирательного отключения некоторых функций WPF, связанных с безопасностью, можно использовать следующие значения в реестре.  Эти значения определены в следующем разделе реестра:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\Windows Presentation Foundation\Features`  
  
 В следующей таблице перечислены значения, которые могут быть установлены.  
  
|Имя значения|Тип значения|Данные значения|  
|------------------|------------------|---------------------|  
|XBAPDisallow|REG\_DWORD|1 — запретить, 0 — разрешить.|  
|LooseXamlDisallow|REG\_DWORD|1 — запретить, 0 — разрешить.|  
|WebBrowserDisallow|REG\_DWORD|1 — запретить, 0 — разрешить.|  
|MediaAudioDisallow|REG\_DWORD|1 — запретить, 0 — разрешить.|  
|MediaImageDisallow|REG\_DWORD|1 — запретить, 0 — разрешить.|  
|MediaVideoDisallow|REG\_DWORD|1 — запретить, 0 — разрешить.|  
|ScriptInteropDisallow|REG\_DWORD|1 — запретить, 0 — разрешить.|  
  
<a name="webbrowser_control_and_feature_controls"></a>   
## Элемент управления WebBrowser и элементы управления функциями  
 Элемент управления WPF <xref:System.Windows.Controls.WebBrowser> можно использовать для размещения веб\-содержимого.  Элемент управления WPF <xref:System.Windows.Controls.WebBrowser> служит оболочкой базового элемента управления ActiveX WebBrowser.  WPF позволяет обеспечить некоторую степень безопасности в приложении, если ненадежное веб\-содержимое размещается в элементе управления WPF <xref:System.Windows.Controls.WebBrowser>.  Впрочем, некоторые функции безопасности должны применяться приложениями напрямую с помощью элемента управления <xref:System.Windows.Controls.WebBrowser>.  Дополнительные сведения об элементе управления ActiveX WebBrowser см. на странице [WebBrowser Control Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=179388).  
  
> [!NOTE]
>  Этот раздел также относится к элементу управления <xref:System.Windows.Controls.Frame>, поскольку он использует элемент <xref:System.Windows.Controls.WebBrowser> для перехода к HTML\-содержимому.  
  
 Если элемент управления WPF <xref:System.Windows.Controls.WebBrowser> используется для размещения ненадежного веб\-содержимого, в приложении следует использовать режим частичного доверия <xref:System.AppDomain> для изоляции кода приложения от потенциально вредоносного кода HTML\-скриптов.  Это особенно важно, если приложение взаимодействует с размещенным скриптом с помощью метода <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> и свойства <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>.  Дополнительные сведения см. в разделе [Общие сведения о надстройках WPF](../../../docs/framework/wpf/app-development/wpf-add-ins-overview.md).  
  
 Если в приложении используется элемент управления WPF <xref:System.Windows.Controls.WebBrowser>, есть и другой способ повысить уровень безопасности и снизить угрозу атак: включить элементы управления функциями Internet Explorer.  Элементы управления функциями — это дополнения к браузеру Internet Explorer, позволяющие администраторам и разработчикам настраивать функции Internet Explorer и приложений, в которых размещается элемент управления ActiveX WebBrowser, оболочкой которого служит элемент управления WPF <xref:System.Windows.Controls.WebBrowser>.  Элементы управления функциями можно настроить с помощью функции [CoInternetSetFeatureEnabled](http://go.microsoft.com/fwlink/?LinkId=179394) или путем изменения значений в реестре.  Дополнительные сведения об элементах управления функциями см. на страницах [Introduction to Feature Controls](http://go.microsoft.com/fwlink/?LinkId=179390) и [Internet Feature Controls](http://go.microsoft.com/fwlink/?LinkId=179392).  
  
 При разработке автономного приложения WPF, в котором используется элемент управления WPF <xref:System.Windows.Controls.WebBrowser>, среда WPF автоматически включает следующие элементы управления функциями для разрабатываемого приложения.  
  
|Элемент управления функциями|  
|----------------------------------|  
|FEATURE\_MIME\_HANDLING|  
|FEATURE\_MIME\_SNIFFING|  
|FEATURE\_OBJECT\_CACHING|  
|FEATURE\_SAFE\_BINDTOOBJECT|  
|FEATURE\_WINDOW\_RESTRICTIONS|  
|FEATURE\_ZONE\_ELEVATION|  
|FEATURE\_RESTRICT\_FILEDOWNLOAD|  
|FEATURE\_RESTRICT\_ACTIVEXINSTALL|  
|FEATURE\_ADDON\_MANAGEMENT|  
|FEATURE\_HTTP\_USERNAME\_PASSWORD\_DISABLE|  
|FEATURE\_SECURITYBAND|  
|FEATURE\_UNC\_SAVEDFILECHECK|  
|FEATURE\_VALIDATE\_NAVIGATE\_URL|  
|FEATURE\_DISABLE\_TELNET\_PROTOCOL|  
|FEATURE\_WEBOC\_POPUPMANAGEMENT|  
|FEATURE\_DISABLE\_LEGACY\_COMPRESSION|  
|FEATURE\_SSLUX|  
  
 Поскольку эти элементы управления функциями включаются безусловно, они могут препятствовать корректной работе приложения с полным доверием.  В этом случае, если для приложения и размещенного в нем содержимого угроза безопасности отсутствует, можно отключить соответствующий элемент управления функциями.  
  
 Элементы управления функциями применяются процессом, создающим экземпляры объекта ActiveX WebBrowser.  Поэтому при разработке автономного приложения, способного переходить к ненадежному содержимому, рекомендуется рассмотреть возможность включения дополнительных элементов управления функциями.  
  
> [!NOTE]
>  Этот совет основан на общих рекомендациях по безопасности основных приложений MSHTML и SHDOCVW.  Дополнительные сведения см. на страницах [The MSHTML Host Security FAQ: Part I of II](http://go.microsoft.com/fwlink/?LinkId=179396) и [The MSHTML Host Security FAQ: Part II of II](http://go.microsoft.com/fwlink/?LinkId=179415).  
  
 При разработке приложения рекомендуется рассмотреть возможность включения следующих элементов управления функциями путем установки значений в реестре на 1.  
  
|Элемент управления функциями|  
|----------------------------------|  
|FEATURE\_ACTIVEX\_REPURPOSEDETECTION|  
|FEATURE\_BLOCK\_LMZ\_IMG|  
|FEATURE\_BLOCK\_LMZ\_OBJECT|  
|FEATURE\_BLOCK\_LMZ\_SCRIPT|  
|FEATURE\_RESTRICT\_RES\_TO\_LMZ|  
|FEATURE\_RESTRICT\_ABOUT\_PROTOCOL\_IE7|  
|FEATURE\_SHOW\_APP\_PROTOCOL\_WARN\_DIALOG|  
|FEATURE\_LOCALMACHINE\_LOCKDOWN|  
|FEATURE\_FORCE\_ADDR\_AND\_STATUS|  
|FEATURE\_RESTRICTED\_ZONE\_WHEN\_FILE\_NOT\_FOUND|  
  
 При разработке приложения рекомендуется рассмотреть возможность отключения следующего элемента управления функциями путем установки значения в реестре на 0.  
  
|Элемент управления функциями|  
|----------------------------------|  
|FEATURE\_ENABLE\_SCRIPT\_PASTE\_URLACTION\_IF\_PROMPT|  
  
 При использовании модуля [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] с частичным доверием, включающего элемент управления WPF <xref:System.Windows.Controls.WebBrowser> в [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)], среда WPF размещает элемент управления ActiveX WebBrowser в адресном пространстве процесса Internet Explorer.  Поскольку элемент управления ActiveX WebBrowser размещается в процессе [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)], все элементы управления функциями для Internet Explorer включены также и для элемента управления ActiveX WebBrowser.  
  
 Модули XBAP, выполняемые в браузере Internet Explorer, также получают более высокий уровень безопасности по сравнению с обычными автономными приложениями.  Этот повышенный уровень безопасности объясняется тем, что в [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] и [!INCLUDE[win7](../../../includes/win7-md.md)] Internet Explorer \(а значит, и элемент управления ActiveX WebBrowser\) по умолчанию выполняется в защищенном режиме.  Дополнительные сведения о защищенном режиме см. на странице [Understanding and Working in Protected Mode Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=179393).  
  
> [!NOTE]
>  При попытке запуска модуля XBAP, содержащего элемент управления WPF <xref:System.Windows.Controls.WebBrowser>, в браузере Firefox при нахождении в зоне "Интернет", генерируется исключение <xref:System.Security.SecurityException>.  Это обуславливается политикой безопасности WPF.  
  
<a name="APTCA"></a>   
## Отключение сборок APTCA для приложений клиентов частичного доверия  
 При установке в [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)] управляемых сборок они становятся полностью безопасными, так как пользователь должен предоставить явное разрешение на их установку.  Поскольку они являются полностью безопасными, только полностью безопасные управляемые клиентские приложения могут использовать их.  Чтобы разрешить частично безопасным приложениям использовать их, они должны быть помечены <xref:System.Security.AllowPartiallyTrustedCallersAttribute>\(APTCA\).  Только сборки, которые были проверены на безопасность выполнения, должны быть помечены этим атрибутом.  
  
 Однако, имеется возможность уязвимости безопасности сборки APTCA после установки в [!INCLUDE[TLA2#tla_gac](../../../includes/tla2sharptla-gac-md.md)].  После нахождения уязвимости в безопасности издатели сборок могут создавать обновления безопасности для решения проблемы существующих установок и защититься от установок, которые могут произойти после обнаружения проблемы.  Одним из вариантов обновления является удаление сборки, хотя это может прервать работу других полностью доверенных клиентских приложений, использующих сборку.  
  
 В [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] предусмотрен механизм, с помощью которого можно отключить сборку APTCA для модулей [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] с частичным доверием, не удаляя ее.  
  
 Чтобы отключить сборку APTCA, необходимо создать специальный раздел реестра:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Ниже представлен пример раздела реестра:  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Этот раздел реестра содержит запись для сборки APTCA.  В этом разделе также необходимо создать значение, включающее или отключающее сборку.  Ниже представлены сведения об этом значении:  
  
-   Имя значения: **APTCA\_FLAG**.  
  
-   Тип значения: **REG\_DWORD**.  
  
-   Данные значения: **1** для отключения; **0** для включения.  
  
 Если необходимо отключить сборку для клиентских приложений с частичным доверием, можно написать обновление, создающее раздел реестра и значение.  
  
> [!NOTE]
>  Сборки ядра [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] не могут быть отключены таким способом, поскольку они необходимы для запуска управляемых приложений.  Поддержка отключения сборок APTCA предназначена прежде всего для сторонних разработчиков приложений.  
  
<a name="LooseContentSandboxing"></a>   
## Поведение изолированной среды для свободных файлов XAML  
 Свободные файлы [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] представляют собой XAML\-файлы, содержащие только разметку и не зависящие от каких\-либо файлов кода программной части, обработчиков событий или сборок, специфичных для приложения.  Когда переход к свободным файлам [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] осуществляется непосредственно из браузера, они загружаются в изолированной среде безопасности в зависимости набора разрешений для зоны "Интернет" по умолчанию.  
  
 Однако, поведение безопасности изменяется при переходе к свободным файлам [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] из <xref:System.Windows.Navigation.NavigationWindow> или <xref:System.Windows.Controls.Frame> в изолированном приложении.  
  
 В обоих случаях свободный файл [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], к которому осуществляется переход, наследует разрешения от главного приложения.  Однако, такое поведение может быть нежелательно с точки зрения безопасности, особенно в том случае, если свободный файл [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] был создан через небезопасную или неизвестную сущность.  Этот тип содержимого известен как *внешнее содержимое*, а <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow> могут быть настроены так, чтобы изолировать его при переходе.  Изоляция достигается установкой свойства **SandboxExternalContent** в значение true, как показано в следующих примерах для <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow>:  
  
 [!code-xml[SecurityOverviewSnippets#FrameMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xml[SecurityOverviewSnippets#NavigationWindowMARKUP](../../../samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 С этим параметром внешнее содержимое будет загружено в процесс, который отличается от процесса, в котором размещено приложение.  Этот процесс ограничен набором разрешений зоны "Интернет" по умолчанию, который изолирует его от главного приложения и клиентского компьютера.  
  
> [!NOTE]
>  Несмотря на то что переход к файлам свободного [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] из элемента управления <xref:System.Windows.Navigation.NavigationWindow> или <xref:System.Windows.Controls.Frame> в автономном приложении реализован на основе инфраструктуры WPF для размещения в браузере, использующей процесс PresentationHost, уровень безопасности при этом чуть ниже, чем при прямой загрузке содержимого в Internet Explorer в [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] и [!INCLUDE[win7](../../../includes/win7-md.md)] \(которая все равно выполняется через процесс PresentationHost\). Это объясняется тем, что у автономного приложения WPF, использующего веб\-браузер, отсутствует функция безопасности "защищенный режим" браузера Internet Explorer.  
  
<a name="BestPractices"></a>   
## Ресурсы для разработки приложений WPF, обеспечивающих безопасность  
 Ниже приведены ссылки на дополнительные сведения по разработке приложений [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], обеспечивающих безопасность.  
  
|Область|Ресурс|  
|-------------|------------|  
|Управляемый код|[Patterns and Practices Security Guidance for Applications](http://go.microsoft.com/fwlink/?LinkId=117426)|  
|[!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)]|[Управление доступом для кода](../../../docs/framework/misc/code-access-security.md)|  
|[!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)]|[Развертывание и безопасность технологии ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[Безопасность частичного доверия в WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)|  
  
## См. также  
 [Безопасность частичного доверия в WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)   
 [Стратегия безопасности WPF — безопасность платформы](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)   
 [Стратегия безопасности WPF — проектирование безопасности](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)   
 [Patterns and Practices Security Guidance for Applications](http://go.microsoft.com/fwlink/?LinkId=117426)   
 [Управление доступом для кода](../../../docs/framework/misc/code-access-security.md)   
 [Развертывание и безопасность технологии ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)