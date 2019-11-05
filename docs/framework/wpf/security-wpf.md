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
ms.openlocfilehash: 908c3fb0baacc7fd75dae875e9a9d49a08fe5401
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459725"
---
# <a name="security-wpf"></a>Безопасность (WPF)
<a name="introduction"></a>При разработке изолированных приложений Windows Presentation Foundation (WPF) и обозревателей, размещенных в браузере, необходимо учитывать модель безопасности. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] автономные приложения выполняются с неограниченными разрешениями (набор разрешений**FULLTRUST** CAS), будь то развертывание с помощью установщик Windows (. msi), XCOPY или ClickOnce. Развертывание автономных приложений WPF с частичным доверием с помощью ClickOnce не поддерживается. Однако ведущее приложение с полным доверием может создать <xref:System.AppDomain> частичного доверия с помощью модели надстройки .NET Framework. Дополнительные сведения см. в разделе [Общие сведения о](./app-development/wpf-add-ins-overview.md)надстройках WPF.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] размещенные в браузере приложения размещаются в Windows Internet Explorer или Firefox и могут быть либо приложениями браузера XAML (XBAP), либо свободными [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] документами. Дополнительные сведения см. в статье [Общие сведения о приложениях браузера WPF XAML](./app-development/wpf-xaml-browser-applications-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] приложения, размещенные в браузере, выполняются в песочнице безопасности с частичным доверием по умолчанию, которая ограничена набором разрешений зоны**Интернета** CAS по умолчанию. Это эффективно изолирует [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] приложений, размещенных в браузере, от клиентского компьютера точно так же, как обычные веб-приложения будут изолированы. Приложение XBAP может повысить привилегии вплоть до полного доверия в зависимости от зоны безопасности URL-адреса развертывания и конфигурации безопасности клиента. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](wpf-partial-trust-security.md).  
  
 В этом разделе обсуждается модель безопасности для изолированных приложений Windows Presentation Foundation (WPF) и обозревателей, размещенных в браузере.  
  
 В этом разделе содержатся следующие подразделы.  
  
