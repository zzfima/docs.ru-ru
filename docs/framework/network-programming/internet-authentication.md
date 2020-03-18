---
title: Аутентификация в Интернете
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [.NET Framework], classes
- IAuthenticationModule interface
- ICredentialLookup interface
- CredentialCache class, about CredentialCache class
- receiving data, authentication
- AuthenticationManager class, about AuthenticationManager class
- Internet, authentication
- sending data, authentication
- network resources, authentication
- user authentication, classes for authentication
- NetworkCredential class, about NetworkCredential class
- client authentication, classes for authentication
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
ms.openlocfilehash: 3e0b5cd58270cec758db5d4dad6f3ad48962921a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047920"
---
# <a name="internet-authentication"></a>Аутентификация в Интернете
Классы <xref:System.Net> поддерживают ряд механизмов проверки подлинности клиентов, включая стандартные методы проверки подлинности в Интернете: базовая проверка подлинности, дайджест-проверка подлинности, проверка подлинности согласованием, проверка подлинности NTLM, проверка подлинности Kerberos, а также создаваемые пользовательские методы.  
  
 Учетные данные проверки подлинности хранятся в классах <xref:System.Net.NetworkCredential> и <xref:System.Net.CredentialCache>, которые реализуют интерфейс <xref:System.Net.ICredentials>. Когда один из этих классов запрашивается на предоставление учетных данных, он возвращает экземпляр класса **NetworkCredential**. Процесс проверки подлинности управляется классом <xref:System.Net.AuthenticationManager>, а фактический процесс проверки подлинности выполняется классом модуля проверки подлинности, который реализует интерфейс <xref:System.Net.IAuthenticationModule>. Перед использованием необходимо зарегистрировать пользовательский модуль проверки подлинности с помощью **AuthenticationManager**. Модули для базовой проверки подлинности, дайджест-проверки подлинности, проверки подлинности согласованием, проверки подлинности NTLM, проверки подлинности Kerberos зарегистрированы по умолчанию.  
  
 Класс **NetworkCredential** хранит набор учетных данных, связанных с одним интернет-ресурсом, определяемым по URI, и возвращает их в ответ на любой вызов метода <xref:System.Net.NetworkCredential.GetCredential%2A>. Класс **NetworkCredential** обычно используют приложения, которые обращаются к ограниченному числу интернет-ресурсов, или приложения, которые используют один набор учетных данных во всех случаях.  
  
 Класс **CredentialCache** хранит коллекцию учетных записей для различных веб-ресурсов. При вызове метода <xref:System.Net.CredentialCache.GetCredential%2A> класс **CredentialCache** возвращает правильный набор учетных данных, как это определяется URI веб-ресурса и запрошенной схемой проверки подлинности. Приложения, использующие множество интернет-ресурсов с разными схемами проверки подлинности, получают эффект от класса **CredentialCache**, поскольку он хранит все учетные записи и предоставляет их по запросу.  
  
 Когда интернет-ресурс запрашивает проверку подлинности, метод <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> отправляет <xref:System.Net.WebRequest> в **AuthenticationManager** вместе с запросом учетных данных. Затем запрос проходит проверку подлинности согласно следующей процедуре.  
  
1. **AuthenticationManager** вызывает метод <xref:System.Net.IAuthenticationModule.Authenticate%2A> в каждом из зарегистрированных модулей проверки подлинности в порядке их регистрации. **AuthenticationManager** использует первый модуль, который не возвращает **null**, для выполнения процесса проверки подлинности. Детали процесса зависят от типа используемого модуля проверки подлинности.  
  
2. По завершении процесса проверки подлинности модуль проверки подлинности возвращает <xref:System.Net.Authorization> в класс **WebRequest**, содержащий сведения, необходимые для доступа к интернет-ресурсу.  
  
 Некоторые схемы проверки могут проверять пользователя без выполнения запроса на доступ к ресурсу. Приложение может сэкономить время за счет предварительной проверки подлинности пользователя на доступ к ресурсу, устраняя по меньшей мере один цикл обращения к серверу. Или оно может провести проверку подлинности во время запуска программы для более оперативного реагирования на запросы пользователя позднее. Схемы проверки подлинности, которые могут использовать предварительную проверку подлинности, задают для свойства <xref:System.Net.IAuthenticationModule.PreAuthenticate%2A> значение **true**.  
  
## <a name="see-also"></a>См. также раздел

- [Обычная и дайджест-проверка подлинности](basic-and-digest-authentication.md)
- [Проверка подлинности NTLM и Kerberos](ntlm-and-kerberos-authentication.md)
- [Безопасность в сетевом программировании](security-in-network-programming.md)
