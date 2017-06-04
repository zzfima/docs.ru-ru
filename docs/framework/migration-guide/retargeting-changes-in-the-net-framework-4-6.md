---
title: "Изменения целевой платформы в .NET Framework 4.6 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa849255-f90f-4bf1-b0ff-b173c12110d7
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Изменения целевой платформы в .NET Framework 4.6
В редких случаях изменения целевой платформы могут повлиять на приложения, которые перекомпилируются для использования в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]. Если не указано иное, эти изменения не влияют на двоичные файлы, предназначенные для предыдущей версии .NET Framework, но выполняемые в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].  
  
 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] содержит изменения целевой платформы в следующих областях.  
  
-   [ASP.NET](#ASP)  
  
-   [Сетевое взаимодействие](#Net)  
  
-   [Windows Communications Foundation \(WCF\)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
-   [Windows Presentation Foundation \(WPF\)](#WPF)  
  
-   [XML](#XML)  
  
<a name="ASP"></a>   
## ASP.NET  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|<xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> со значением `tagKey` свойства <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>|В соответствии со стандартом HTML метод <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> теперь передает <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName> как незакрывающийся тег в HTML\-ответе.|Тег BR теперь преобразуется в один разрыв строки. Ранее он преобразовывался в два разрыва строк.<br /><br /> В приложениях, в которых тег `<BR>` использовался для создания двух разрывов строк, можно восстановить прежнее поведение, добавив дополнительный вызов метода <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag%28System.Web.UI.HtmlTextWriterTag%29?displayProperty=fullName> с аргументом <xref:System.Web.UI.HtmlTextWriterTag?displayProperty=fullName>.|Дополнительный номер|  
  
<a name="Net"></a>   
## Сетевое взаимодействие  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|<xref:System.Net.ServicePointManager?displayProperty=fullName> и <xref:System.Net.Security.SslStream?displayProperty=fullName>.|Начиная с приложений, предназначенных для версии .NET Framework 4.6, классы <xref:System.Net.ServicePointManager?displayProperty=fullName> и <xref:System.Net.Security.SslStream?displayProperty=fullName> могут использовать один из трех следующих протоколов: Tls 1.0, Tls 1.1 или Tls 1.2.<br /><br /> Приложения, предназначенные для предыдущей версии платформы .NET Framework, даже если они выполняются в .NET Framework 4.6, не затрагиваются.|Это изменение влияет на все приложения, предназначенные для .NET Framework 4.6 и использующие протокол SSL для связи с сервером HTTPS или сервером сокетов с помощью любого из следующих типов: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> и <xref:System.Net.Security.SslStream>.  Дополнительные сведения см. в разделе [Уменьшение. Протоколы TLS](../../../docs/framework/migration-guide/mitigation-tls-protocols.md).|Дополнительный номер|  
  
<a name="WCF"></a>   
## Windows Communications Foundation \(WCF\)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|<xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%2A?displayProperty=fullName>|Реализация контекста <xref:System.IdentityModel.Policy.AuthorizationContext>, возвращаемого путем вызова <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> с аргументом `authorizationPolicies` со значением `null`, изменена в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].|В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении. Если требуется прежнее поведение, см. раздел [Уменьшение. Контекст AuthorizationContext по умолчанию](../../../docs/framework/migration-guide/mitigation-default-authorizationcontext.md).|Дополнительный номер|  
  
<a name="WinForms"></a>   
## Windows Forms  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|<xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName>|Начиная с приложений, предназначенных для .NET Framework 4.6, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> успешно преобразует значки с кадрами PNG в объекты <xref:System.Drawing.Bitmap>.<br /><br /> В приложениях, предназначенных для .NET Framework 4.5.2 и более ранних версий, метод <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=fullName> создает исключение <xref:System.ArgumentOutOfRangeException>, если объект <xref:System.Drawing.Icon> содержит кадры PNG.|Это изменение затрагивает приложения, которые компилируются повторно для платформы .NET Framework 4.6 и в которых реализуется специальная обработка исключения <xref:System.ArgumentOutOfRangeException>, создаваемого при наличии кадров PNG в объекте <xref:System.Drawing.Icon>. Если такое поведение нежелательно, можно восстановить предыдущее поведение с помощью параметра конфигурации. Для получения дополнительной информации см. [Решение проблемы: кадры PNG в объектах Icon](../../../docs/framework/migration-guide/mitigation-png-frames-in-icon-objects.md).|Дополнительный номер|  
  
<a name="WPF"></a>   
## Windows Presentation Foundation \(WPF\)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Округление макета при высоком разрешении|Способ округления полей, а также их границ и фона, изменен.|Макет элементов управления WPF может немного изменяться. Дополнительные сведения см. в разделе [Уменьшение. Макет WPF](../../../docs/framework/migration-guide/mitigation-wpf-layout.md).|Дополнительный номер|  
  
<a name="XML"></a>   
## XML  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Проверка схемы XSD|Начиная с .NET Framework 4.6, в ходе проверки XSD\-схемы выявляется нарушение ограничения уникальности, если используется составной ключ и один ключ является пустым.|См. раздел [Уменьшение. Проверка схемы XML](../../../docs/framework/migration-guide/mitigation-xml-schema-validation.md).|Дополнительный номер|  
|<xref:System.Xml.XmlWriter>|Для приложений с целевой платформой .NET Framework 4.5.2 или предыдущих версий запись недействительной суррогатной пары с помощью обработки резервного исключения не всегда вызывает исключение.<br /><br /> Для приложений с целевой платформой [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] попытка записи недействительной суррогатной пары вызывает исключение <xref:System.ArgumentException>.|В приложениях, перекомпилированных для целевой платформы [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], в которых записываются недействительные суррогатные пары, будут вызваны исключения в случаях, где раньше их не возникало.|Пограничный случай|