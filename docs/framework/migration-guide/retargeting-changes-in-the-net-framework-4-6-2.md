---
title: "Изменения целевой платформы в .NET Framework 4.6.2 | Документация Майкрософт"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retargeting changes, .NET Framework
- retargeting changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 76dc6849-8210-4e41-8731-20828c98b282
caps.latest.revision: 26
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 229ccf3fa4ff1029334641da350cfd040e4b286e
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="retargeting-changes-in-the-net-framework-462"></a>Изменения целевой платформы в .NET Framework 4.6.2
В редких случаях изменения целевой платформы могут повлиять на приложения, которые перекомпилируются для использования в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]. Они не влияют на двоичные файлы, предназначенные для предыдущей версии .NET Framework, но выполняемые в версии 4.6.2. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] содержит изменения целевой платформы в следующих областях.  
  
-   [Ядро](#Core)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Forms](#WinForms)  
  
 Столбец "Scope" в следующих таблицах определяет важность каждого изменения.  
  
-   Основное. Значительное изменение, влияющее на большое количество приложений или требующее существенного изменения кода. Обратите внимание, что ни одно из изменений целевой платформы не попадает в эту категорию.  
  
-   Незначительное. Изменение влияет на небольшое количество приложений или требует незначительного изменения кода.  
  
-   Пограничное. Изменение влияет на приложения в исключительных ситуациях.  
  
-   Прозрачное. Изменение не оказывает особого влияния на разработчика или пользователя приложения. При этом вносить изменения в приложения не требуется.  
  
<a name="Core"></a>   
## <a name="core"></a>Ядро  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Поддержка длинных путей|Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], поддерживаются длинные пути (длиной до 32 тысячи символов), а ограничение в 260 символов (или `MAX_PATH`) на длину пути устранено.|В приложениях, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], некоторые пути кода, которые ранее вызвали исключение <xref:System.IO.PathTooLongException>, могут больше не вызывать исключений. Дополнительные сведения см. в разделе [Устранение рисков: поддержка длинных путей](~/docs/framework/migration-guide/mitigation-long-path-support.md).|Дополнительный номер|  
|Нормализация путей|Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], был изменен способ нормализации путей, чтобы переложить эту задачу на операционную систему и обеспечить более удобный доступ к путям на устройствах DOS.|Изменения позволяют получить доступ к путям устройств, которые ранее не поддерживались. Дополнительные сведения см. в разделе [Устранение рисков. Нормализация путей](~/docs/framework/migration-guide/mitigation-path-normalization.md).|Дополнительный номер|  
|<xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> и <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName>.|Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], выполнен ряд изменений для поддержки ранее не поддерживаемых путей (с точки зрения и длины, и формата). В частности, усовершенствованы проверки правильности синтаксиса разделителя диска (двоеточия).|Эти изменения блокируют некоторые пути URI, которые ранее поддерживались этими двумя методами. Дополнительные сведения см. в разделе [Устранение рисков. Проверки двоеточий в путях](~/docs/framework/migration-guide/mitigation-path-colon-checks.md).|Пограничный случай|  
|Конструктор <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName>|Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], вызов <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> создает свойство <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> в виде нового экземпляра <xref:System.Security.Claims.ClaimsIdentity>. В предыдущих версиях платформы .NET Framework <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> являлось ссылкой на существующий экземпляр.|В некоторых случаях,сравнение свойства <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> со свойством <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> из <xref:System.Security.Principal.IIdentity> конструктора возвращает разные результаты.<br /><br /> Дополнительные сведения см. в разделе [Устранение рисков. Конструктор ClaimsIdentity](~/docs/framework/migration-guide/mitigation-claimsidentity-constructor.md).|Пограничный случай|  
|<xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor%2A?displayProperty=fullName>|Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], дешифратор <xref:System.Security.Cryptography.AesCryptoServiceProvider> возвращает преобразование, которое можно использовать повторно.   Это преобразование повторно инициализируется после вызова <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A> и его можно использовать снова.<br /><br /> Для приложений, предназначенных для более ранних версий платформы .NET Framework, попытка повторного использования дешифратора путем вызова <xref:System.Security.Cryptography.ICryptoTransform.TransformBlock%2A> после вызова <xref:System.Security.Cryptography.ICryptoTransform.TransformFinalBlock%2A> приводит к исключению <xref:System.Security.Cryptography.CryptographicException> или к повреждению данных.|Воздействие должно быть минимальным, так как это ожидаемое поведение.<br /><br /> В приложениях, которые зависят от прежнего поведения, можно отказаться от его изменения, добавив следующий параметр конфигурации в раздел [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true"/> </runtime>`<br /><br /> Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздних версий. Для этого добавьте в раздел [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения следующий параметр:<br /><br /> `<runtime>    <AppContextSwitchOverrides value="Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false"/> </runtime>`|Дополнительный номер|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Поддержка безопасности транспорта WCF для сертификатов, сохраненных с помощью CNG|Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], безопасность транспорта WCF поддерживает сертификаты, сохраненные с использованием библиотеки шифрования Windows (CNG). Эта поддержка ограничивается сертификатами с открытым ключом, длина экспоненты которого не превышает 32 бита. Если приложение предназначено для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], эта функция включена по умолчанию.<br /><br /> В более ранних версиях платформы .NET Framework попытка использовать сертификаты X509 с поставщиком хранилища ключей CSG вызывала исключение.|Для приложений, которые предназначены для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версий, но работают в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], можно включить поддержку сертификатов CNG, добавив следующую строку в раздел runtime файла app.config или web.config.<br /><br /> `<AppContextSwitchOverrides     value="Switch.System.ServiceModel.DisableCngCertificates=false" />`<br /><br /> Это также можно сделать программно с помощью следующего кода:<br /><br /> `private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate"; AppContext.SetSwitch(disableCngCertificates, false);`<br /><br /> `Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates" AppContext.SetSwitch(disableCngCertificates, False)`<br /><br /> Обратите внимание, что из-за этого изменения любой код обработки исключений, который зависит от неудачной попытки инициировать защищенное взаимодействие с сертификатом CNG, больше не будет выполняться.|Дополнительный номер|  
  
<a name="WinForms"></a>   
## <a name="windows-forms"></a>Windows Forms  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=fullName>, `System.ComponentModel.EventDescriptor.Equals` и `System.ComponentModel.PropertyDescriptor.Equals`|Начиная с приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], изменилась реализация метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A> базового класса.|Так как проверка на равенство теперь выдает ожидаемый результат, это изменение не должно оказывать существенное влияние.<br /><br /> Но в приложениях, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] и зависящих от прежнего поведения, можно отказаться от этого изменения. Аналогично, для приложений, которые предназначены для более ранних версий платформы .NET Framework, но выполняются в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], это изменение можно включить. Дополнительные сведения см. в разделе [Устранение рисков. MemberDescriptor.Equals ](~/docs/framework/migration-guide/mitigation-memberdescriptor-equals.md).|Пограничный случай|  
  
## <a name="see-also"></a>См. также  
 [Совместимость приложений в 4.6.2](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
