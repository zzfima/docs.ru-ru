---
title: Сетевое программирование в .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 1e7f0123ab07fd4e83eea957b72bf79eeeecef2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74204697"
---
# <a name="network-programming-in-the-net-framework"></a>Сетевое программирование в .NET Framework
Microsoft .NET Framework обеспечивает многоуровневую, расширяемую и управляемую реализацию служб Интернета, которую можно легко и быстро интегрировать в приложения. В сетевых приложениях можно использовать подключаемые протоколы, которые позволяют автоматически применять новые протоколы Интернета, или управляемую реализацию интерфейса сокетов Windows, дающую возможность работать с сетью на уровне сокетов.  
  
## <a name="in-this-section"></a>Содержание  

 [Введение в подключаемые протоколы](introducing-pluggable-protocols.md)  
 Описание способов доступа к интернет-ресурсу вне зависимости от используемого протокола доступа  
  
 [Запрос данных](requesting-data.md)  
 Объясняется, как использовать подключаемые протоколы для отправки и приема данных из интернет-ресурсов.  
  
 [Программирование подключаемых протоколов](programming-pluggable-protocols.md)  
 Объясняется, как создать классы для определенных протоколов чтобы реализовать подключаемые протоколы.  
  
 [Использование протоколов приложений](using-application-protocols.md)  
 Описание процесса создания приложений, которые используют сетевые протоколы, такие как TCP, UDP и HTTP.  
  
 [Протокол IP версии 6](internet-protocol-version-6.md)  
 Описание преимуществ протокола IP версии 6 (IPv6) над текущей версией набора протоколов IP (IPv4); описание адресации, маршрутизации и автоматической настройки IPv6, а также процедур включения и выключения IPv6.  
  
 [Настройка веб-приложений](configuring-internet-applications.md)  
 Описание использования файлов конфигурации .NET Framework для настройки интернет-приложений.  
  
 [Трассировка сети в .NET Framework](network-tracing.md)  
 Описание использования трассировки сети для получения сведений о вызовах методов и о сетевом трафике, созданном управляемым приложением.  
  
 [Управление кэшем для сетевых приложений](cache-management-for-network-applications.md)  
 Описание использования кэширования для приложений, которые используют классы <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>и <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> .  
  
 [Безопасность в сетевом программировании](security-in-network-programming.md)  
 Описание использования стандартных методов безопасности и аутентификации в Интернете.  
  
 [Рекомендации по использованию классов System.Net](best-practices-for-system-net-classes.md)  
 Советы по достижению максимальной эффективности разрабатываемых интернет-приложений.  
  
 [Доступ к Интернету через прокси-сервер](accessing-the-internet-through-a-proxy.md)  
 Описание порядка настройки прокси.  
  
 [NetworkInformation](networkinformation.md)  
 Описание порядка сбора информации о событиях, изменениях, статистике и свойствах сети, а также порядка определения доступности удаленного узла с помощью класса <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> .  
  
 [Изменения пространства имен System.Uri в версии 2.0](changes-to-the-system-uri-namespace-in-version-2-0.md)  
 Описание нескольких изменений, внесенных в класс <xref:System.Uri?displayProperty=nameWithType> в версии 2.0 для устранения неправильного поведения, повышения удобства работы и безопасности.  
  
 [Поддержка международного кода ресурса в System.Uri](international-resource-identifier-support-in-system-uri.md)  
 Описание усовершенствований класса <xref:System.Uri?displayProperty=nameWithType> в версиях 3.5, 3.0 с пакетом обновления 1 (SP1) и 2.0 с пакетом обновления 1 (SP1), касающихся поддержки международного идентификатора ресурсов (IRI) и международных доменных имен (IDN).  
  
 [Улучшения производительности сокетов в версии 3.5](socket-performance-enhancements-in-version-3-5.md)  
 Описание набора усовершенствований класса <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> в версиях 3.5, 3.0 с пакетом обновления 1 (SP1) и 2.0 с пакетом обновления 1 (SP1), которые предоставляют альтернативный шаблон асинхронной модели, который может использоваться специализированными высокопроизводительными приложениями сокетов.  
  
 [Протокол PNRP](peer-name-resolution-protocol.md)  
 Описание появившейся в версии 3.5 поддержки протокола PNRP, динамической регистрации имен и регистрации имен без сервера, а также протокола разрешения имен. Эти новые функции поддерживаются пространством имен <xref:System.Net.PeerToPeer?displayProperty=nameWithType> .  
  
 [Одноранговая совместная работа](peer-to-peer-collaboration.md)  
 Описание появившейся в версии 3.5 поддержки одноранговой совместной работы на базе протокола PNRP. Эти новые функции поддерживаются пространством имен <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> .  
  
 [Изменения в аутентификации NTLM для HttpWebRequest в версии 3.5 с пакетом обновления 1 (SP1)](changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 Описание изменений безопасности в версии 3.5 с пакетом обновления 1 (SP1), влияющих на обработку интегрированной аутентификации Windows классами <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>и связанными классами в пространстве имен System.Net.  
  
 [Встроенная аутентификация Windows с расширенной защитой](integrated-windows-authentication-with-extended-protection.md)  
 Описание усовершенствований расширенной защиты, влияющих на обработку интегрированной аутентификации классами <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>и связанными классами в пространстве имен <xref:System.Net?displayProperty=nameWithType> и связанных пространствах имен.  
  
 [Обход NAT с помощью IPv6 и Teredo](nat-traversal-using-ipv6-and-teredo.md)  
 Описание усовершенствований, добавленных в пространства имен <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>и <xref:System.Net.Sockets?displayProperty=nameWithType> для поддержки обхода преобразования сетевых адресов (NAT) с помощью IPv6 и Teredo.  
  
 [Сетевая изоляция для приложений Магазина Windows](network-isolation-for-windows-store-apps.md)  
 Описание последствий сетевой изоляции, когда классы в пространствах имен <xref:System.Net>, <xref:System.Net.Http>и <xref:System.Net.Http.Headers> используются в приложениях Microsoft Store для Windows 8.x.  
  
 [Примеры сетевого программирования](network-programming-samples.md)  
 Ссылки на загружаемые примеры программ, в которых используются классы из пространств имен <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> .  
  
## <a name="reference"></a>Справочник  
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
 Предоставляет объектное представление универсального идентификатора ресурсов (URI) и обеспечивает простой доступ к его частям.  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 Обеспечивает поддержку аутентификации за счет расширенной защиты приложений.  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 Обеспечивает поддержку настройки аутентификации с помощью расширенной защиты приложений.  
  
## <a name="see-also"></a>См. также раздел

- [Рекомендации по использованию протокола TLS с .NET Framework](tls.md)
- [Практические руководства по сетевому программированию](network-programming-how-to-topics.md)
- [Примеры сетевого программирования](network-programming-samples.md)
- [Пример HttpClient](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
