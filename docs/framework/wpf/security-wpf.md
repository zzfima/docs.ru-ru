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
ms.openlocfilehash: 8d01e018e570a1ab530f476368d80f4082a73bda
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400788"
---
# <a name="security-wpf"></a>Безопасность (WPF)
<a name="introduction"></a>При разработке изолированных приложений Windows Presentation Foundation (WPF) и обозревателей, размещенных в браузере, необходимо учитывать модель безопасности. [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]автономные приложения выполняются с неограниченными разрешениями (набор разрешений**FULLTRUST** ЦС), а также развернут с помощью установщик Windows (. msi), XCOPY или ClickOnce. Развертывание автономных приложений WPF с частичным доверием с помощью ClickOnce не поддерживается. Однако ведущее приложение с полным доверием может создать частичное доверие <xref:System.AppDomain> с помощью модели надстройки .NET Framework. Дополнительные сведения см. в разделе [Общие сведения о](./app-development/wpf-add-ins-overview.md)надстройках WPF.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]приложения, размещенные в браузере, [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)] размещаются с помощью или Firefox и [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] могут быть [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] либо свободными документами. Дополнительные сведения см. в разделе [Общие сведения о приложениях браузера WPF XAML](./app-development/wpf-xaml-browser-applications-overview.md).  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]приложения, размещенные в браузере, выполняются в песочнице безопасности с частичным доверием по умолчанию, которая ограничена набором разрешений зоны**Интернета** CAS по умолчанию. Это эффективно изолирует [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] приложения, размещенные в браузере, от клиентского компьютера так же, как обычные веб-приложения будут изолированы. Приложение XBAP может повысить привилегии вплоть до полного доверия в зависимости от зоны безопасности URL-адреса развертывания и конфигурации безопасности клиента. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](wpf-partial-trust-security.md).  
  
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
 Для [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] следует[!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] отличать два типа навигации: приложение и браузер.  
  
 *Навигация в приложении* — это навигация между элементами содержимого в пределах приложения, размещенного в браузере. *Навигация в браузере* — это навигация, изменяющая содержимое и URL-адрес расположения самого браузера. Связь между навигацией между приложениями (обычно XAML) и навигацией в браузере (как правило, HTML) показана на следующем рисунке:
  
 ![Связь между навигацией приложения и навигацией в браузере.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 Тип содержимого, которое считается безопасным для [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] перехода к, в первую очередь определяется тем, используется ли Навигация по приложению или браузер.  
  
<a name="Application_Navigation_Security"></a>   
### <a name="application-navigation-security"></a>Безопасность навигации в приложениях  
 Навигация по приложениям считается надежной, если ее можно определить с помощью [!INCLUDE[TLA2#tla_uri](../../../includes/tla2sharptla-uri-md.md)]типа Pack, который поддерживает четыре типа содержимого:  
  
|Тип содержимого|Описание|Пример URI|  
|------------------|-----------------|-----------------|  
|Ресурс|Файлы, добавляемые в проект с типом построения " **ресурс**".|`pack://application:,,,/MyResourceFile.xaml`|  
|Content|Файлы, добавляемые в проект с типом сборки **содержимое**.|`pack://application:,,,/MyContentFile.xaml`|  
|Исходный веб-сайт|Файлы, добавляемые в проект с типом построения " **нет**".|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Код приложения|Ресурсы XAML, имеющие скомпилированный код программной части.<br /><br /> -или-<br /><br /> Файлы XAML, добавляемые в проект с типом сборки **страница**.|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
>  Дополнительные сведения о файлах данных приложения и пакете [!INCLUDE[TLA2#tla_uri#plural](../../../includes/tla2sharptla-urisharpplural-md.md)]см. в разделе [ресурсы приложения WPF, содержимое и файлы данных](./app-development/wpf-application-resource-content-and-data-files.md).  
  
 Файлы этих типов содержимого поддерживают навигацию, выполняемую пользователем или программно.  
  
- **Навигация, выполняемая пользователем**. Пользователь переходит по щелчку <xref:System.Windows.Documents.Hyperlink> элемента.  
  
- **Программная навигация**. Приложение переходит без участия пользователя, например путем установки <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> свойства.  
  
<a name="Browser_Navigation_Security"></a>   
### <a name="browser-navigation-security"></a>Безопасность навигации в браузере  
 Навигация в браузере считается безопасной только при выполнении следующих условий.  
  
- **Навигация, выполняемая пользователем**. Пользователь переходит по щелчку <xref:System.Windows.Documents.Hyperlink> элемента, который находится внутри основного <xref:System.Windows.Navigation.NavigationWindow>, а не вложенного <xref:System.Windows.Controls.Frame>.  
  
- **Зона**. Содержимое, к которому выполняется переход, находится в Интернете или в локальной интрасети.  
  
- **Протокол**. Используемый протокол — **http**, **HTTPS**, **File**или **mailto**.  
  
 При попытке перехода к содержимому способом, который не соответствует этим условиям <xref:System.Security.SecurityException> , создается исключение. [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)]  
  
<a name="InternetExplorerSecuritySettings"></a>   
## <a name="web-browsing-software-security-settings"></a>Параметры безопасности программного обеспечения для просмотра веб-страниц  
 Параметры безопасности компьютера определяют уровень доступа, который предоставляется программному обеспечению для просмотра веб-страниц. Программное обеспечение для обзора веб-страниц включает в себя любое приложение или компонент, использующие API [WinInet](https://go.microsoft.com/fwlink/?LinkId=179379) или [UrlMon](https://go.microsoft.com/fwlink/?LinkId=179383) , включая Internet Explorer и PresentationHost. exe.  
  
 [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)]предоставляет механизм, с помощью которого можно настроить функциональные возможности, которые разрешено выполнять в или из [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)], включая следующие:  
  
- Компоненты, зависящие от .NET Framework  
  
- элементы управления ActiveX и подключаемые модули;  
  
- Загрузки  
  
- Скрипты  
  
- проверка подлинности пользователя.  
  
 Набор функциональных возможностей, которые могут быть защищены таким образом, настраивается для каждой зоны в зонах " **Интернет**", "интрасеть", " **Доверенные сайты**" и " **ограниченные сайты** ". Ниже приведена процедура для настройки параметров безопасности.  
  
1. Откройте **панель управления**.  
  
2. Щелкните **сеть и Интернет** , а затем выберите **Свойства обозревателя**.  
  
     Откроется диалоговое окно «Свойства веб-обозревателя».  
  
3. На вкладке **Безопасность** выберите зону, для которой необходимо настроить параметры безопасности.  
  
4. Нажмите кнопку **Пользовательский уровень** .  
  
     Откроется диалоговое окно **Параметры безопасности** , в котором можно настроить параметры безопасности для выбранной зоны.  
  
     ![Снимок экрана, на котором показано диалоговое окно "Параметры безопасности".](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
>  К диалоговому окну "Свойства обозревателя" можно также перейти из Internet Explorer. В меню **Сервис** выберите пункт **Свойства обозревателя**.  
  
 Начиная с [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)], включены следующие параметры безопасности, специально предназначенные для .NET Framework:  
  
- **Свободный XAML**. Определяет, [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] можно ли переходить к [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлам и свободно просматривать их. (Варианты: "Включить", "Отключить" и "Запрашивать".)  
  
- **XAML-приложения браузера**. Определяет, [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] Возможен ли переход к и [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]запуск. (Варианты: "Включить", "Отключить" и "Запрашивать".)  
  
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
 Элемент управления <xref:System.Windows.Controls.WebBrowser> WPF можно использовать для размещения веб-содержимого. Элемент управления <xref:System.Windows.Controls.WebBrowser> WPF заключает в оболочку базовый элемент управления ActiveX WebBrowser. WPF обеспечивает некоторую поддержку защиты приложения при использовании элемента управления WPF <xref:System.Windows.Controls.WebBrowser> для размещения ненадежного веб-содержимого. Однако некоторые функции безопасности должны быть применены непосредственно приложениями с помощью <xref:System.Windows.Controls.WebBrowser> элемента управления. Дополнительные сведения об элементе управления ActiveX WebBrowser см. в разделе [WebBrowser Control обзоры и учебники](https://go.microsoft.com/fwlink/?LinkId=179388).  
  
> [!NOTE]
>  Этот раздел также применяется к <xref:System.Windows.Controls.Frame> элементу управления, так как он <xref:System.Windows.Controls.WebBrowser> использует для перехода к содержимому HTML.  
  
 Если элемент управления <xref:System.Windows.Controls.WebBrowser> WPF используется для размещения ненадежного веб-содержимого, приложение должно использовать частичное доверие <xref:System.AppDomain> , чтобы изолировать код приложения от потенциально вредоносного кода HTML-скрипта. Это особенно верно, если приложение взаимодействует с размещенным скриптом с помощью <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> метода <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> и свойства. Дополнительные сведения см. в разделе [Общие сведения о](./app-development/wpf-add-ins-overview.md)надстройках WPF.  
  
 Если приложение использует элемент управления WPF <xref:System.Windows.Controls.WebBrowser> , другим способом повышения безопасности и устранения атак является включение элементов управления функциями Internet Explorer. Элементы управления функциями — это дополнения к Internet Explorer, позволяющие администраторам и разработчикам настраивать функции Internet Explorer и приложений, на которых размещается элемент <xref:System.Windows.Controls.WebBrowser> управления ActiveX WebBrowser, который является элементом управления WPF. Элементы управления функциями можно настраивать с помощью функции [коинтернетсетфеатуринаблед](https://go.microsoft.com/fwlink/?LinkId=179394) или изменяя значения в реестре. Дополнительные сведения об элементах управления функциями см. [в разделе Введение в элементы управления функциями](https://go.microsoft.com/fwlink/?LinkId=179390) и [элементы управления функциями Интернета](https://go.microsoft.com/fwlink/?LinkId=179392).  
  
 При разработке автономного приложения WPF, использующего элемент управления WPF <xref:System.Windows.Controls.WebBrowser> , WPF автоматически включает следующие элементы управления функциями для приложения.  
  
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
>  Эта рекомендация основана на общих рекомендациях по безопасности узлов MSHTML и SHDOCVW. Дополнительные сведения см. в [разделе вопросы и ответы по безопасности главного узла MSHTML: Часть I из II](https://go.microsoft.com/fwlink/?LinkId=179396) и [часто задаваемые вопросы по безопасности узла MSHTML: Часть II из II](https://go.microsoft.com/fwlink/?LinkId=179415).  
  
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
  
 При выполнении частичного доверия [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] , включающего элемент управления WPF <xref:System.Windows.Controls.WebBrowser> в [!INCLUDE[TLA#tla_iegeneric](../../../includes/tlasharptla-iegeneric-md.md)], в WPF размещается элемент управления ActiveX WebBrowser в адресном пространстве процесса Internet Explorer. Так как элемент управления ActiveX WebBrowser размещается [!INCLUDE[TLA2#tla_iegeneric](../../../includes/tla2sharptla-iegeneric-md.md)] в процессе, все элементы управления функциями для Internet Explorer также включены для элемента управления ActiveX WebBrowser.  
  
 XBAP-приложения, выполняющиеся в Internet Explorer, также получают более высокий уровень безопасности по сравнению с обычными автономными приложениями. Такая дополнительная безопасность заключается в том, что Internet Explorer и, следовательно, элемент управления ActiveX WebBrowser по умолчанию [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] работает в защищенном режиме в и. [!INCLUDE[win7](../../../includes/win7-md.md)] Дополнительные сведения о защищенном режиме см. [в разделе понимание и работа в защищенном режиме Internet Explorer](https://go.microsoft.com/fwlink/?LinkId=179393).  
  
> [!NOTE]
>  При попытке запустить XBAP, включающий элемент управления WPF <xref:System.Windows.Controls.WebBrowser> в браузере Firefox, в зоне <xref:System.Security.SecurityException> Интернета будет создано исключение. Это связано с политикой безопасности WPF.  
  
<a name="APTCA"></a>   
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Отключение сборок APTCA для клиентских приложений с частичным доверием  
 Когда управляемые сборки устанавливаются в [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)], они становятся полностью доверенными, поскольку пользователь должен предоставить явное разрешение на их установку. Поскольку они пользуются полным доверием, их могут использовать только полностью доверенные управляемые клиентские приложения. Чтобы разрешить приложениям с частичным доверием использовать их, они должны быть помечены <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибутом (APTCA). Этим атрибутом могут быть помечены только сборки, которые были протестированы для подтверждения безопасности при выполнении в режиме частичного доверия.  
  
 Однако сборка APTCA может вызвать изъян в системе безопасности после установки в [!INCLUDE[TLA2#tla_gac](../../../includes/tla2sharptla-gac-md.md)]. После обнаружения уязвимости безопасности издатели сборок могут создавать обновления безопасности для решения проблем существующих установок и защиты установок, которые могут выполняться после выявления проблемы. Одним из вариантов обновления является удаление сборки, хотя это может нарушить работу других полностью доверенных клиентских приложений, использующих сборку.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]предоставляет механизм, с помощью которого сборку APTCA можно отключить для частичного доверия [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] без удаления сборки APTCA.  
  
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
>  На сборки ядра .NET Framework не повлияло их отключение, поскольку они необходимы для запуска управляемых приложений. Поддержка отключения сборок APTCA в основном ориентирована на сторонние приложения.  
  
<a name="LooseContentSandboxing"></a>   
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Режим песочницы для свободных файлов XAML  
 Свободные [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлы — это файлы XAML только для разметки, которые не зависят от кода программной части, обработчика событий или сборки конкретного приложения. При переходе к свободным [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлам непосредственно из браузера они загружаются в песочнице безопасности на основе набора разрешений зоны Интернета по умолчанию.  
  
 Однако поведение безопасности отличается при переходе к свободным [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлам из <xref:System.Windows.Navigation.NavigationWindow> или <xref:System.Windows.Controls.Frame> в автономном приложении.  
  
 В обоих случаях свободный [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файл, к которому осуществляется переход, наследует разрешения ведущего приложения. Однако такое поведение может быть нежелательно с точки зрения безопасности, особенно если свободный [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файл был создан ненадежной или неизвестной сущностью. Этот тип содержимого называется *внешним содержимым*, и его <xref:System.Windows.Navigation.NavigationWindow> можно настроить <xref:System.Windows.Controls.Frame> таким образом, чтобы изолировать его при переходе к. Изоляция достигается путем присвоения свойству **сандбоксекстерналконтент** значения true, как показано в следующих примерах <xref:System.Windows.Controls.Frame> для <xref:System.Windows.Navigation.NavigationWindow>и:  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Этот параметр позволяет загружать внешнее содержимое в процесс, который отделен от процесса, содержащего приложение. Этот процесс ограничен набором разрешений зоны Интернета по умолчанию, что эффективно изолирует его от ведущего приложения и клиентского компьютера.  
  
> [!NOTE]
>  Несмотря на то, что [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] переход на свободные файлы <xref:System.Windows.Navigation.NavigationWindow> из <xref:System.Windows.Controls.Frame> или в автономном приложении реализуется на основе инфраструктуры размещения браузера WPF, включающей в себя процесс PresentationHost, уровень безопасности немного меньше, чем, когда содержимое загружается непосредственно в Internet [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] Explorer [!INCLUDE[win7](../../../includes/win7-md.md)] в и (что по-прежнему выполняется через PresentationHost). Это обусловлено тем, что автономное приложение WPF, использующее веб-браузер, не предоставляет дополнительную функцию безопасности "Защищенный режим" Internet Explorer.  
  
<a name="BestPractices"></a>   
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Ресурсы для разработки приложений WPF, обеспечивающих безопасность  
 Ниже приведены некоторые дополнительные ресурсы, помогающие в [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] разработке приложений, повышающих безопасность.  
  
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
- [Общие сведения о языке XAML (WPF)](./advanced/xaml-overview-wpf.md)
