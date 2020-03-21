---
title: Безопасность
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
ms.openlocfilehash: e0a56dcbf8d151fcb0d4f6271ecba15c0ff955a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174619"
---
# <a name="security-wpf"></a>Безопасность (WPF)
<a name="introduction"></a>При разработке автономных и размещенных в браузерах приложений Windows Presentation Foundation (WPF) необходимо учитывать модель безопасности. Автономные приложения WPF выполняются с неограниченными разрешениями (набор разрешений CAS**FullTrust),** независимо от того, развернуты ли они с помощью установки Windows (.msi), XCopy или ClickOnce. Развертывание автономных приложений WPF с частичным доверием с помощью ClickOnce не поддерживается. Однако полностью доверяемый хост-приложение может создать частичное доверие <xref:System.AppDomain> с помощью модели добавленной инфраструктуры .NET. Для получения дополнительной [WPF Add-Ins Overview](./app-development/wpf-add-ins-overview.md)информации см.  
  
 Приложения, размещенные в браузере WPF, размещаются Windows Internet Explorer или Firefox, и [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] могут быть либо приложениями для браузеров XAML (XBAPs), либо свободными документами Для получения дополнительной информации, [см.](./app-development/wpf-xaml-browser-applications-overview.md)  
  
 Приложения, размещенные в браузере WPF, выполняются в песочнице безопасности частичного доверия по умолчанию, которая ограничена набором разрешений**в Интернет-зоне** CAS по умолчанию. Это эффективно изолирует приложения, размещенные в браузере WPF, с клиентского компьютера так же, как можно ожидать, что типичные веб-приложения будут изолированы. Приложение XBAP может повысить привилегии вплоть до полного доверия в зависимости от зоны безопасности URL-адреса развертывания и конфигурации безопасности клиента. Дополнительные сведения см. в разделе [Безопасность частичного доверия в WPF](wpf-partial-trust-security.md).  
  
 На этой теме обсуждается модель безопасности для автономных и размещенных в браузере приложений Windows Presentation Foundation (WPF).  
  
 Этот раздел состоит из следующих подразделов.  
  
