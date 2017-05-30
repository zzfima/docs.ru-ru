---
title: "Изменения целевой платформы в .NET Framework 4.6 | Документы Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6
- application compatibility
ms.assetid: fa849255-f90f-4bf1-b0ff-b173c12110d7
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 19ad80233a79a4fdef89550696c1c3d33e14b355
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-46"></a>Изменения целевой платформы в .NET Framework 4.6
В редких случаях изменения целевой платформы могут повлиять на приложения, которые перекомпилируются для использования в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Если не указано иное, эти изменения не влияют на двоичные файлы, предназначенные для предыдущей версии .NET Framework, но выполняемые в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].  
  
 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] содержит изменения целевой платформы в следующих областях.  
  
-   [Ядро](#Core)  
  
-   [ASP.NET](#ASP)  
  
-   [Сеть](#Net)  
  
-   [Windows Communications Foundation (WCF)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [XML](#XML)  
  
<a name="Core"></a>   
## <a name="core"></a>Ядро  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName>, <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> и асинхронные операции на основе задач с <xref:System.Threading.Tasks.Task> и <xref:System.Threading.Tasks.Task%601>|Для приложений, предназначенных для [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и более поздних версий, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> хранятся в свойстве <xref:System.Threading.ExecutionContext> потока, который сохраняется для всех асинхронных операций.|Изменения, внесенные в свойства <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, будут отражены в во всех запущенных позднее асинхронных задачах. Дополнительные сведения см.в разделе [Устранение рисков: язык и региональные параметры и асинхронные операции](../../../docs/framework/migration-guide/mitigation-culture-and-asynchronous-operations.md).|Дополнительный номер|  
  
<a name="ASP"></a>   
## <a name="aspnet"></a>ASP.NET  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> со значением `tagKey` для свойства <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>|В соответствии со стандартом HTML метод <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> теперь передает <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> как незакрывающийся тег в HTML-ответе.|Тег BR теперь преобразуется в один разрыв строки. Ранее он преобразовывался в два разрыва строк.<br /><br /> В приложениях, в которых тег `<BR>` использовался для создания двух разрывов строк, можно восстановить прежнее поведение, добавив дополнительный вызов метода <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> с аргументом <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>.|Дополнительный номер|  
  
<a name="Net"></a>   
## <a name="networking"></a>Сетевое взаимодействие  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Net.ServicePointManager?displayProperty=fullName> и <xref:System.Net.Security.SslStream?displayProperty=fullName>.|Начиная с приложений, предназначенных для версии .NET Framework 4.6, классы <xref:System.Net.ServicePointManager?displayProperty=fullName> и <xref:System.Net.Security.SslStream?displayProperty=fullName> могут использовать один из трех следующих протоколов: Tls 1.0, Tls 1.1 или Tls 1.2.<br /><br /> Приложения, предназначенные для предыдущей версии платформы .NET Framework, даже если они выполняются в .NET Framework 4.6, не затрагиваются.|Это изменение влияет на все приложения, предназначенные для .NET Framework 4.6 и использующие протокол SSL для связи с сервером HTTPS или сервером сокетов с помощью любого из следующих типов: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> и <xref:System.Net.Security.SslStream>.  Дополнительные сведения см. в разделе [Устранение рисков. Протоколы TLS](../../../docs/framework/migration-guide/mitigation-tls-protocols.md).|Дополнительный номер|  
  
<a name="WCF"></a>   
## <a name="windows-communications-foundation-wcf"></a>Windows Communications Foundation (WCF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%2A?displayProperty=fullName>|В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] изменена реализация контекста <xref:System.IdentityModel.Policy.AuthorizationContext>, возвращаемого при вызове <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> с аргументом `null``authorizationPolicies`.|В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении. Сведения о возврате к прежнему поведению см. в разделе [Устранение рисков. Контекст AuthorizationContext по умолчанию](../../../docs/framework/migration-guide/mitigation-default-authorizationcontext.md).|Дополнительный номер|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>|Начиная с приложений, предназначенных для .NET Framework 4.6, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> успешно преобразует значки с кадрами PNG в объекты <xref:System.Drawing.Bitmap>.<br /><br /> В приложениях, предназначенных для .NET Framework 4.5.2 и более ранних версий, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> создает исключение <xref:System.ArgumentOutOfRangeException>, если объект <xref:System.Drawing.Icon> содержит кадры PNG.|Это изменение затрагивает приложения, которые компилируются повторно для платформы .NET Framework 4.6 и в которых реализована специальная обработка исключения <xref:System.ArgumentOutOfRangeException>, создаваемого при наличии кадров PNG в объекте <xref:System.Drawing.Icon>. Если такое поведение нежелательно, можно восстановить предыдущее поведение с помощью параметра конфигурации. Дополнительные сведения см. в разделе [Устранение рисков: кадры PNG кадров в объектах Icon](../../../docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|Дополнительный номер|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>.|В приложениях, предназначенных для .NET Framework 4.6 или .NET Framework 4.6.1, изменения свойств <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> или <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, внесенные в <xref:System.Windows.Threading.Dispatcher>, теряются при завершении соответствующей операции диспетчеризации. Аналогичным образом, изменения <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>, внесенные за пределами операции диспетчеризации, не будут учитываться при выполнении этой операции.|Изменения свойств <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> и <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> не передаются между вызовами пользовательского интерфейса WPF и другим кодом в приложении WPF. Дополнительные сведения см.в разделе [Устранение рисков: язык и региональные параметры и операции диспетчеризации в приложениях WPF](../../../docs/framework/migration-guide/mitigation-culture-and-dispatcher-operations-in-wpf-apps.md).|Дополнительный номер|  
|Округление макета при высоком разрешении|Способ округления полей, а также их границ и фона, изменен.|Макет элементов управления WPF может немного изменяться. Дополнительные сведения см. в разделе [Устранение рисков. Макет WPF](../../../docs/framework/migration-guide/mitigation-wpf-layout.md).|Дополнительный номер|  
  
<a name="XML"></a>   
## <a name="xml"></a>XML  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Проверка схемы XSD|Начиная с .NET Framework 4.6, в ходе проверки XSD-схемы выявляется нарушение ограничения уникальности, если используется составной ключ и один ключ является пустым.|См. раздел [Устранение рисков. Проверка схемы XML](../../../docs/framework/migration-guide/mitigation-xml-schema-validation.md).|Дополнительный номер|  
|<xref:System.Xml.XmlWriter>|Для приложений с целевой платформой .NET Framework 4.5.2 или предыдущих версий запись недействительной суррогатной пары с помощью обработки резервного исключения не всегда вызывает исключение.<br /><br /> Для приложений с целевой платформой [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] попытка записи недействительной суррогатной пары вызывает исключение <xref:System.ArgumentException>.|В приложениях, перекомпилированных для целевой платформы [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], в которых записываются недействительные суррогатные пары, будут вызваны исключения в случаях, где раньше их не возникало.|Пограничный случай|
