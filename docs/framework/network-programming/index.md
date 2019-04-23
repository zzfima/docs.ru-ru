---
title: Сетевое программирование в .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 74084b8eef46f700733ad44e04cf8b3811456b85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61642416"
---
# <a name="network-programming-in-the-net-framework"></a>Сетевое программирование в .NET Framework
Microsoft .NET Framework обеспечивает многоуровневую, расширяемую и управляемую реализацию служб Интернета, которую можно легко и быстро интегрировать в приложения. В сетевых приложениях можно использовать подключаемые протоколы, которые позволяют автоматически применять новые протоколы Интернета, или управляемую реализацию интерфейса сокетов Windows, дающую возможность работать с сетью на уровне сокетов.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Введение в подключаемые протоколы](../../../docs/framework/network-programming/introducing-pluggable-protocols.md)  
 Описание способов доступа к интернет-ресурсу вне зависимости от используемого протокола доступа  
  
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)  
 Объясняется, как использовать подключаемые протоколы для отправки и приема данных из интернет-ресурсов.  
  
 [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md)  
 Объясняется, как создать классы для определенных протоколов чтобы реализовать подключаемые протоколы.  
  
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)  
 Описание процесса создания приложений, которые используют сетевые протоколы, такие как TCP, UDP и HTTP.  
  
 [Протокол IP версии 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 Описание преимуществ протокола IP версии 6 (IPv6) над текущей версией набора протоколов IP (IPv4); описание адресации, маршрутизации и автоматической настройки IPv6, а также процедур включения и выключения IPv6.  
  
 [Настройка веб-приложений](../../../docs/framework/network-programming/configuring-internet-applications.md)  
 Описание использования файлов конфигурации .NET Framework для настройки интернет-приложений.  
  
 [Трассировка сети в .NET Framework](../../../docs/framework/network-programming/network-tracing.md)  
 Описание использования трассировки сети для получения сведений о вызовах методов и о сетевом трафике, созданном управляемым приложением.  
  
 [Управление кэшем для сетевых приложений](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 Описание использования кэширования для приложений, которые используют классы <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>и <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .  
  
 [Безопасность в сетевом программировании](../../../docs/framework/network-programming/security-in-network-programming.md)  
 Описание использования стандартных методов безопасности и аутентификации в Интернете.  
  
 [Рекомендации по использованию классов System.Net](../../../docs/framework/network-programming/best-practices-for-system-net-classes.md)  
 Советы по достижению максимальной эффективности разрабатываемых интернет-приложений.  
  
 [Доступ к Интернету через прокси-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 Описание порядка настройки прокси.  
  
 [NetworkInformation](../../../docs/framework/network-programming/networkinformation.md)  
 Описание порядка сбора информации о событиях, изменениях, статистике и свойствах сети, а также порядка определения доступности удаленного узла с помощью класса <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> .  
  
 [Изменения пространства имен System.Uri в версии 2.0](../../../docs/framework/network-programming/changes-to-the-system-uri-namespace-in-version-2-0.md)  
 Описание нескольких изменений, внесенных в класс <xref:System.Uri?displayProperty=nameWithType> в версии 2.0 для устранения неправильного поведения, повышения удобства работы и безопасности.  
  
 [Поддержка международного кода ресурса в System.Uri](../../../docs/framework/network-programming/international-resource-identifier-support-in-system-uri.md)  
 Описание усовершенствований класса <xref:System.Uri?displayProperty=nameWithType> в версиях 3.5, 3.0 с пакетом обновления 1 (SP1) и 2.0 с пакетом обновления 1 (SP1), касающихся поддержки международного идентификатора ресурсов (IRI) и международных доменных имен (IDN).  
  
 [Улучшения производительности сокетов в версии 3.5](../../../docs/framework/network-programming/socket-performance-enhancements-in-version-3-5.md)  
 Описание набора усовершенствований класса <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> в версиях 3.5, 3.0 с пакетом обновления 1 (SP1) и 2.0 с пакетом обновления 1 (SP1), которые предоставляют альтернативный шаблон асинхронной модели, который может использоваться специализированными высокопроизводительными приложениями сокетов.  
  
 [Протокол PNRP](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)  
 Описание появившейся в версии 3.5 поддержки протокола PNRP, динамической регистрации имен и регистрации имен без сервера, а также протокола разрешения имен. Эти новые функции поддерживаются пространством имен <xref:System.Net.PeerToPeer?displayProperty=nameWithType> .  
  
 [Одноранговая совместная работа](../../../docs/framework/network-programming/peer-to-peer-collaboration.md)  
 Описание появившейся в версии 3.5 поддержки одноранговой совместной работы на базе протокола PNRP. Эти новые функции поддерживаются пространством имен <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> .  
  
 [Изменения в аутентификации NTLM для HttpWebRequest в версии 3.5 с пакетом обновления 1 (SP1)](../../../docs/framework/network-programming/changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 Описание изменений безопасности в версии 3.5 с пакетом обновления 1 (SP1), влияющих на обработку интегрированной аутентификации Windows классами <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>и связанными классами в пространстве имен System.Net.  
  
 [Встроенная аутентификация Windows с расширенной защитой](../../../docs/framework/network-programming/integrated-windows-authentication-with-extended-protection.md)  
 Описание усовершенствований расширенной защиты, влияющих на обработку интегрированной аутентификации классами <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>и связанными классами в пространстве имен <xref:System.Net?displayProperty=nameWithType> и связанных пространствах имен.  
  
 [Обход NAT с помощью IPv6 и Teredo](../../../docs/framework/network-programming/nat-traversal-using-ipv6-and-teredo.md)  
 Описание усовершенствований, добавленных в пространства имен <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>и <xref:System.Net.Sockets?displayProperty=nameWithType> для поддержки обхода преобразования сетевых адресов (NAT) с помощью IPv6 и Teredo.  
  
 [Сетевая изоляция для приложений Магазина Windows](../../../docs/framework/network-programming/network-isolation-for-windows-store-apps.md)  
 Описание последствий сетевой изоляции, когда классы в пространствах имен <xref:System.Net>, <xref:System.Net.Http>и <xref:System.Net.Http.Headers> используются в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .  
  
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)  
 Ссылки на загружаемые примеры программ, в которых используются классы из пространств имен <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> .  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Net?displayProperty=nameWithType>  
 Предоставляет простой программный интерфейс для многих современных сетевых протоколов. Классы <xref:System.Net.WebRequest?displayProperty=nameWithType> и <xref:System.Net.WebResponse?displayProperty=nameWithType> в этом пространстве имен являются основой для подключаемых протоколов.  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 Определение типов и перечислений, используемых для определения политик кэширования ресурсов, получаемых с помощью классов <xref:System.Net.WebRequest?displayProperty=nameWithType> и <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 Классы, используемые в приложениях для программного доступа к параметрам конфигурации пространств имен System.Net и обновления этих параметров.  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 Классы, которые обеспечивают интерфейс программирования для современных приложений HTTP.  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 Обеспечивает поддержку коллекций заголовков HTTP, используемых пространством имен <xref:System.Net.Http?displayProperty=nameWithType>  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 Классы, формирующие и отправляющие почту по протоколу SMTP.  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 Определяет типы, используемые для представления заголовков MIME (Multipurpose Internet Mail Exchange), которые используются классами в пространстве имен <xref:System.Net.Mail?displayProperty=nameWithType> .  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 Классы для программного сбора информации о событиях, изменениях, статистике и свойствах сети.  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 Предоставляет управляемую реализацию протокола PNRP для разработчиков.  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 Предоставляет управляемую реализацию интерфейса одноранговой совместной работы для разработчиков.  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 Классы, обеспечивающие сетевые потоки для безопасного взаимодействия между узлами.  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 Предоставляет управляемую реализацию интерфейса сокетов Windows (Winsock) для разработчиков, которым нужно обеспечивать контроль доступа к сети.  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 Предоставляет управляемую реализацию интерфейса WebSocket для разработчиков.  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 Обеспечивает объектное представление универсального кода ресурсов (URI), а также простой доступ к его частям.  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 Обеспечивает поддержку аутентификации за счет расширенной защиты приложений.  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 Обеспечивает поддержку настройки аутентификации с помощью расширенной защиты приложений.  
  
## <a name="see-also"></a>См. также

- [Рекомендации по использованию протокола TLS с .NET Framework](../../../docs/framework/network-programming/tls.md)
- [Практические руководства по сетевому программированию](../../../docs/framework/network-programming/network-programming-how-to-topics.md)
- [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)
- [Примеры сетевых приложений для .NET в галерее кода MSDN](https://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)
- [Пример HttpClient](https://go.microsoft.com/fwlink/?LinkId=242550)
