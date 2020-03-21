---
title: Частичная доверительная безопасность
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
ms.openlocfilehash: 99c7d9cfae2b137053ca77d9e3d7055b4674ce5b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174580"
---
# <a name="wpf-partial-trust-security"></a>Безопасность частичного доверия в WPF
<a name="introduction"></a> Как правило, интернет-приложениям следует ограничить прямой доступ к критическим системным ресурсам, чтобы избежать злонамеренного повреждения. По умолчанию html и клиентские языки скриптов не могут получить доступ к критически важным системным ресурсам. Поскольку приложения, размещенные в браузере Для Windows Presentation Foundation (WPF), могут быть запущены из браузера, они должны соответствовать аналогичному набору ограничений. Для обеспечения соблюдения этих ограничений WPF опирается как на Code Access Security (CAS), так и на ClickOnce (см. [Стратегию безопасности WPF - Platform Security).](wpf-security-strategy-platform-security.md) По умолчанию приложения, размещенные в браузере, запрашивают в интернет-зоне CAS набор разрешений, независимо от того, запускаются ли они из Интернета, локальной интрасети или локального компьютера. Приложения, выполняющиеся с набором разрешений меньшим, чем полный набор, называют выполняющимися с частичным доверием.  
  
 WPF предоставляет широкий спектр поддержки для обеспечения того, чтобы как можно больше функциональных возможностей можно было безопасно использовать в частичном доверии, и наряду с CAS, обеспечивает дополнительную поддержку для частичного программирования доверия.  
  
 Этот раздел состоит из следующих подразделов.  
  
