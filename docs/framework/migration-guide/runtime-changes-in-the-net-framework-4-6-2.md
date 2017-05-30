---
title: "Изменения среды выполнения в .NET Framework 4.6.2 | Документация Майкрософт"
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
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.2
- application compatibility
ms.assetid: 23bf3a87-6fa1-4b5e-b92c-a39867a06e7f
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: da809955776b5a5cd3776898ecc4c97db74ceb0e
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="runtime-changes-in-the-net-framework-462"></a>Изменения среды выполнения в .NET Framework 4.6.2
В редких случаях изменения среды выполнения могут повлиять на существующие приложения, предназначенные для предыдущих версий .NET Framework, но выполняющиеся в более поздней версии среды выполнения .NET Framework. Они также включают различия в поведении между приложениями, которые выполняются в разных средах .NET Framework. [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] включает изменения в следующих областях:  
  
-   [Ядро](#Core)  
  
-   [ASP.NET](#ASP)

-   [Данные](#Data)  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
-   [Подписание и проверка XML](#XML)  
  
<a name="Core"></a>   
## <a name="core"></a>Ядро  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName><br /><br /> <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory%2A?displayProperty=fullName>|Категории символов в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] основаны на стандарте Юникод версии 8.0. Версии платформы .NET Framework от 4.5 до 4.6.1 классифицировали символы Юникода на основе стандарта Юникод версии 6.3.<br /><br /> Это изменение не затрагивает сравнение и сортировку символов. Дополнительные сведения см. в разделе "Строки и стандарт Юникода" в статье о классе <xref:System.String>.|Категории символов в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] могут не соответствовать таковым в предыдущих версиях платформы .NET Framework. Это изменение в первую очередь влияет на слоги языка чероки, а также знаки гласных и обозначения тонов в новой письменности Тай-Лю.<br /><br /> Чтобы учесть это изменение, следует просмотреть код и удалить или изменить логику, зависящую от жестко заданных категорий символов Юникода.|Дополнительный номер|  
|<xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.RSACng.ImportParameters%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPrivateKey%2A?displayProperty=fullName>, <xref:System.Security.Cryptography.X509Certificates.RSACertificateExtensions.GetRSAPublicKey%2A?displayProperty=fullName>|Начиная с версии [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], эти методы могут получать доступ к ключам нестандартного размера для сертификатов RSA. В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версиях при попытке обращения к этим ключам создается исключение <xref:System.Security.Cryptography.CryptographicException>.|Если вы используете логику обработки исключений, которая зависит от появления <xref:System.Security.Cryptography.CryptographicException> при использовании нестандартных размеров ключей, ее следует изменить.|Пограничный случай|  
|<xref:System.Security.Cryptography.RSACng.VerifyHash%2A?displayProperty=fullName>|Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], этот метод возвращает `false`, если сама подпись неверно форматирована. Теперь он возвращает `false` при любом сбое проверки.<br /><br /> В версиях [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] и 4.6.1 метод создает исключение <xref:System.Security.Cryptography.CryptographicException>, если подпись имеет неправильный формат.|Любой код, выполнение которого зависит от <xref:System.Security.Cryptography.CryptographicException>, следует изменить так, чтобы он выполнялся, когда проверка завершается неудачей и метод возвращает `false`.|Дополнительный номер|  
  
## <a name="a-nameasp--aspnet"></a><a name="ASP" /> ASP.NET

|Функция|Изменение|Последствия|Область| 
|-------------|------------|------------|-----------|  
| <xref:System.Web.HttpRuntime.AppDomainApopPath%2A> | В .NET Framework 4.6.2 среда выполнения создает исключение <xref:System.NullReferenceException>, когда полученное значение <xref:System.Web.HttpRuntime.AppDomainAppPath%2A> содержит символы null. В .NET Framework 4.6.1 и более ранних версиях она создает исключение <xref:System.ArgumentNullException>.  | В ответ на это изменение можно сделать следующее: <br/> обрабатывайте <xref:System.NullReferenceException>, если приложение работает на платформе .NET Framework 4.6.2; <br /> обновите систему до версии .NET Framework 4.7, в которой восстановлено прежнее поведение, то есть создается исключение <xref:System.ArgumentNullException>. | Пограничный случай |

<a name="Data"></a>   
## <a name="data"></a>Данные  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Период блокировки пула соединений для баз данных Azure SQL|Для запросов на открытие подключения к известным базам данных Azure SQL период блокировки пула соединений удаляется.|Почти сразу же после временных ошибок подключения будут выполняться повторные попытки запросов на открытие подключения. Дополнительные сведения см. в статье [Устранение рисков. Период блокировки пула](~/docs/framework/migration-guide/mitigation-pool-blocking-period.md).|Дополнительный номер|  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>Windows Communication Foundation (WCF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName> <br /> <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=fullName>|При использовании NetTcp для обеспечения безопасности транспорта и применении типа учетных данных сертификата протокол SSL 3 больше не является протоколом по умолчанию для согласования безопасного соединения.|В большинстве случаев существующие приложения не должны затрагиваться, так как протокол TLS 1.0 всегда входил в список протоколов для NetTcp. Все существующие клиенты должны иметь возможность согласовывать подключение с помощью TLS версии не ниже 1.0.<br /><br /> Если требуется Ssl3, можно воспользоваться одним из указанных далее механизмов конфигурации и добавить Ssl3 в список установленных протоколов:<br /><br /> свойство <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=fullName>;<br />свойство <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols%2A?displayProperty=fullName>;<br />-   раздел [\<transport>](~/docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md) в [\<netTcpBinding>](~/docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md);<br />-   раздел [\<sslStreamSecurity>](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) в [\<customBinding>](~/docs/framework/configure-apps/file-schema/wcf/custombinding.md).|Пограничный случай|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>Windows Presentation Foundation (WPF)  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Свойство `IsEnabled` родительского элемента для элемента управления <xref:System.Windows.Controls.TextBlock>|Начиная с [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], изменения свойства `IsEnabled` родительского элемента для элемента управления <xref:System.Windows.Controls.TextBlock> влияют на все дочерние элементы управления (например, гиперссылки и кнопки) этого элемента управления <xref:System.Windows.Controls.TextBlock>.<br /><br /> В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версиях платформы .NET Framework элементы управления внутри <xref:System.Windows.Controls.TextBlock> не всегда соответствовали состоянию свойства `IsEnabled` для родительского элемента управления <xref:System.Windows.Controls.TextBlock>.|Это изменение соответствует ожидаемому поведению для элементов управления, содержащихся внутри элемента управления <xref:System.Windows.Controls.TextBlock>.|Дополнительный номер|  
|Горизонтальная прокрутка, виртуализация и <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName>|Изменено поведение операции прокрутки для <xref:System.Windows.Controls.ItemsControl>, который выполняет собственную виртуализацию в направлении, перпендикулярном основному направлению прокрутки.|Это поведение стало более прогнозируемым и интуитивно понятным для конечного пользователя, но изменение может повлиять на те приложения, которые ожидают конкретных значений свойства <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> после горизонтальной прокрутки. Дополнительные сведения см. в статье [Устранение рисков. Горизонтальная прокрутка и виртуализация](~/docs/framework/migration-guide/mitigation-horizontal-scrolling-and-virtualization.md).|Дополнительный номер|  
|Средство проверки орфографии WPF (класс <xref:System.Windows.Controls.SpellCheck?displayProperty=fullName>)|Три проблемы, отмеченные для средства проверки орфографии при выполнении в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], были разрешены в [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]:<br /><br /> – средство проверки орфографии в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] иногда вызывает исключение <xref:System.Runtime.InteropServices.COMException> при вызове метода [ISpellChecker](https://msdn.microsoft.com/library/windows/desktop/hh869767\(v=vs.85\).aspx) или [ISpellCheckerFactory](https://msdn.microsoft.com/library/windows/desktop/hh869770\(v=vs.85\).aspx). В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] эти исключения устранены.<br />-   В [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] средство проверки орфографии неверно определяет орфографические ошибки в составных словах, например "Hausnummer" в немецком языке. В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] средство проверки орфографии правильно обрабатывает составные слова.<br />– средство проверки орфографии в [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] вызывает исключение <xref:System.UnauthorizedAccessException>, если приложение запущено в режиме "запуска от имени другого пользователя". В [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] этот сценарий не поддерживается, и средство проверки орфографии автоматически отключается.|Эти изменения повышают надежность средства проверки орфографии.  Они не должны негативно влиять на приложение, если только код приложения не зависит от вызываемого исключения.|Пограничный случай|  
| Метод [DataGridCellsPanel.BringIndexIntoView](xref:System.Windows.Controls.DataGridCellsPanel.BringIndexInfoView(System.Int32)) | В платформе .NET Framework 4.6.2 метод **BringIndexIntoView** будет выполняться асинхронно, если виртуализация столбцов включена, но ширина столбцов не определена. Однако если столбцы удаляются до завершения асинхронной операции, может возникнуть исключение [ArgumentOutOfRangeException](xref:System.ArgumentOutOfRangeException).<br/></br>Начиная с .NET Framework 4.7, исключение в этом сценарии больше не вызывается. | Чтобы предотвратить возникновение исключения, можно выполнить следующие действия. <br/> - Выполнить обновление до .NET Framework 4.7. <br/> - Установить новейшее служебное исправление для .NET Framework 4.6.2. <br/> - Избегать удаления столбцов до завершения асинхронного ответа на метод [DataGrid.ScrollIntoView](xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)). | Пограничный случай | 
  
<a name="XML"></a>   
## <a name="signed-xml-verification-requirements"></a>Требования к проверке подписанного XML  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|<xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=fullName> и <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=fullName>.|Загрузка внешних ресурсов отключена, а неоднозначные целевые идентификаторы считаются недопустимыми.|Исключение вызывается в ряде случаев, включая следующие:<br /><br /> -   идентификация элемента по атрибуту id и определение второго элемента с таким же идентификатором;<br />-   определение идентификатора, который не является допустимым значением `NCName`;<br />-   ссылка на внешние URI.<br /><br /> <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A?displayProperty=fullName> всегда возвращает значение `false` для документов:<br /><br /> -   которые используют преобразование ссылок XPath;<br />-   которые используют преобразование ссылок XSLT.<br /><br /> Разработчикам следует изучить, как используются <xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=fullName>, <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> и производные от <xref:System.Security.Cryptography.Xml.Transform?displayProperty=fullName> типы, поскольку получатель документа не всегда сможет обработать его.<br /><br /> Дополнительные сведения см. в статье [После установки обновления для системы безопасности 3141780 приложений платформа.NET Framework возникновении исключения ошибок или непредвиденные сбои при обработке файлов, содержащих SignedXml](https://support.microsoft.com/en-us/kb/3148821).|Дополнительный номер|  
  
## <a name="see-also"></a>См. также  
 [Совместимость приложений в 4.6.2](~/docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
