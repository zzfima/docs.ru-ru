---
title: Безопасность частичного доверия в WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- partial trust security [WPF]
- detecting permissions [WPF]
- security settings for Internet Explorer [WPF]
- partial trust applications [WPF], debugging
- permissions [WPF], managing
- debugging partial trust applications [WPF]
- permissions [WPF], detecting
- feature security requirements [WPF]
- managing permissions [WPF]
ms.assetid: ef2c0810-1dbf-4511-babd-1fab95b523b5
ms.openlocfilehash: 683d0a28fa151cf2116b4125dfb7a604605c7c4a
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972240"
---
# <a name="wpf-partial-trust-security"></a>Безопасность частичного доверия в WPF
<a name="introduction"></a> Как правило, интернет-приложениям следует ограничить прямой доступ к критическим системным ресурсам, чтобы избежать злонамеренного повреждения. По умолчанию HTML и языки сценариев на стороне клиента не могут получить доступ к критическим системным ресурсам. Поскольку приложения, размещаемые в браузере Windows Presentation Foundation (WPF), можно запускать из браузера, они должны соответствовать аналогичному набору ограничений. Чтобы применить эти ограничения, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] полагается на систему управления доступом для кода (CAS) и ClickOnce (см. раздел [стратегия безопасности WPF — безопасность платформы](wpf-security-strategy-platform-security.md)). По умолчанию приложения, размещенные в браузере, запрашивают набор разрешений ЦС зоны Интернета, независимо от того, были ли они запущены из Интернета, из локальной интрасети или локального компьютера. Приложения, выполняющиеся с набором разрешений меньшим, чем полный набор, называют выполняющимися с частичным доверием.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]предоставляет обширную поддержку, позволяющую безопасно использовать как можно больше функциональных возможностей при частичном доверии, а также с CAS обеспечивает дополнительную поддержку для программирования с частичным доверием.  
  
 В этом разделе содержатся следующие подразделы.  
  
- [Поддержка частичного доверия функциями WPF](#WPF_Feature_Partial_Trust_Support)  
  
- [Программирование в режиме частичного доверия](#Partial_Trust_Programming)  
  
- [Управление разрешениями](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>   
## <a name="wpf-feature-partial-trust-support"></a>Поддержка частичного доверия функциями WPF  
 В следующей таблице перечислены высокоуровневые функции Windows Presentation Foundation (WPF), которые можно использовать в ограничениях набора разрешений зоны Интернета.  
  
 Таблица 1. Функции WPF, которые являются надежными в режиме частичного доверия  
  
|Область функции|Компонент|  
|------------------|-------------|  
|Общие|Окно обозревателя<br /><br /> Доступ к исходному сайту<br /><br /> IsolatedStorage (ограничение 512 КБ)<br /><br /> Поставщики UIAutomation<br /><br /> Система команд<br /><br /> Редакторы метода ввода (IME)<br /><br /> Перо планшетного компьютера и рукописный ввод<br /><br /> Моделирование перетаскивания с помощью событий захвата и перемещения мыши<br /><br /> OpenFileDialog<br /><br /> Десериализация XAML (посредством XamlReader.Load)|  
|Веб-интеграция|Диалоговое окно загрузки браузера<br /><br /> Навигация верхнего уровня, инициированная пользователем<br /><br /> mailto:links<br /><br /> Параметры универсального идентификатора ресурса (URI)<br /><br /> HTTPWebRequest<br /><br /> Содержимое WPF, размещенное в IFRAME<br /><br /> Размещение HTML-страниц одного веб-сайта с помощью Frame<br /><br /> Размещение HTML-страниц одного веб-сайта с помощью WebBrowser<br /><br /> Веб-службы (ASMX-файлы)<br /><br /> Веб-службы (с помощью Windows Communication Foundation)<br /><br /> Скрипты<br /><br /> Модель DOM|  
|Визуальные элементы|2D- и 3D-графика<br /><br /> Анимация<br /><br /> Мультимедиа (исходный сайт и междоменные)<br /><br /> Обработка изображений/аудио/видео|  
|Чтение|FlowDocument<br /><br /> XPS-документы<br /><br /> Внедренные и системные шрифты<br /><br /> Шрифты CFF и TrueType|  
|Редактирование|Проверка орфографии<br /><br /> RichTextBox<br /><br /> Поддержка буфера обмена для обычного текста и рукописного ввода<br /><br /> Вставка, инициированная пользователем<br /><br /> Копирование выделенного содержимого|  
|Элементы управления|Общие элементы управления|  
  
 В [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] этой таблице описаны функции высокого уровня. Для получения более подробных сведений в пакете средств разработки программного обеспечения (SDK) для Windows задокументированы разрешения, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)]необходимые для каждого члена в. Кроме того, следующие функции содержат более подробные сведения, касающиеся выполнения при частичном доверии, включая некоторые особые аспекты.  
  
- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)](см. раздел [Общие сведения о XAML (WPF)](./advanced/xaml-overview-wpf.md)).  
  
- Всплывающие окна ( <xref:System.Windows.Controls.Primitives.Popup?displayProperty=nameWithType>см.).  
  