- [Безопасная навигация](#SafeTopLevelNavigation)  
  
- [Параметры безопасности программного обеспечения для просмотра веб-страниц](#InternetExplorerSecuritySettings)  
  
- [Элемент управления WebBrowser и элементы управления функциями](#webbrowser_control_and_feature_controls)  
  
- [Отключение сборок APTCA для клиентских приложений с частичным доверием](#APTCA)  
  
- [Режим песочницы для свободных файлов XAML](#LooseContentSandboxing)  
  
- [Ресурсы для разработки приложений WPF, обеспечивающих безопасность](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>   
## <a name="safe-navigation"></a>Безопасная навигация  
 Для XBAP [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] различает два типа навигации: приложение и браузер.  
  
 *Навигация в приложении* — это навигация между элементами содержимого в пределах приложения, размещенного в браузере. *Навигация в браузере* — это навигация, изменяющая содержимое и URL-адрес расположения самого браузера. Связь между навигацией между приложениями (обычно XAML) и навигацией в браузере (как правило, HTML) показана на следующем рисунке:
  
 ![Связь между навигацией приложения и навигацией в браузере.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 Тип содержимого, которое считается безопасным для перехода XBAP, в первую очередь определяется тем, используется ли Навигация по приложению или браузер.  
  
<a name="Application_Navigation_Security"></a>   
### <a name="application-navigation-security"></a>Безопасность навигации в приложениях  
 Навигация по приложениям считается надежной, если ее можно определить с помощью URI типа "Pack", который поддерживает четыре типа содержимого:  
  
|Тип содержимого|Описание|Пример URI|  
|------------------|-----------------|-----------------|  
|Ресурс|Файлы, добавляемые в проект с типом построения " **ресурс**".|`pack://application:,,,/MyResourceFile.xaml`|  
|Content|Файлы, добавляемые в проект с типом сборки **содержимое**.|`pack://application:,,,/MyContentFile.xaml`|  
|Исходный веб-сайт|Файлы, добавляемые в проект с типом построения " **нет**".|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Код приложения|Ресурсы XAML, имеющие скомпилированный код программной части.<br /><br /> \- или -<br /><br /> Файлы XAML, добавляемые в проект с типом сборки **страница**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> Дополнительные сведения о файлах данных приложения и URI типа "Pack" см. в разделе [ресурс приложения WPF, содержимое и файлы данных](./app-development/wpf-application-resource-content-and-data-files.md).  
  
 Файлы этих типов содержимого поддерживают навигацию, выполняемую пользователем или программно.  
  
- **Навигация, выполняемая пользователем**. Пользователь переходит по щелчку элемента <xref:System.Windows.Documents.Hyperlink>.  
  
- **Программная навигация**. Приложение переходит без участия пользователя, например путем установки свойства <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType>.  
  
<a name="Browser_Navigation_Security"></a>   
### <a name="browser-navigation-security"></a>Безопасность навигации в браузере  
 Навигация в браузере считается безопасной только при выполнении следующих условий.  
  
- **Навигация, выполняемая пользователем**. Пользователь переходит по элементу <xref:System.Windows.Documents.Hyperlink>, который находится в основном <xref:System.Windows.Navigation.NavigationWindow>, а не во вложенной <xref:System.Windows.Controls.Frame>.  
  
- **Зона**. Содержимое, к которому выполняется переход, находится в Интернете или в локальной интрасети.  
  
- **Протокол**. Используемый протокол — **http**, **HTTPS**, **File**или **mailto**.  
  
 Если XBAP пытается переходить к содержимому способом, который не соответствует этим условиям, выдается <xref:System.Security.SecurityException>.  
  
<a name="InternetExplorerSecuritySettings"></a>   
## <a name="web-browsing-software-security-settings"></a>Параметры безопасности программного обеспечения для просмотра веб-страниц  
 Параметры безопасности компьютера определяют уровень доступа, который предоставляется программному обеспечению для просмотра веб-страниц. Программное обеспечение для обзора веб-страниц включает в себя любое приложение или компонент, использующие API [WinInet](https://go.microsoft.com/fwlink/?LinkId=179379) или [UrlMon](https://go.microsoft.com/fwlink/?LinkId=179383) , включая Internet Explorer и PresentationHost. exe.  
  
 Internet Explorer предоставляет механизм, с помощью которого можно настроить функциональные возможности, разрешенные для выполнения в Internet Explorer, включая следующие.  
  
- Компоненты, зависящие от .NET Framework  
  
- элементы управления ActiveX и подключаемые модули;  
  
- Загрузки  
  
- Скрипты  
  
- проверка подлинности пользователя.  
  
 Набор функциональных возможностей, которые могут быть защищены таким образом, настраивается для каждой зоны в зонах " **Интернет**", " **интрасеть**", " **Доверенные сайты**" и " **ограниченные сайты** ". Ниже приведена процедура для настройки параметров безопасности.  
  
1. Откройте **панель управления**.  
  
2. Щелкните **сеть и Интернет** , а затем выберите **Свойства обозревателя**.  
  
     Откроется диалоговое окно «Свойства веб-обозревателя».  
  
3. На вкладке **Безопасность** выберите зону, для которой необходимо настроить параметры безопасности.  
  
4. Нажмите кнопку **Пользовательский уровень** .  
  
     Откроется диалоговое окно **Параметры безопасности** , в котором можно настроить параметры безопасности для выбранной зоны.  
  
     ![Снимок экрана, на котором показано диалоговое окно "Параметры безопасности".](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> К диалоговому окну "Свойства обозревателя" можно также перейти из Internet Explorer. В меню **Сервис** выберите пункт **Свойства обозревателя**.  
  
 Начиная с Windows Internet Explorer 7, включены следующие параметры безопасности, специально предназначенные для .NET Framework:  
  
- **Свободный XAML**. Определяет, может ли Internet Explorer переходить к файлам, свободным [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]. (Варианты: "Включить", "Отключить" и "Запрашивать".)  
  
- **XAML-приложения браузера**. Определяет, может ли Internet Explorer переходить к и запускать XBAP. (Варианты: "Включить", "Отключить" и "Запрашивать".)  
  
 По умолчанию все эти параметры включены для зон " **Интернет**", " **Местная интрасеть**" и " **Доверенные сайты** " и отключены для зоны **ограниченных узлов** .  
  
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
 Элемент управления <xref:System.Windows.Controls.WebBrowser> WPF можно использовать для размещения веб-содержимого. Элемент управления <xref:System.Windows.Controls.WebBrowser> WPF служит оболочкой для базового элемента управления ActiveX WebBrowser. WPF обеспечивает некоторую поддержку защиты приложения при использовании элемента управления <xref:System.Windows.Controls.WebBrowser> WPF для размещения ненадежного веб-содержимого. Однако некоторые функции безопасности должны быть применены непосредственно приложениями с помощью элемента управления <xref:System.Windows.Controls.WebBrowser>. Дополнительные сведения об элементе управления ActiveX WebBrowser см. в разделе [WebBrowser Control обзоры и учебники](https://go.microsoft.com/fwlink/?LinkId=179388).  
  
> [!NOTE]
> Этот раздел также относится к элементу управления <xref:System.Windows.Controls.Frame>, так как он использует <xref:System.Windows.Controls.WebBrowser> для перехода к содержимому HTML.  
  
 Если элемент управления WPF <xref:System.Windows.Controls.WebBrowser> используется для размещения ненадежного веб-содержимого, приложение должно использовать <xref:System.AppDomain> частичного доверия для облегчения изоляции кода приложения от потенциально вредоносного кода HTML-скрипта. Это особенно верно, если приложение взаимодействует с размещенным скриптом с помощью метода <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> и свойства <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A>. Дополнительные сведения см. в разделе [Общие сведения о](./app-development/wpf-add-ins-overview.md)надстройках WPF.  
  
 Если приложение использует элемент управления WPF <xref:System.Windows.Controls.WebBrowser>, еще один способ повышения безопасности и устранения атак — включить элементы управления функциями Internet Explorer. Элементы управления функциями — это дополнения к Internet Explorer, позволяющие администраторам и разработчикам настраивать функции Internet Explorer и приложений, на которых размещается элемент управления ActiveX WebBrowser, который является элементом управления WPF <xref:System.Windows.Controls.WebBrowser>. Элементы управления функциями можно настраивать с помощью функции [коинтернетсетфеатуринаблед](https://go.microsoft.com/fwlink/?LinkId=179394) или изменяя значения в реестре. Дополнительные сведения об элементах управления функциями см. [в разделе Введение в элементы управления функциями](https://go.microsoft.com/fwlink/?LinkId=179390) и [элементы управления функциями Интернета](https://go.microsoft.com/fwlink/?LinkId=179392).  
  
 При разработке автономного приложения WPF, использующего элемент управления WPF <xref:System.Windows.Controls.WebBrowser>, WPF автоматически включает следующие элементы управления функциями для приложения.  
  
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
  
 Элементы управления функциями применяются процессом, создающим экземпляр объекта ActiveX WebBrowser. Таким образом, при создании автономного приложения, которое может переходить к ненадежному содержимому, следует рассмотреть возможность включения дополнительных элементов управления функциями.  
  
> [!NOTE]
> Эта рекомендация основана на общих рекомендациях по безопасности узлов MSHTML и SHDOCVW. Дополнительные сведения см. [в разделе вопросы и ответы по безопасности главного узла MSHTML: часть I из II](https://go.microsoft.com/fwlink/?LinkId=179396) и [часто задаваемые вопросы о безопасности узла MSHTML: часть II из II](https://go.microsoft.com/fwlink/?LinkId=179415).  
  
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
  
 При запуске приложения браузера XAML (XBAP) с частичным доверием, которое включает элемент управления WPF <xref:System.Windows.Controls.WebBrowser> в Windows Internet Explorer, WPF размещает элемент управления ActiveX WebBrowser в адресном пространстве процесса Internet Explorer. Так как элемент управления ActiveX WebBrowser размещается в процессе Internet Explorer, все элементы управления функциями для Internet Explorer также включены для элемента управления ActiveX WebBrowser.  
  
 XBAP-приложения, выполняющиеся в Internet Explorer, также получают более высокий уровень безопасности по сравнению с обычными автономными приложениями. Такая дополнительная безопасность обусловлена тем, что Internet Explorer и, следовательно, элемент управления ActiveX WebBrowser запускается в защищенном режиме по умолчанию на [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] и [!INCLUDE[win7](../../../includes/win7-md.md)]. Дополнительные сведения о защищенном режиме см. [в разделе понимание и работа в защищенном режиме Internet Explorer](https://go.microsoft.com/fwlink/?LinkId=179393).  
  
> [!NOTE]
> При попытке запустить XBAP, включающий элемент управления WPF <xref:System.Windows.Controls.WebBrowser> в браузере Firefox, в зоне Интернета будет выдано <xref:System.Security.SecurityException>. Это связано с политикой безопасности WPF.  
  
<a name="APTCA"></a>   
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Отключение сборок APTCA для клиентских приложений с частичным доверием  
 Если управляемые сборки устанавливаются в глобальный кэш сборок (GAC), они становятся полностью доверенными, поскольку пользователь должен предоставить явное разрешение на их установку. Поскольку они пользуются полным доверием, их могут использовать только полностью доверенные управляемые клиентские приложения. Чтобы разрешить приложениям с частичным доверием использовать их, они должны быть помечены <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA). Этим атрибутом могут быть помечены только сборки, которые были протестированы для подтверждения безопасности при выполнении в режиме частичного доверия.  
  
 Однако сборка APTCA может вызвать изъян в системе безопасности после установки в глобальный кэш сборок. После обнаружения уязвимости безопасности издатели сборок могут создавать обновления безопасности для решения проблем существующих установок и защиты установок, которые могут выполняться после выявления проблемы. Одним из вариантов обновления является удаление сборки, хотя это может нарушить работу других полностью доверенных клиентских приложений, использующих сборку.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] предоставляет механизм, с помощью которого сборку APTCA можно отключить для частично доверенных XBAP без удаления сборки APTCA.  
  
 Чтобы отключить сборку APTCA, необходимо создать специальный раздел реестра.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Пример приведен ниже.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Этот раздел содержит запись для сборки APTCA. Вам также потребуется создать значение в этом разделе, включающее или отключающее сборку. Ниже приведены сведения об этом значении.  
  
- Имя значения: **APTCA_FLAG**.  
  
- Тип значения: **REG_DWORD**.  
  
- Данные значения: **1** для отключения; **0** , чтобы включить.  
  
 Если сборку необходимо отключить для клиентских приложений с частичным доверием, можно написать обновление, создающее раздел реестра и значение.  
  
> [!NOTE]
> На сборки ядра .NET Framework не повлияло их отключение, поскольку они необходимы для запуска управляемых приложений. Поддержка отключения сборок APTCA в основном ориентирована на сторонние приложения.  
  
<a name="LooseContentSandboxing"></a>   
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Режим песочницы для свободных файлов XAML  
 Свободные файлы [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] — это файлы XAML только для разметки, которые не зависят от кода программной части, обработчика событий или сборки, зависящей от приложения. При переходе к свободным [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлам непосредственно из браузера они загружаются в песочнице безопасности на основе набора разрешений зоны Интернета по умолчанию.  
  
 Однако поведение безопасности отличается при переходе к свободным [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлам из <xref:System.Windows.Navigation.NavigationWindow> или <xref:System.Windows.Controls.Frame> в автономном приложении.  
  
 В обоих случаях свободный файл [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)], к которому осуществляется переход, наследует разрешения ведущего приложения. Однако такое поведение может быть нежелательно с точки зрения безопасности, особенно в том случае, если свободный [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файл был создан ненадежной или неизвестной сущностью. Этот тип содержимого известен как *внешнее содержимое*, и <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow> можно настроить таким образом, чтобы изолировать его при переходе к. Изоляция достигается путем присвоения свойству **сандбоксекстерналконтент** значения true, как показано в следующих примерах для <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow>.  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Этот параметр позволяет загружать внешнее содержимое в процесс, который отделен от процесса, содержащего приложение. Этот процесс ограничен набором разрешений зоны Интернета по умолчанию, что эффективно изолирует его от ведущего приложения и клиентского компьютера.  
  
> [!NOTE]
> Хотя переход к свободным [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлам из <xref:System.Windows.Navigation.NavigationWindow> или <xref:System.Windows.Controls.Frame> в автономном приложении реализован на основе инфраструктуры размещения браузера WPF, включающей в себя процесс PresentationHost, уровень безопасности немного меньше, чем при содержимое загружается непосредственно в Internet Explorer на [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] и [!INCLUDE[win7](../../../includes/win7-md.md)] (который по-прежнему будет использоваться в PresentationHost). Это обусловлено тем, что автономное приложение WPF, использующее веб-браузер, не предоставляет дополнительную функцию безопасности "Защищенный режим" Internet Explorer.  
  
<a name="BestPractices"></a>   
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Ресурсы для разработки приложений WPF, обеспечивающих безопасность  
 Ниже приведены некоторые дополнительные ресурсы, помогающие в разработке [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] приложений, повышающих безопасность:  
  
|Область|Ресурс|  
|----------|--------------|  
|Управляемый код|[Шаблоны и рекомендации по обеспечению безопасности приложений](https://go.microsoft.com/fwlink/?LinkId=117426)|  
|CAS|[Управление доступом для кода](../misc/code-access-security.md)|  
|ClickOnce|[Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)|  
|[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]|[Безопасность частичного доверия в WPF](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>См. также

- [Безопасность частичного доверия в WPF](wpf-partial-trust-security.md)
- [Стратегия безопасности WPF — безопасность платформы](wpf-security-strategy-platform-security.md)
- [Стратегия безопасности WPF — проектирование безопасности](wpf-security-strategy-security-engineering.md)
- [Шаблоны и рекомендации по обеспечению безопасности приложений](https://go.microsoft.com/fwlink/?LinkId=117426)
- [Управление доступом для кода](../misc/code-access-security.md)
- [Развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)
- [Общие сведения о языке XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
