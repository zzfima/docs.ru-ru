---
title: "Изменения целевой платформы в .NET Framework 4.6.1 | Документы Майкрософт"
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
- retargeting changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 411ad548-30fa-43da-8716-10eccfc839e6
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0adc4a6cae566b6a15c5fa492620abb74b47335b
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-461"></a>Изменения целевой платформы в .NET Framework 4.6.1
В редких случаях изменения целевой платформы могут повлиять на приложения, которые перекомпилируются для использования в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Если не указано иное, эти изменения не влияют на двоичные файлы, предназначенные для предыдущей версии .NET Framework, но выполняемые в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] содержит изменения целевой платформы в следующих областях.  
  
-   [Ядро](#Core)  
  
-   [Контракты для кода](#Contracts)  
  
-   [Windows Communication Foundation](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
<a name="Core"></a>   
## <a name="core"></a>Ядро  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>|В приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более поздних версий, символ разделителя пути изменился с обратной косой черты ("\\") на прямую косую черту ("/") в свойстве <xref:System.IO.Compression.ZipArchiveEntry.FullName%2A> объектов <xref:System.IO.Compression.ZipArchiveEntry>, созданных перегрузками метода <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A?displayProperty=fullName>.|Изменение обеспечивает соответствие реализации .NET разделу 4.4.17.1 [спецификации формата ZIP-файла](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) и позволяет распаковывать ZIP-архивы в системах, отличных от Windows.<br /><br /> Однако возможно отказаться от этого поведения в приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более поздних версий. Дополнительные сведения см. в разделе [Устранение рисков: разделитель пути ZipArchiveEntry.FullName](../../../docs/framework/migration-guide/mitigation-ziparchiveentry-fullname-path-separator.md).|Пограничный случай|  
  
<a name="Contracts"></a>   
## <a name="code-contracts"></a>Контракты для кода  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=fullName> и <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=fullName> и вызовы <xref:System.String.IsNullOrEmpty%2A?displayProperty=fullName>|В приложениях, предназначенных для .NET Framework 4.6.1, средство перезаписи выдает предупреждение компилятора CC1036: "Обнаружен вызов метода 'System.String.IsNullOrWhiteSpace(System.String)' без [Pure] в методе..."|Это предупреждение, а не ошибка компилятора.<br /><br /> Проблема была устранена в [билете 339 на сайте GitHub](https://github.com/Microsoft/CodeContracts/issues/339). Чтобы устранить это предупреждение, можно скачать и скомпилировать обновленную версию исходного кода для инструментов контрактов кода с сайта [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md). Сведения о скачивании находятся в нижней части страницы.|Дополнительный номер|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation"></a>Windows Communication Foundation  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A?displayProperty=fullName><br /><br /> (пространство имен <xref:System.IdentityModel.Claims>)|Если в приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], набор утверждений X509 инициализируется из сертификата, имеющего несколько записей DNS в поле SAN, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> пытается сопоставить аргумент `claimType`.<br /><br /> В приложениях, предназначенных для предыдущих версий .NET Framework, метод <xref:System.IdentityModel.Claims.X509CertificateClaimSet.FindClaims%2A> пытается сопоставить аргумент `claimType` только с последней записью DNS.|Это изменение затрагивает все приложения, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Приложения, предназначенные для предыдущих версий платформы .NET Framework, это изменение не затрагивает.<br /><br /> Однако возможно отказаться от этого поведения в приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Кроме того, можно согласиться на это поведение в приложениях, которые предназначены для предыдущих версий платформы .NET Framework, но работают в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Дополнительные сведения см. в разделе [Устранение рисков: метод X509CertificateClaimSet.FindClaims](../../../docs/framework/migration-guide/mitigation-x509certificateclaimset-findclaims-method.md).|Дополнительный номер|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Метод <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> (пространство имен <xref:System.Windows.Forms>)|В приложениях Windows Forms, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], пользовательская реализация <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> может безопасно фильтровать сообщения, когда вызывается метод <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>, если реализация <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName>:<br /><br /> <ul><li>Выполняет одно или оба следующих действия:<br /><br /> <ul><li>Добавляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.</li><li>Удаляет фильтр сообщений путем вызова метода <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>. метод.</li></ul></li><li>**И** передает сообщения путем вызова метода <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName>.</li></ul><br /> В приложениях Windows Forms, которые предназначены для предыдущих версий платформы .NET Framework, такие реализации в некоторых случаях вызывают исключение <xref:System.IndexOutOfRangeException> при вызове метода <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName>.|Это изменение затрагивает все приложения, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Приложения, предназначенные для предыдущих версий платформы .NET Framework, это изменение не затрагивает.<br /><br /> Однако возможно отказаться от этого поведения в приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Кроме того, можно согласиться на это поведение в приложениях, которые предназначены для предыдущих версий платформы .NET Framework, но работают в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]. Дополнительные сведения см. в разделе [Устранение рисков: пользовательские реализации IMessageFilter.PreFilterMessage](../../../docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).|Пограничный случай|  
  
## <a name="see-also"></a>См. также  
 [Совместимость приложений в 4.6.1](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