- [Поддержка частичного доверия функциями WPF](#WPF_Feature_Partial_Trust_Support)  
  
- [Программирование в режиме частичного доверия](#Partial_Trust_Programming)  
  
- [Управление разрешениями](#Managing_Permissions)  
  
<a name="WPF_Feature_Partial_Trust_Support"></a>
## <a name="wpf-feature-partial-trust-support"></a>Поддержка частичного доверия функциями WPF  
 В следующей таблице перечислены функции высокого уровня Фонда презентаций Windows (WPF), которые безопасны для использования в пределах набора разрешений зоны Интернета.  
  
 Таблица 1. Функции WPF, которые являются безопасными в режиме частичного доверия  
  
|Область функций|Компонент|  
|------------------|-------------|  
|Общие сведения|Окно обозревателя<br /><br /> Доступ к исходному сайту<br /><br /> IsolatedStorage (ограничение 512 КБ)<br /><br /> Поставщики UIAutomation<br /><br /> Система команд<br /><br /> Редакторы метода ввода (IME)<br /><br /> Перо планшетного компьютера и рукописный ввод<br /><br /> Моделирование перетаскивания с помощью событий захвата и перемещения мыши<br /><br /> OpenFileDialog<br /><br /> Десериализация XAML (посредством XamlReader.Load)|  
|Веб-интеграция|Диалоговое окно загрузки браузера<br /><br /> Навигация верхнего уровня, инициированная пользователем<br /><br /> mailto:links<br /><br /> Параметры универсального идентификатора ресурса (URI)<br /><br /> HTTPWebRequest<br /><br /> Содержимое WPF, размещенное в IFRAME<br /><br /> Размещение HTML-страниц одного веб-сайта с помощью Frame<br /><br /> Размещение HTML-страниц одного веб-сайта с помощью WebBrowser<br /><br /> Веб-службы (ASMX-файлы)<br /><br /> Веб-службы (с помощью Windows Communication Foundation)<br /><br /> Написание сценариев<br /><br /> Модель DOM|  
|Визуальные элементы|2D- и 3D-графика<br /><br /> Анимация<br /><br /> Мультимедиа (исходный сайт и междоменные)<br /><br /> Обработка изображений/аудио/видео|  
|Чтение|FlowDocument<br /><br /> XPS-документы<br /><br /> Внедренные и системные шрифты<br /><br /> Шрифты CFF и TrueType|  
|Редактирование|Проверка орфографии<br /><br /> RichTextBox<br /><br /> Поддержка буфера обмена для обычного текста и рукописного ввода<br /><br /> Вставка, инициированная пользователем<br /><br /> Копирование выделенного содержимого|  
|Управление|Общие элементы управления|  
  
 Эта таблица охватывает функции WPF на высоком уровне. Для получения более подробной информации SDK Windows документирует разрешения, требуемые каждым участником WPF. Кроме того, следующие функции содержат более подробные сведения, касающиеся выполнения при частичном доверии, включая некоторые особые аспекты.  
  
- [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)][(см. обзор XAML (WPF)](../../desktop-wpf/fundamentals/xaml.md)).  
  
- Всплывающие окно <xref:System.Windows.Controls.Primitives.Popup?displayProperty=nameWithType>(см.).  
  
- Перетащите и падение (см. [Перетащите и Drop Обзор](./advanced/drag-and-drop-overview.md)).  
  
- Клипборд <xref:System.Windows.Clipboard?displayProperty=nameWithType>(см.).  
  
- Изображение (см.). <xref:System.Windows.Controls.Image?displayProperty=nameWithType>  
  
- Сериализация (см. веестый <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>, <xref:System.Windows.Markup.XamlWriter.Save%2A?displayProperty=nameWithType>).  
  
- Открыть файл Диалог Box <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>(см.).  
  
 В следующей таблице излагаются функции WPF, которые небезопасны для выполнения в пределах набора разрешений зоны Интернета.  
  
 Таблица 2. Функции WPF, которые не являются безопасными в режиме частичного доверия  
  
|Область функций|Компонент|  
|------------------|-------------|  
|Общие сведения|Окно (определенные приложением окна и диалоговые окна)<br /><br /> SaveFileDialog<br /><br /> Файловая система<br /><br /> Доступ к реестру<br /><br /> Перетаскивание<br /><br /> Сериализация XAML (через XamlWriter.Save)<br /><br /> Клиенты UIAutomation<br /><br /> Доступ к исходному окну (HwndHost)<br /><br /> Полная поддержка управления речью<br /><br /> Взаимодействие с Windows Forms|  
|Визуальные элементы|Эффекты для точечных рисунков<br /><br /> Кодирование изображений|  
|Редактирование|Буфер обмена формата RTF<br /><br /> Полная поддержка XAML|  
  
<a name="Partial_Trust_Programming"></a>
## <a name="partial-trust-programming"></a>Программирование в режиме частичного доверия  
 Для приложений XBAP код, превышающий набор разрешений по умолчанию, будет иметь различное поведение в зависимости от зоны безопасности. В некоторых случаях пользователь получит предупреждение при попытке установить приложение. Пользователь может выбрать продолжение или отмену установки. В следующей таблице описаны поведение приложения для каждой зоны безопасности и действия, необходимые для получения приложением полного доверия.  
  
|Зона безопасности|Поведение|Получение полного доверия|  
|-------------------|--------------|------------------------|  
|Локальный компьютер|Автоматическое получение полного доверия|Никаких действий не требуется.|  
|Интрасеть и надежные веб-сайты|Запрос полного доверия|Подпишите приложение XBAP с помощью сертификата, чтобы пользователь видел источник в запросе.|  
|Интернет|Сбой с сообщением "Доверие не оказано"|Подпишите приложение XBAP с помощью сертификата.|  
  
> [!NOTE]
> Поведение, описанное в предыдущей таблице, относится к приложениям XBAP с полным доверием, не следующим модели доверенного развертывания ClickOnce.  
  
 В общем случае код, который может превышать допустимые разрешения, вероятнее всего, является общим кодом, который совместно используется автономными и браузерными приложениями. CAS и WPF предлагают несколько методов управления этим сценарием.  
  
<a name="Detecting_Permissions_using_CAS"></a>
### <a name="detecting-permissions-using-cas"></a>Определение разрешений с помощью CAS  
 В некоторых ситуациях общий код в библиотечных сборках может использоваться как автономными приложениями, так и XBAPs. В этих случаях код может выполнять функции, которые могут потребовать больше разрешений, чем позволяет набор разрешений, присвоенный приложению. Ваше приложение может определить, имеет ли оно определенное разрешение с помощью безопасности Microsoft .NET Framework. В частности, он может проверить, есть <xref:System.Security.CodeAccessPermission.Demand%2A> ли у него конкретное разрешение, вызывая метод на экземпляр желаемого разрешения. Это показано в следующем примере, который содержит код, запрашивающий возможность сохранить файл на локальный диск.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandling.cs#detectpermscode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandling.vb#detectpermscode2)]  
  
 Если приложение не имеет желаемого разрешения, <xref:System.Security.CodeAccessPermission.Demand%2A> вызов будет бросать исключение безопасности. В противном случае разрешение будет предоставлено. `IsPermissionGranted`инкапсулирует это поведение и `true` `false` возвращает или по мере необходимости.  
  
<a name="Graceful_Degradation_of_Functionality"></a>
### <a name="graceful-degradation-of-functionality"></a>Постепенное снижение функциональности  
 Возможность обнаружения у кода разрешений на выполнение действия представляет интерес для кода, который может выполняться из разных зон. Обнаружение зоны — это один из аспектов, однако рекомендуется по возможности предоставить пользователю альтернативу. Например, приложение с полным доверием обычно позволяет пользователям создавать файлы в любом расположении, тогда как приложение с частичным доверием может создавать файлы только в изолированном хранилище. Если код для создания файла существует в сборке, которая совместно используется приложениями с полным доверием (автономными) и приложениями с частичным доверием (размещенными в браузере), и оба приложения должны обеспечивать функцию создания файлов пользователем, общий код должен определить, выполняется ли он в режиме частичного или полного доверия перед созданием файла в соответствующем расположении. Оба варианта демонстрируются в следующем коде.  
  
 [!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode1)]
 [!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode1)]  