- Перетаскивание (см. раздел [Общие сведения о перетаскивании](./advanced/drag-and-drop-overview.md)).  
  
- Буфер обмена ( <xref:System.Windows.Clipboard?displayProperty=nameWithType>см. раздел).  
  
- Создание образов (см <xref:System.Windows.Controls.Image?displayProperty=nameWithType>.).  
  
- Сериализация (см <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>. <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=nameWithType>,).  
  
- Диалоговое окно «Открытие файла <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>» (см. раздел).  
  
 В следующей таблице [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] перечислены функции, которые ненадежны для выполнения в пределах набора разрешений зоны Интернета.  
  
 Таблица 2. Функции WPF, которые не являются надежными при частичном доверии  
  
|Область функции|Компонент|  
|------------------|-------------|  
|Общие|Окно (определенные приложением окна и диалоговые окна)<br /><br /> SaveFileDialog<br /><br /> Файловая система<br /><br /> Доступ к реестру<br /><br /> Перетаскивание<br /><br /> Сериализация XAML (через XamlWriter.Save)<br /><br /> Клиенты UIAutomation<br /><br /> Доступ к исходному окну (HwndHost)<br /><br /> Полная поддержка управления речью<br /><br /> Взаимодействие с Windows Forms|  
|Визуальные элементы|Эффекты для точечных рисунков<br /><br /> Кодирование изображений|  
|Редактирование|Буфер обмена формата RTF<br /><br /> Полная поддержка XAML|  
  
<a name="Partial_Trust_Programming"></a>   
## <a name="partial-trust-programming"></a>Программирование в режиме частичного доверия  
 Для [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] приложений код, превышающий набор разрешений по умолчанию, будет иметь различное поведение в зависимости от зоны безопасности. В некоторых случаях пользователь получит предупреждение при попытке установить приложение. Пользователь может выбрать продолжение или отмену установки. В следующей таблице описаны поведение приложения для каждой зоны безопасности и действия, необходимые для получения приложением полного доверия.  
  
|Зона безопасности|Поведение|Получение полного доверия|  
|-------------------|--------------|------------------------|  
|Локальный компьютер|Автоматическое получение полного доверия|Никаких действий не требуется.|  
|Интрасеть и надежные веб-сайты|Запрос полного доверия|Подпишите приложение XBAP с помощью сертификата, чтобы пользователь видел источник в запросе.|  
|Интернет|Сбой с сообщением "Доверие не оказано"|Подпишите приложение XBAP с помощью сертификата.|  
  
> [!NOTE]
>  Поведение, описанное в предыдущей таблице, относится к приложениям XBAP с полным доверием, не следующим модели доверенного развертывания ClickOnce.  
  
 В общем случае код, который может превышать допустимые разрешения, вероятнее всего, является общим кодом, который совместно используется автономными и браузерными приложениями. CAS и [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] предлагают несколько методов для управления этим сценарием.  
  
<a name="Detecting_Permissions_using_CAS"></a>   
### <a name="detecting-permissions-using-cas"></a>Определение разрешений с помощью CAS  
 В некоторых ситуациях общий код в сборках библиотеки может использоваться как автономными приложениями, так и [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)]. В этих случаях код может выполнять функции, которые могут потребовать больше разрешений, чем позволяет набор разрешений, присвоенный приложению. Приложение может определить, имеет ли оно определенные разрешения с помощью Microsoft .NETной безопасности платформы. В частности, он может проверить наличие определенного разрешения, вызвав <xref:System.Security.CodeAccessPermission.Demand%2A> метод для экземпляра требуемого разрешения. Это показано в следующем примере, который содержит код, запрашивающий возможность сохранить файл на локальный диск.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Если приложение не имеет нужных разрешений, вызов метода <xref:System.Security.CodeAccessPermission.Demand%2A> вызывает исключение безопасности. В противном случае разрешение будет предоставлено. `IsPermissionGranted`Инкапсулирует это поведение и возвращает `true` или `false` соответственно.  
  
<a name="Graceful_Degradation_of_Functionality"></a>   
### <a name="graceful-degradation-of-functionality"></a>Постепенное снижение функциональности  
 Возможность обнаружения у кода разрешений на выполнение действия представляет интерес для кода, который может выполняться из разных зон. Обнаружение зоны — это один из аспектов, однако рекомендуется по возможности предоставить пользователю альтернативу. Например, приложение с полным доверием обычно позволяет пользователям создавать файлы в любом расположении, тогда как приложение с частичным доверием может создавать файлы только в изолированном хранилище. Если код для создания файла существует в сборке, которая совместно используется приложениями с полным доверием (автономными) и приложениями с частичным доверием (размещенными в браузере), и оба приложения должны обеспечивать функцию создания файлов пользователем, общий код должен определить, выполняется ли он в режиме частичного или полного доверия перед созданием файла в соответствующем расположении. Оба варианта демонстрируются в следующем коде.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 Во многих случаях вы сможете найти альтернативу частичному доверию.  
  
 В управляемой среде, такой как интрасеть, пользовательские управляемые платформы можно установить на клиентской базе в глобальный кэш сборок (GAC). Эти библиотеки могут выполнять код, требующий полного доверия, и ссылаться на них из приложений, которые разрешают только частичное доверие с помощью <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (дополнительные сведения см. в статье [безопасность](security-wpf.md) и [стратегия безопасности WPF — безопасность платформы](wpf-security-strategy-platform-security.md)).  
  