- [Безопасная навигация](#SafeTopLevelNavigation)  
  
- [Параметры безопасности программного обеспечения для просмотра веб-страниц](#InternetExplorerSecuritySettings)  
  
- [Элемент управления WebBrowser и элементы управления функциями](#webbrowser_control_and_feature_controls)  
  
- [Отключение сборок APTCA для клиентских приложений с частичным доверием](#APTCA)  
  
- [Режим песочницы для свободных файлов XAML](#LooseContentSandboxing)  
  
- [Ресурсы для разработки приложений WPF, обеспечивающих безопасность](#BestPractices)  
  
<a name="SafeTopLevelNavigation"></a>
## <a name="safe-navigation"></a>Безопасная навигация  
 Для XBAPs WPF выделяет два типа навигации: приложение и браузер.  
  
 *Навигация в приложении* — это навигация между элементами содержимого в пределах приложения, размещенного в браузере. *Навигация в браузере* — это навигация, изменяющая содержимое и URL-адрес расположения самого браузера. Взаимосвязь между навигацией приложений (обычно XAML) и навигацией браузера (обычно HTML) показана на следующей иллюстрации:
  
 ![Взаимосвязь между навигацией приложений и навигацией браузера.](./media/security-wpf/application-browser-navigation-relationship.png)  
  
 Тип содержимого, который считается безопасным для xBAP для навигации в основном определяется ли навигация приложения или навигации браузера используется.  
  
<a name="Application_Navigation_Security"></a>
### <a name="application-navigation-security"></a>Безопасность навигации в приложениях  
 Навигация приложения считается безопасной, если ее можно идентифицировать с пакетом URI, который поддерживает четыре типа содержимого:  
  
|Тип содержимого|Описание|Пример URI|  
|------------------|-----------------|-----------------|  
|Ресурс|Файлы, добавленные в проект с типом сборки **ресурса.**|`pack://application:,,,/MyResourceFile.xaml`|  
|Содержимое|Файлы, добавленные в проект с типом сборки **содержимого.**|`pack://application:,,,/MyContentFile.xaml`|  
|Исходный веб-сайт|Файлы, добавленные в проект с типом сборки **None.**|`pack://siteoforigin:,,,/MySiteOfOriginFile.xaml`|  
|Код приложения|Ресурсы XAML, имеющие скомпилированный код программной части.<br /><br /> -или-<br /><br /> Файлы XAML, добавленные в проект с типом сборки **Страницы.**|`pack://application:,,,/MyResourceFile` `.xaml`|  
  
> [!NOTE]
> Для получения дополнительной информации о файлах данных приложений и упаковке URIs [см.](./app-development/wpf-application-resource-content-and-data-files.md)  
  
 Файлы этих типов содержимого поддерживают навигацию, выполняемую пользователем или программно.  
  
- **Навигация, выполняемая пользователем**. Пользователь переходит, нажав <xref:System.Windows.Documents.Hyperlink> на элемент.  
  
- **Программная навигация**. Приложение перемещается без привлечения пользователя, например, <xref:System.Windows.Navigation.NavigationWindow.Source%2A?displayProperty=nameWithType> путем настройки свойства.  
  
<a name="Browser_Navigation_Security"></a>
### <a name="browser-navigation-security"></a>Безопасность навигации в браузере  
 Навигация в браузере считается безопасной только при выполнении следующих условий.  
  
- **Навигация, выполняемая пользователем**. Пользователь переходит, нажав <xref:System.Windows.Documents.Hyperlink> элемент, который <xref:System.Windows.Navigation.NavigationWindow>находится в пределах <xref:System.Windows.Controls.Frame>основного, а не в вложенных .  
  
- **Зона**. Содержимое, к которому выполняется переход, находится в Интернете или в локальной интрасети.  
  
- **Протокол**. Протокол используется либо **http**, **https,** **файл**, или **mailto**.  
  
 Если XBAP пытается перейти к содержимому таким образом, чтобы <xref:System.Security.SecurityException> не соответствовать этим условиям, a брошен.  
  
<a name="InternetExplorerSecuritySettings"></a>
## <a name="web-browsing-software-security-settings"></a>Параметры безопасности программного обеспечения для просмотра веб-страниц  
 Параметры безопасности компьютера определяют уровень доступа, который предоставляется программному обеспечению для просмотра веб-страниц. Программное обеспечение для просмотра веб-страниц включает в себя любое приложение или компонент, который использует [AIS WinINet](/windows/win32/wininet/portal) или [UrlMon,](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa767916(v=vs.85)) включая Internet Explorer и PresentationHost.exe.  
  
 Internet Explorer предоставляет механизм, с помощью которого можно настроить функциональность, которая может быть выполнена или из Internet Explorer, в том числе следующее:  
  
- Компоненты рамочно-зависимых компонентов .NET  
  
- элементы управления ActiveX и подключаемые модули;  
  
- Файлы для загрузки  
  
- Написание сценариев  
  
- Аутентификация пользователей  
  
 Коллекция функциональных возможностей, которые могут быть защищены таким образом, настроена на основе в зависимости от зоны для **Интернета,** **Интрасети,** **Доверенных Сайтов**и зон **ограниченных сайтов.** Ниже приведена процедура для настройки параметров безопасности.  
  
1. Откройте **панель управления**.  
  
2. Нажмите **сети и Интернета,** а затем нажмите **Интернет Параметры**.  
  
     Откроется диалоговое окно «Свойства веб-обозревателя».  
  
3. На вкладке **безопасности** выберите зону для настройки параметров безопасности.  
  
4. Нажмите кнопку **Пользовательского уровня.**  
  
     Появляется диалоговая коробка **«Настройки безопасности»,** и можно настроить настройки безопасности для выбранной зоны.  
  
     ![Скриншот, отображающий диалоговую коробку параметров безопасности.](./media/security-wpf/windows-presentation-foundation-security-settings.png)  
  
> [!NOTE]
> К диалоговому окну "Свойства обозревателя" можно также перейти из Internet Explorer. Нажмите **Инструменты,** а затем нажмите **Интернет Параметры**.  
  
 Начиная с Windows Internet Explorer 7, включены следующие параметры безопасности, специально предназначенные для рамочного соглашения .NET:  
  
- **Свободный XAML**. Контролирует, может ли Internet [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] Explorer перемещаться по файлам и потерять их. (Варианты: "Включить", "Отключить" и "Запрашивать".)  
  
- **XAML-приложения браузера**. Контролирует, может ли Internet Explorer перемещаться по XBAPs и запускать его. (Варианты: "Включить", "Отключить" и "Запрашивать".)  
  
 По умолчанию все эти параметры включены для **Интернета,** **локальных интрасетей**и зон **доверенных сайтов,** а также отключены для зоны **ограниченных сайтов.**  
  
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
 Контроль WPF <xref:System.Windows.Controls.WebBrowser> может использоваться для размещения веб-контента. Контроль WPF <xref:System.Windows.Controls.WebBrowser> обертывает базовый элемент управления WebBrowser ActiveX. WPF предоставляет некоторую поддержку для обеспечения <xref:System.Windows.Controls.WebBrowser> безопасности приложения при использовании управления WPF для размещения ненадежного веб-контента. Тем не менее, некоторые функции безопасности <xref:System.Windows.Controls.WebBrowser> должны быть применены непосредственно приложениями, использующими элемент управления. Для получения дополнительной информации о webBrowser ActiveX управления, см [Веббраузер управления обзоры и учебники](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752041(v=vs.85)).  
  
> [!NOTE]
> Этот раздел также относится к элементу <xref:System.Windows.Controls.Frame> управления, поскольку он использует для навигации <xref:System.Windows.Controls.WebBrowser> по HTML-контенту.  
  
 Если элемент <xref:System.Windows.Controls.WebBrowser> управления WPF используется для размещения ненадежного веб-контента, приложение должно использовать частичное доверие, <xref:System.AppDomain> чтобы помочь оградить код приложения от потенциально вредоносного кода HTML-скриптов. Это особенно верно, если ваше приложение взаимодействует с <xref:System.Windows.Controls.WebBrowser.InvokeScript%2A> размещенным <xref:System.Windows.Controls.WebBrowser.ObjectForScripting%2A> скриптом, используя метод и свойство. Для получения дополнительной [WPF Add-Ins Overview](./app-development/wpf-add-ins-overview.md)информации см.  
  
 Если приложение использует элемент <xref:System.Windows.Controls.WebBrowser> управления WPF, еще один способ повысить безопасность и смягчить атаки — включить элементы управления функциями Internet Explorer. Элементы управления — это дополнения к Internet Explorer, которые позволяют администраторам и разработчикам настраивать <xref:System.Windows.Controls.WebBrowser> функции Internet Explorer и приложений, в которых размещается управление WebBrowser ActiveX, которое управляет WPF. Элементы управления могут быть настроены с помощью функции [CoInternetSetFeature](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537168(v=vs.85)) или путем изменения значений в реестре. Для получения дополнительной информации о элементах [Internet Feature Controls](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/general-info/ee330720(v=vs.85))управления функциями [см.](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537184(v=vs.85))  
  
 Если вы разрабатываете отдельное приложение WPF, <xref:System.Windows.Controls.WebBrowser> использующем элемент управления WPF, WPF автоматически позволяет управлять следующими функциями для вашего приложения.  
  
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
  
 Элементы управления применяются в процессе мгновенного WebBrowser ActiveX объекта. Таким образом, при создании автономного приложения, которое может переходить к ненадежному содержимому, следует рассмотреть возможность включения дополнительных элементов управления функциями.  
  
> [!NOTE]
> Эта рекомендация основана на общих рекомендациях по безопасности узлов MSHTML и SHDOCVW. Для получения дополнительной информации, см [MSHTML Хост безопасности часто задаваемые вопросы: Часть I II](https://msrc-blog.microsoft.com/2009/04/02/the-mshtml-host-security-faq-part-i-of-ii/) и [MSHTML Хост безопасности частозасуми: Часть II](https://msrc-blog.microsoft.com/2009/04/03/the-mshtml-host-security-faq-part-ii-of-ii/)II .  
  
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
  
 Если вы запустите браузерное приложение XAML частичного доверия <xref:System.Windows.Controls.WebBrowser> (XBAP), которое включает в себя управление WPF в Windows Internet Explorer, WPF размещает управление WebBrowser ActiveX в адресном пространстве процесса Internet Explorer. Поскольку управление WebBrowser ActiveX размещается в процессе Internet Explorer, все элементы управления для Internet Explorer также включены для управления WebBrowser ActiveX.  
  
 XBAP-приложения, выполняющиеся в Internet Explorer, также получают более высокий уровень безопасности по сравнению с обычными автономными приложениями. Эта дополнительная безопасность объясняется тем, что Internet Explorer, и, следовательно, управление WebBrowser ActiveX, работает в защищенном режиме по умолчанию на Windows Vista и Windows 7. Для получения дополнительной информации о защищенном режиме [см. Понимание и работа в защищенном режиме Internet Explorer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/).  
  
> [!NOTE]
> Если вы попытаетесь запустить XBAP, <xref:System.Windows.Controls.WebBrowser> который включает в себя контроль WPF в Firefox, в то время как в интернет-зоне, <xref:System.Security.SecurityException> будет брошен. Это связано с политикой безопасности WPF.  
  
<a name="APTCA"></a>
## <a name="disabling-aptca-assemblies-for-partially-trusted-client-applications"></a>Отключение сборок APTCA для клиентских приложений с частичным доверием  
 При установке управляемых сборок в глобальный кэш сборки (GAC) они становятся полностью надежными, поскольку пользователь должен предоставить явное разрешение на их установку. Поскольку они пользуются полным доверием, их могут использовать только полностью доверенные управляемые клиентские приложения. Чтобы частично доверенные приложения могли использовать их, <xref:System.Security.AllowPartiallyTrustedCallersAttribute> они должны быть помечены (APTCA). Этим атрибутом могут быть помечены только сборки, которые были протестированы для подтверждения безопасности при выполнении в режиме частичного доверия.  
  
 Тем не менее, это возможно для сборки APTCA проявлять недостаток безопасности после установки в GAC . После обнаружения уязвимости безопасности издатели сборок могут создавать обновления безопасности для решения проблем существующих установок и защиты установок, которые могут выполняться после выявления проблемы. Одним из вариантов обновления является удаление сборки, хотя это может нарушить работу других полностью доверенных клиентских приложений, использующих сборку.  
  
 WPF предоставляет механизм, с помощью которого сборка APTCA может быть отключена для частично доверенных XBAPs без установки сборки APTCA.  
  
 Чтобы отключить сборку APTCA, необходимо создать специальный раздел реестра.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\<AssemblyFullName>, FileVersion=<AssemblyFileVersion>`  
  
 Пример приведен ниже.  
  
 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\policy\APTCA\aptcagac, Version=1.0.0.0, Culture=neutral, PublicKeyToken=215e3ac809a0fea7, FileVersion=1.0.0.0`  
  
 Этот раздел содержит запись для сборки APTCA. Вам также потребуется создать значение в этом разделе, включающее или отключающее сборку. Ниже приведены сведения об этом значении.  
  
- Значение Имя: **APTCA_FLAG**.  
  
- Тип значения: **REG_DWORD**.  
  
- Данные значений: **1** для отсутсвия; **0** для включения.  
  
 Если сборку необходимо отключить для клиентских приложений с частичным доверием, можно написать обновление, создающее раздел реестра и значение.  
  
> [!NOTE]
> Сборки основных рамок .NET не влияют на их отключение таким образом, поскольку они необходимы для запуска управляемых приложений. Поддержка отключения сборок APTCA в основном ориентирована на сторонние приложения.  
  
<a name="LooseContentSandboxing"></a>
## <a name="sandbox-behavior-for-loose-xaml-files"></a>Режим песочницы для свободных файлов XAML  
 Свободные [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] файлы — это файлы XAML только разметки, которые не зависят от какой-либо сборки кода, обработчика событий или конкретного приложения. Когда [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] свободные файлы перемещаются непосредственно из браузера, они загружаются в песочнице безопасности на основе набора разрешений в интернет-зоне по умолчанию.  
  
 Тем не менее, поведение [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] безопасности отличается, когда <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> свободные файлы перемещаются либо из или в отдельном приложении.  
  
 В обоих случаях [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] свободный файл, который перемещается, наследует разрешения его приложения хоста. Однако такое поведение может быть нежелательным с [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] точки зрения безопасности, особенно если свободный файл был создан сущностью, которому либо не доверяют, либо неизвестно. Этот тип содержимого известен как *внешнее содержимое,* и оба <xref:System.Windows.Controls.Frame> и <xref:System.Windows.Navigation.NavigationWindow> могут быть настроены, чтобы изолировать его при навигации. Изоляция достигается путем установки свойства **SandboxExternalContent** на <xref:System.Windows.Controls.Frame> истину, как показано в следующих примерах для и: <xref:System.Windows.Navigation.NavigationWindow>  
  
 [!code-xaml[SecurityOverviewSnippets#FrameMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window2.xaml#framemarkup)]  
  
 [!code-xaml[SecurityOverviewSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/SecurityOverviewSnippets/CS/Window1.xaml#navigationwindowmarkup)]  
  
 Этот параметр позволяет загружать внешнее содержимое в процесс, который отделен от процесса, содержащего приложение. Этот процесс ограничен набором разрешений зоны Интернета по умолчанию, что эффективно изолирует его от ведущего приложения и клиентского компьютера.  
  
> [!NOTE]
> Несмотря на [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] то, что <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> навигация для защиты файлов из отдельного приложения реализована на основе инфраструктуры хостинга браузера WPF, включающей процесс PresentationHost, уровень безопасности немного меньше, чем при загрузке содержимого непосредственно в Internet Explorer на Windows Vista и Windows 7 (который все равно будет осуществляться через PresentationHost). Это обусловлено тем, что автономное приложение WPF, использующее веб-браузер, не предоставляет дополнительную функцию безопасности "Защищенный режим" Internet Explorer.  
  
<a name="BestPractices"></a>
## <a name="resources-for-developing-wpf-applications-that-promote-security"></a>Ресурсы для разработки приложений WPF, обеспечивающих безопасность  
 Ниже приведены некоторые дополнительные ресурсы, чтобы помочь в разработке приложений WPF, которые способствуют безопасности:  
  
|Область|Ресурс|  
|----------|--------------|  
|Управляемый код|[Шаблоны и рекомендации по обеспечению безопасности приложений](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))|  
|CAS|[Безопасность доступа к коду](../misc/code-access-security.md)|  
|ClickOnce|[ClickOnce безопасности и развертывания](/visualstudio/deployment/clickonce-security-and-deployment)|  
|WPF|[WPF Частичная доверительная безопасность](wpf-partial-trust-security.md)|  
  
## <a name="see-also"></a>См. также раздел

- [WPF Частичная доверительная безопасность](wpf-partial-trust-security.md)
- [Стратегия безопасности WPF — безопасность платформы](wpf-security-strategy-platform-security.md)
- [Стратегия безопасности WPF — проектирование безопасности](wpf-security-strategy-security-engineering.md)
- [Шаблоны и рекомендации по обеспечению безопасности приложений](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))
- [Безопасность доступа к коду](../misc/code-access-security.md)
- [ClickOnce безопасности и развертывания](/visualstudio/deployment/clickonce-security-and-deployment)
- [Обзор XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)