[!code-csharp[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/csharp/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/CSharp/FileHandlingGraceful.cs#detectpermsgracefulcode2)]
[!code-vb[PartialTrustSecurityOverviewSnippets#DetectPermsGracefulCODE2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PartialTrustSecurityOverviewSnippets/VisualBasic/FileHandlingGraceful.vb#detectpermsgracefulcode2)]  
  
 Во многих случаях вы сможете найти альтернативу частичному доверию.  
  
 В контролируемой среде, такой как интранет, пользовательские управляемые фрегаты могут быть установлены по всей клиентской базе в глобальный кэш сборки (GAC). Эти библиотеки могут выполнять код, который требует полного доверия, и <xref:System.Security.AllowPartiallyTrustedCallersAttribute> ссылаться на приложения, которые только разрешено частичное доверие с помощью (для получения дополнительной информации, см. [Безопасность безопасности](security-wpf.md) и [Стратегии безопасности WPF - Платформа безопасности](wpf-security-strategy-platform-security.md)).  
  
<a name="Browser_Host_Detection"></a>
### <a name="browser-host-detection"></a>Обнаружение узла браузера  
 Использование CAS для проверки разрешений является подходящим методом, когда вам нужно проверить на основе разрешения. Тем не менее эта методика зависит от перехвата исключений в рамках нормальной обработки, что не рекомендуется в общем и может вызывать проблемы производительности. Вместо этого, если ваше браузерное приложение XAML (XBAP) работает только <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A?displayProperty=nameWithType> в песочнице зоны Интернета, вы можете использовать свойство, которое возвращается верно для приложений для браузера XAML (XBAPs).  
  
> [!NOTE]
> <xref:System.Windows.Interop.BrowserInteropHelper.IsBrowserHosted%2A>только различает, работает ли приложение в браузере, а не какой набор разрешений приложение работает с.  
  
<a name="Managing_Permissions"></a>
## <a name="managing-permissions"></a>Управление разрешениями  
 По умолчанию XBAPs работают с частичным доверием (набор разрешений в интернет-зоне по умолчанию). Тем не менее в зависимости от требований приложения можно изменить набор разрешений по умолчанию. Например, если XBAPs запущен из локальной интрасети, он может воспользоваться увеличенным набором разрешений, который отображается в следующей таблице.  
  
 Таблица 3. Наборы разрешений LocalIntranet и Internet  
  
|Разрешение|attribute|LocalIntranet|Интернет|  
|----------------|---------------|-------------------|--------------|  
|DNS|Доступ к DNS-серверам|Да|нет|  
|Переменные среды|Чтение|Да|нет|  
|Диалоговые окна для работы с файлами|Открыть|Да|Да|  
|Диалоговые окна для работы с файлами|С неограниченным доступом|Да|нет|  
|Изолированное хранилище|Изоляция сборки по пользователю|Да|нет|  
|Изолированное хранилище|Неизвестная изоляция|Да|Да|  
|Изолированное хранилище|Неограниченная квота для пользователя|Да|нет|  
|Служба мультимедиа|Безопасные аудио-, видеоданные и изображения|Да|Да|  
|Печать|Печать по умолчанию|Да|нет|  
|Печать|Безопасная печать|Да|Да|  
|Отражение|Вывод|Да|нет|  
|Безопасность|Выполнение управляемого кода|Да|Да|  
|Безопасность|Утверждение предоставленных разрешений|Да|нет|  
|Пользовательский интерфейс|С неограниченным доступом|Да|нет|  
|Пользовательский интерфейс|Безопасные окна верхнего уровня|Да|Да|  
|Пользовательский интерфейс|Собственный буфер обмена|Да|Да|  
|Веб-браузер|Безопасная навигация по фреймам в HTML|Да|Да|  
  
> [!NOTE]
> Вырезание и вставка разрешены только в режиме частичного доверия при инициации пользователем.  
  
 Если вам требуется повысить уровень разрешений, необходимо изменить параметры проекта и манифест приложения ClickOnce. Дополнительные сведения см. в разделе [Общие сведения о приложениях браузера WPF XAML](./app-development/wpf-xaml-browser-applications-overview.md). Следующие документы также могут быть полезны.  
  
- [Mage.exe (Manifest поколения и редактирования инструмент)](../tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
- [MageUI.exe (Manifest Поколения и Редактирование инструмент, Графический клиент)](../tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client.md).  
  
- [Обеспечение ClickOnce приложений](/visualstudio/deployment/securing-clickonce-applications).  
  
 Если вашему XBAP требуется полное доверие, вы можете использовать те же инструменты для увеличения запрошенных разрешений. Хотя XBAP получит полное доверие только в том случае, если он установлен и запущен с локального компьютера, интрасети или с URL-адреса, который указан на доверенных или разрешенных сайтах браузера. Если приложение установлено из интрасети или с доверенного сайта, пользователь получит стандартный запрос ClickOnce, уведомляющий о повышенных разрешениях. Пользователь может выбрать продолжение или отмену установки.  
  
 Кроме того, модель доверенного развертывания ClickOnce можно использовать для полностью доверенного развертывания из любой зоны безопасности. Для получения дополнительной информации [Security](security-wpf.md)см. [Trusted Application Deployment Overview](/visualstudio/deployment/trusted-application-deployment-overview)  
  
## <a name="see-also"></a>См. также раздел

- [Безопасность](security-wpf.md)
- [Стратегия безопасности WPF — безопасность платформы](wpf-security-strategy-platform-security.md)
- [Стратегия безопасности WPF — проектирование безопасности](wpf-security-strategy-security-engineering.md)
