---
title: "Безопасность частичного доверия в WPF | Microsoft Docs"
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
  - "отладка приложений с частичным доверием"
  - "определение разрешений"
  - "функции требований безопасности"
  - "управление разрешениями"
  - "приложения с частичным доверием, отладка"
  - "безопасность частичного доверия"
  - "разрешения, обнаружение"
  - "разрешения, управление"
  - "Internet Explorer - параметры безопасности"
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
caps.latest.revision: 40
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 36
---
# Безопасность частичного доверия в WPF
<a name="introduction"></a> В общем случае, чтобы избежать злонамеренного повреждения, веб\-приложения не должны иметь прямой доступ к критическим системным ресурсам.  По умолчанию [!INCLUDE[TLA#tla_html](../../../includes/tlasharptla-html-md.md)] и клиентские языки скриптов не имеют доступа к критическим системным ресурсам.  Поскольку приложения [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)], реализованные в браузере, можно запускать из браузера, то они должны соответствовать аналогичному набору ограничений.  Для принудительного применения этих ограничений [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] использует и [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)], и [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] \(см. раздел [Стратегия безопасности WPF — безопасность платформы](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)\).  По умолчанию приложения, реализованные в браузере, запрашивают набор разрешений зоны Интернета [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)], независимо от того, запускаются ли они из Интернета, из локальной интрасети или с локального компьютера.  Приложения, имеющие не полный набор разрешений, выполняются "с частичным доверием".  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] предоставляет широкую поддержку того, чтобы при частичном доверии можно было безопасно использовать максимально возможную функциональность, и, как и [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)], обеспечивает поддержку программирования с использованием частичного доверия.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Поддержка частичного доверия функциями WPF](#WPF_Feature_Partial_Trust_Support)  
  
-   [Программирование с использованием частичного доверия](#Partial_Trust_Programming)  
  
-   [Управление разрешениями](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>   
## Поддержка частичного доверия функциями WPF  
 В следующей таблице перечислены функции высокого уровня [!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)], являющиеся безопасными для использования в пределах набора разрешений зоны Интернета.  
  
 Таблица 1. Безопасные в частичном доверии функции WPF  
  
|Область функций|Функция|  
|---------------------|-------------|  
|Общие|Окно браузера<br /><br /> Доступ к узлу источника<br /><br /> IsolatedStorage \(ограничение 512KB\)<br /><br /> Поставщики UIAutomation<br /><br /> Управление<br /><br /> Редакторы методов ввода \(IME\)<br /><br /> Перо планшета и рукописный ввод<br /><br /> Моделирование перетаскивания с помощью событий захвата и перемещения мыши<br /><br /> OpenFileDialog<br /><br /> Десериализация языка XAML \(с помощью XamlReader.Load\)|  
|Веб\-интеграция|Диалоговое окно загрузки браузера<br /><br /> Верхний уровень инициированной пользователем навигации<br /><br /> ссылки "mailto:"<br /><br /> Параметры универсального кода ресурса \(URI\)<br /><br /> HTTPWebRequest<br /><br /> Содержимое WPF, размещенное в IFRAME<br /><br /> Размещение HTML\-страниц одного веб\-узла с помощью элемента управления Frame<br /><br /> Размещение HTML\-страниц одного веб\-узла с помощью элемента управления WebBrowser<br /><br /> Веб\-службы \(ASMX\)<br /><br /> Веб\-службы \(использующие Windows Communication Foundation\)<br /><br /> Сценарии<br /><br /> Модель DOM|  
|Визуальные|2D и 3D<br /><br /> Анимация<br /><br /> Мультимедиа \(от узла источника и междоменное\)<br /><br /> Обработка изображений\/аудио\/видео|  
|Чтение|FlowDocuments<br /><br /> Документы XPS<br /><br /> Внедренные и системные шрифты<br /><br /> Шрифты CFF и TrueType|  
|Редактирование|Проверка орфографии<br /><br /> RichTextBox<br /><br /> Поддержка помещения в буфер обмена незашифрованного текста и рукописного ввода<br /><br /> Команда "Вставить" инициированная пользователем<br /><br /> Копирование выбранного содержимого|  
|Элементы управления|Общие элементы управления|  
  
 В этой таблице приводятся функции [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] высокого уровня.  Дополнительные сведения, о разрешениях, необходимых каждому элементу [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] см. в документах [!INCLUDE[TLA#tla_lhsdk](../../../includes/tlasharptla-lhsdk-md.md)].  Кроме того, для следующих функций имеются дополнительные сведения, касающиеся выполнения при частичном доверии, включающие некоторые особенности.  
  
-   [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] \(см. в разделе [Общие сведения о языке XAML \(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)\).  
  
-   Всплывающие окна \(см. разделе <xref:System.Windows.Controls.Primitives.Popup?displayProperty=fullName>\).  
  
-   Перетаскивание \(см. раздел [Общие сведения о перетаскивании](../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)\).  
  
-   Буфер обмена \(см. раздел <xref:System.Windows.Clipboard?displayProperty=fullName>\).  
  
-   Обработка изображений \(см. раздел <xref:System.Windows.Controls.Image?displayProperty=fullName>\).  
  
-   Сериализация \(см. раздел <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=fullName>, <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=fullName>\).  
  
-   Диалоговое окно открытия файла \(см. раздел <xref:Microsoft.Win32.OpenFileDialog?displayProperty=fullName>\).  
  
 В следующей таблице описываются функции [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], которые не являются безопасными для выполнения в пределах набора разрешений зоны Интернета.  
  
 Таблица 2. Не безопасные в частичном доверии функции WPF  
  
|Область функций|Функция|  
|---------------------|-------------|  
|Общие|Окна \(определенные приложением окна и диалоговые окна\)<br /><br /> SaveFileDialog<br /><br /> Файловая система<br /><br /> Доступ к реестру<br /><br /> Перетаскивание<br /><br /> Сериализация языка XAML \(с помощью XamlWriter.Save\)<br /><br /> Клиенты UIAutomation<br /><br /> Доступ к окну источника \(HwndHost\)<br /><br /> Полная поддержка управления речью<br /><br /> Взаимодействие с Windows Forms|  
|Визуальные|Эффекты для точечных рисунков<br /><br /> Кодировка изображения|  
|Редактирование|Копирование в буфер обмена формата RTF<br /><br /> Полная поддержка языка XAML|  
  
<a name="Partial_Trust_Programming"></a>   
## Программирование с использованием частичного доверия  
 Для приложений [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] код, превышающий набор разрешений по умолчанию, имеет другое поведение \(в зависимости от зоны безопасности\).  В некоторых случаях пользователю выдается предупреждение при попытке установки.  Пользователь может выбрать, продолжить или отменить установку.  В следующей таблице описывается поведение приложения в каждой зоне безопасности и указываются действия, необходимые, чтобы приложение получило полное доверие.  
  
|Зона безопасности|Поведение|Получение полного доверия|  
|-----------------------|---------------|-------------------------------|  
|Локальный компьютер|Автоматическое получение полного доверия|Никаких действий не требуется.|  
|Интрасеть и надежные сайты|Вывод диалогового окна с запросом о полном доверии|Заверьте модуль XBAP сертификатом, чтобы его источник отображался в диалоговом окне запроса.|  
|Internet|Сбой с сообщением "Доверие не предоставлено"|Заверьте модуль XBAP сертификатом.|  
  
> [!NOTE]
>  Поведение, приведенное в предыдущей таблице, относится к XBAP, не следующим модели доверенного развертывания ClickOnce.  
  
 В общем случае код, который может выходить за рамки доступных разрешений, вероятно, является общим кодом, который доступен как отдельным приложениям, так и приложениям, работающим в браузере.  [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] и [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] предлагают несколько технологий для таких случаев.  
  
<a name="Detecting_Permissions_using_CAS"></a>   
### Определение разрешений с помощью управления доступом для кода \(CAS\)  
 В некоторых случаях общий код в сборках библиотек может использоваться как отдельными приложениями, так и [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)].  В этих случаях код может выполнять функции, которые могут потребовать больше разрешений, чем позволяет набор разрешений, присвоенный приложению.  Приложение может определять, имеет ли оно определенные разрешения, используя безопасность [!INCLUDE[TLA#tla_winfx](../../../includes/tlasharptla-winfx-md.md)].  В частности, приложение может проверить, обладает ли оно определенным разрешением, вызвав метод <xref:System.Security.CodeAccessPermission.Demand%2A> для экземпляра нужного разрешения.  Это показано в следующем примере, имеющим код, который уточняет, имеет ли он имеет возможность сохранить файл на локальный диск:  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Если приложение не имеет нужных разрешений, вызов <xref:System.Security.CodeAccessPermission.Demand%2A> вызывает исключение безопасности.  В противном случае, разрешение было предоставлено.  `IsPermissionGranted` инкапсулирует это поведение и возвращает значения `true` или `false` соответственно.  
  
<a name="Graceful_Degradation_of_Functionality"></a>   
### Постепенное снижение функциональности  
 Возможность обнаружения, имеет ли код разрешения для выполнения необходимых ему действий является выгодной для кода, который может выполняться из различных зон.  Определение зоны — это полезная возможность, однако гораздо лучше предоставить выбор пользователю, если возможно.  Например, приложение полного доверия обычно позволяет пользователям создавать файлы в любом желаемом месте, в то время как приложение частичного доверия может создавать файлы только в изолированном хранилище.  Если код создания файла существует в сборке, которая совместно используется и приложениями с полным доверием \(отдельные приложения\), и приложениями с частичным доверием \(приложения, реализованные в браузере\), и нужно, чтобы оба приложения давали пользователям возможность создавать файлы, то до создания файла в соответствующем приложении общий код должен определить, выполняется ли он при частичном или полном доверии.  Это демонстрируется в следующем коде.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 В множестве случаев найти альтернативу частичному доверию можно.  
  
 В управляемой среде, такой как интрасеть, настраиваемые управляемые объектные структуры могут быть установлены через клиентскую базу в [!INCLUDE[TLA#tla_gac](../../../includes/tlasharptla-gac-md.md)].  Эти библиотеки могут выполнять код, который требует полного доверия, и на них можно ссылаться из приложений, которые допускают только частичное доверие, посредством <xref:System.Security.AllowPartiallyTrustedCallersAttribute> \(дополнительные сведения см. в разделах [Безопасность](../../../docs/framework/wpf/security-wpf.md) и [Стратегия безопасности WPF — безопасность платформы](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)\).  
  
<a name="Browser_Host_Detection"></a>   
### Определение узла браузера  
 Использование [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] для проверки разрешений является подходящим способом, если необходимо проверять на отдельные разрешения.  Однако следует отметить, что перехватывание исключений при использовании этого метода — это неотъемлемая часть нормальной работы. В общем случае не рекомендуется использовать такое поведение, это может повлиять на производительность.  Вместо этого, если [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] выполняется только в песочнице зоны Интернета, то можно использовать свойство <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=fullName>, которое возвращает значение true для [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
> [!NOTE]
>  Свойство <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A> распознает только, выполняется ли приложение в браузере, оно не может определить набор разрешений, с которым выполняется приложение.  
  
<a name="Managing_Permissions"></a>   
## Управление разрешениями  
 По умолчанию [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] выполняется с частичным доверием \(набор разрешений зоны Интернета по умолчанию\).  Однако, в зависимости от требований приложения, можно изменять набор разрешений по умолчанию.  Например, если [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] запускается из локальной интрасети, он может воспользоваться преимуществом расширенного набора разрешений. См. следующую таблицу.  
  
 Таблица 3. Разрешения локальной интрасети и Интернета  
  
|Разрешение|Атрибут|Локальная интрасеть \(LocalIntranet\)|Internet|  
|----------------|-------------|-------------------------------------------|--------------|  
|DNS.|Доступ к DNS\-серверам|Да|Нет|  
|Переменные среды|Прочитайте|Да|Нет|  
|Диалоговые окна файла|Откройте .|Да|Да|  
|Диалоговые окна файла|Unrestricted|Да|Нет|  
|Изолированное хранилище|Изоляция сборки по пользователю|Да|Нет|  
|Изолированное хранилище|Неизвестная изоляция|Да|Да|  
|Изолированное хранилище|Неограниченная квота для пользователя|Да|Нет|  
|Мультимедиа|Безопасное аудио, видео и изображения|Да|Да|  
|Печать|Печать по умолчанию|Да|Нет|  
|Печать|Безопасная печать|Да|Да|  
|Отражение|Эмиссия|Да|Нет|  
|Безопасность|Выполнение управляемого кода|Да|Да|  
|Безопасность|Утверждение предоставленных разрешений|Да|Нет|  
|Пользовательский интерфейс|Unrestricted|Да|Нет|  
|Пользовательский интерфейс|Безопасные окна высокого уровня|Да|Да|  
|Пользовательский интерфейс|Собственный буфер обмена|Да|Да|  
|браузер|Безопасная навигация по рамкам в HTML|Да|Да|  
  
> [!NOTE]
>  При частичном доверии действия "вырезать" и "вставить" допускаются, только если они инициированы пользователем.  
  
 Если требуется повысить уровень разрешений, нужно изменить параметры проекта и манифест приложения ClickOnce.  Дополнительные сведения см. в разделе [Общие сведения о приложениях браузера WPF XAML](../../../docs/framework/wpf/app-development/wpf-xaml-browser-applications-overview.md).  Также могут быть полезны следующие документы.  
  
-   [Mage.exe \(средство создания и редактирования манифеста\)](../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
-   [MageUI.exe \(средство создания и редактирования манифестов, графический клиент\)](../../../docs/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
-   [Защита приложений ClickOnce](../Topic/Securing%20ClickOnce%20Applications.md).  
  
 Если ваше приложение [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] требует полного доверия, можно использовать те же средства для предоставления запрошенных разрешений.  Однако приложение [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] получит полное доверие только в том случае, если оно установлено на локальном компьютере или запущено с локального компьютера, из интрасети или с URL\-адреса, перечисленного среди доверенных или разрешенных сайтов браузера.  Если приложение установлено из интрасети или с доверенного сайта, пользователь получит стандартное извещение ClickOnce, сообщающее о повышенных разрешениях.  Пользователь может выбрать, продолжить или отменить установку.  
  
 Кроме того, можно использовать модель доверенного развертывания ClickOnce для полностью доверенного развертывания из любой зоны безопасности.  Дополнительные сведения см. в разделах [Общие сведения о развертывании доверенных приложений](../Topic/Trusted%20Application%20Deployment%20Overview.md) и [Безопасность](../../../docs/framework/wpf/security-wpf.md).  
  
## См. также  
 [Безопасность](../../../docs/framework/wpf/security-wpf.md)   
 [Стратегия безопасности WPF — безопасность платформы](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)   
 [Стратегия безопасности WPF — проектирование безопасности](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)