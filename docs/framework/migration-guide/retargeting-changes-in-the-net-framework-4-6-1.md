---
title: "Изменения целевой платформы в .NET Framework 4.6.1 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Изменения целевой платформы в .NET Framework 4.6.1
В редких случаях изменения целевой платформы могут повлиять на приложения, которые перекомпилируются для использования в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Если не указано иное, эти изменения не влияют на двоичные файлы, предназначенные для предыдущей версии .NET Framework, но выполняемые в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] содержит изменения целевой платформы в следующих областях.  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="WCF"></a>   
## Windows Communication Foundation  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> \(пространство имен <xref:System.IdentityModel.Claims>\)|Если в приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], набор утверждений X509 инициализируется из сертификата, имеющего несколько DNS\-записей в поле SAN, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> пытается сопоставить аргумент `claimType` со всеми записями DNS.<br /><br /> В приложениях, предназначенных для предыдущих версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> пытается сопоставить аргумент `claimType` только с последней записью DNS.|Это изменение затрагивает все приложения, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Приложения, предназначенные для предыдущих версий платформы .NET Framework, это изменение не затрагивает.<br /><br /> Однако возможно отказаться от этого поведения в приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Кроме того, можно согласиться на это поведение в приложениях, которые предназначены для предыдущих версий платформы .NET Framework, но работают в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Дополнительные сведения см. в разделе [Решение проблемы: метод X509CertificiateClaimSet.FindClaims](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|Дополнительный номер|  
  
<a name="WinForms"></a>   
## Windows Forms  
  
|Функция|Изменение|Последствия|Область|  
|-------------|---------------|-----------------|-------------|  
|Метод <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> \(пространство имен <xref:System.Windows.Forms>\)|В приложениях Windows Forms, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], реализация настраиваемого метода <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> может безопасно фильтровать сообщения, когда вызывается метод <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>, если реализация <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:<br /><br /> <ul><li>Выполняет одно или оба следующих действия:<br /><br /> <ul><li>добавляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.AddMessageFilter%2A>;</li><li>удаляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. метод.</li></ul></li><li>**И** передает сообщения путем вызова метода <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.</li></ul><br /> Такие реализации в приложениях Windows Forms, которые предназначены для предыдущих версий платформы .NET Framework, в некоторых случаях вызывают исключение <xref:System.IndexOutOfRangeException> при вызове метода <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>.|Это изменение затрагивает все приложения, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Приложения, предназначенные для предыдущих версий платформы .NET Framework, это изменение не затрагивает.<br /><br /> Однако возможно отказаться от этого поведения в приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Кроме того, можно согласиться на это поведение в приложениях, которые предназначены для предыдущих версий платформы .NET Framework, но работают в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Для получения дополнительной информации см. [Уменьшение: реализации пользовательских IMessageFilter.PreFilterMessage](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|Пограничный случай|  
  
## См. также  
 [Совместимость приложений в платформе 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)