<a name="Browser_Host_Detection"></a>   
### <a name="browser-host-detection"></a>Обнаружение узла браузера  
 Использование CAS для проверки разрешений является подходящим способом, если необходимо проверить на наличие разрешения. Тем не менее эта методика зависит от перехвата исключений в рамках нормальной обработки, что не рекомендуется в общем и может вызывать проблемы производительности. Вместо этого, если [!INCLUDE[TLA#tla_xbap](../../../includes/tlasharptla-xbap-md.md)] выполняется только в песочнице зоны Интернета, можно <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> использовать свойство, которое возвращает значение true для [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)].  
  
> [!NOTE]
>  <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A>различаются только приложения, выполняемые в браузере, а не набор разрешений, с которыми работает приложение.  
  
<a name="Managing_Permissions"></a>   
## <a name="managing-permissions"></a>Управление разрешениями  
 По умолчанию [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] выполните команду с частичным доверием (набор разрешений зоны Интернета по умолчанию). Тем не менее в зависимости от требований приложения можно изменить набор разрешений по умолчанию. Например, если [!INCLUDE[TLA2#tla_xbap#plural](../../../includes/tla2sharptla-xbapsharpplural-md.md)] запускается из локальной интрасети, она может воспользоваться преимуществами расширенного набора разрешений, как показано в следующей таблице.  
  
 Таблица 3. Интрасеть и разрешения в Интернете  
  
|Разрешение|Атрибут|LocalIntranet|Интернет|  
|----------------|---------------|-------------------|--------------|  
|DNS|Доступ к DNS-серверам|Да|Нет|  
|Переменные среды|Чтение|Да|Нет|  
|Диалоговые окна для работы с файлами|Открыть|Да|Да|  
|Диалоговые окна для работы с файлами|Без ограничений|Да|Нет|  
|Изолированное хранилище|Изоляция сборки по пользователю|Да|Нет|  
|Изолированное хранилище|Неизвестная изоляция|Да|Да|  
|Изолированное хранилище|Неограниченная квота для пользователя|Да|Нет|  
|Мультимедиа|Безопасные аудио-, видеоданные и изображения|Да|Да|  
|Печать|Печать по умолчанию|Да|Нет|  
|Печать|Безопасная печать|Да|Да|  
|Отражение|Вывод|Да|Нет|  
|Безопасность|Выполнение управляемого кода|Да|Да|  
|Безопасность|Утверждение предоставленных разрешений|Да|Нет|  
|Пользовательский интерфейс|Без ограничений|Да|Нет|  
|Пользовательский интерфейс|Безопасные окна верхнего уровня|Да|Да|  
|Пользовательский интерфейс|Собственный буфер обмена|Да|Да|  
|Веб-браузер|Безопасная навигация по фреймам в HTML|Да|Да|  
  
> [!NOTE]
>  Вырезание и вставка разрешены только в режиме частичного доверия при инициации пользователем.  
  
 Если вам требуется повысить уровень разрешений, необходимо изменить параметры проекта и манифест приложения ClickOnce. Дополнительные сведения см. в разделе [Общие сведения о приложениях браузера WPF XAML](./app-development/wpf-xaml-browser-applications-overview.md). Следующие документы также могут быть полезны.  
  
- [Mage.exe (средство создания и редактирования манифеста)](../tools/mage-exe-manifest-generation-and-editing-tool.md)  
  
- [MageUI.exe (средство создания и редактирования манифестов, графический клиент)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
  
- [Защита приложений ClickOnce](/visualstudio/deployment/securing-clickonce-applications)  
  
 [!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] Если требуется полное доверие, можно использовать те же средства для увеличения запрошенных разрешений. Хотя при установке и запуске на локальном компьютере, интрасети или URL-адресе, указанном в списке доверенных или разрешенных сайтов браузера, будетполученотолькополноедоверие.[!INCLUDE[TLA2#tla_xbap](../../../includes/tla2sharptla-xbap-md.md)] Если приложение установлено из интрасети или с доверенного сайта, пользователь получит стандартный запрос ClickOnce, уведомляющий о повышенных разрешениях. Пользователь может выбрать продолжение или отмену установки.  
  
 Кроме того, модель доверенного развертывания ClickOnce можно использовать для полностью доверенного развертывания из любой зоны безопасности. Дополнительные сведения см. в разделе [Общие сведения о развертывании доверенных приложений](/visualstudio/deployment/trusted-application-deployment-overview) и [Безопасность](security-wpf.md).  
  
## <a name="see-also"></a>См. также

- [Безопасность](security-wpf.md)
- [Стратегия безопасности WPF — безопасность платформы](wpf-security-strategy-platform-security.md)
- [Стратегия безопасности WPF — проектирование безопасности](wpf-security-strategy-security-engineering.md)
