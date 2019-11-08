---
title: <httpTransport>
ms.date: 03/30/2017
ms.assetid: 8b30c065-b32a-4fa3-8eb4-5537a9c6b897
ms.openlocfilehash: b3558db6018d79f0fad27ff28657bfadb5637467
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736764"
---
# <a name="httptransport"></a>\<Хттптранспорт >
Задает транспорт HTTP для передачи сообщений протокола SOAP для пользовательской привязки.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)\
привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<хттптранспорт >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<httpTransport allowCookies="Boolean"
               authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"
               bypassProxyOnLocal="Boolean"
               hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"
               keepAliveEnabled="Boolean"
               maxBufferSize="Integer"
               proxyAddress="Uri"
               proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"
               realm="String"
               transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
               unsafeConnectionNtlmAuthentication="Boolean"
               useDefaultWebProxy="Boolean" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|allowCookies|Логическое значение, указывающее, принимает ли клиент файлы cookie и распространяет ли он их на будущие запросы. Значение по умолчанию: `false`.<br /><br /> Этот атрибут можно использовать при взаимодействии с веб-службами ASMX, которые используют файлы Cookie. В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.|  
|authenticationScheme|Задает протокол, используемый для проверки подлинности клиентских запросов, обрабатываемых прослушивателем HTTP. Допустимы следующие значения:<br /><br /> -Digest: указывает дайджест-проверку подлинности.<br />-Negotiate: согласовывается с клиентом для определения схемы проверки подлинности. Если и клиент, и сервер поддерживают Kerberos, используется именно этот протокол; в противном случае используется NTLM.<br />-NTLM: указывает проверку подлинности NTLM.<br />-Basic: указывает обычную проверку подлинности.<br />Анонимный. Указывает анонимную проверку подлинности.<br /><br /> Значение по умолчанию - Anonymous. Это атрибут типа <xref:System.Net.AuthenticationSchemes>. Этот атрибут может быть задан лишь один раз.|  
|bypassProxyOnLocal|Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов. Значение по умолчанию: `false`.<br /><br /> Локальный адрес — это адрес, находящийся в локальной сети или в интрасети.<br /><br /> Windows Communication Foundation (WCF) всегда пропускает прокси-сервер, если адрес службы начинается с `http://localhost`.<br /><br /> Следует использовать имя узла (а не localhost), если необходимо, чтобы клиенты проходили через прокси при взаимодействии со службами на том же компьютере.|  
|hostnameComparisonMode|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI). Допустимы следующие значения:<br /><br /> -StrongWildcard: ("+") соответствует всем возможным именам узлов в контексте указанной схемы, порта и относительного URI.<br />-СОВПАД: нет подстановочных знаков<br />-Веаквилдкард: ("\*") соответствует всем возможным именам узлов в контексте указанной схемы, порта и относительных УИР, которые не совпали явным образом или с помощью механизма строгих подстановочных знаков.<br /><br /> Это атрибут типа <xref:System.ServiceModel.HostNameComparisonMode>. Значение по умолчанию: <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>.|  
|keepAliveEnabled|Логическое значение, указывающее, следует ли устанавливать постоянное подключение к интернет-ресурсу.|  
|maxBufferSize|Положительное целое число, указывающее максимальный размер буфера. Значение по умолчанию - 524 288|  
|proxyAddress|Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP. Если параметр `useSystemWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`. Значение по умолчанию: `null`.|  
|proxyAuthenticationScheme|Задает протокол, используемый для проверки подлинности клиентских запросов, обрабатываемых прокси-сервером HTTP. Допустимы следующие значения:<br /><br /> -None: проверка подлинности не выполняется.<br />-Digest: указывает дайджест-проверку подлинности.<br />-Negotiate: согласовывается с клиентом для определения схемы проверки подлинности. Если и клиент, и сервер поддерживают Kerberos, используется именно этот протокол; в противном случае используется NTLM.<br />-NTLM: указывает проверку подлинности NTLM.<br />-Basic: указывает обычную проверку подлинности.<br />Анонимный. Указывает анонимную проверку подлинности.<br /><br /> Значение по умолчанию - Anonymous. Это атрибут типа <xref:System.Net.AuthenticationSchemes>. Обратите внимание, что <xref:System.Net.AuthenticationSchemes.IntegratedWindowsAuthentication?displayProperty=nameWithType> не поддерживается.|  
|realm|Строка, задающая область для использования на прокси-сервере. Значение по умолчанию - пустая строка.<br /><br /> Серверы используют области для разделения защищенных ресурсов. Каждый раздел может иметь свою собственную схему проверки подлинности и/или базу данных авторизации. Области используются только для обычной проверки подлинности и дайджест-проверки подлинности. После успешного прохождения клиентом проверки подлинности ее результаты действительны для всех ресурсов в данной области. Подробное описание сфер см. в документе RFC 2617 на [веб-сайте IETF](https://www.ietf.org).|  
|transferMode|Указывает, следует ли буферизировать сообщения или передавать их потоком по запросу или ответу. Допустимы следующие значения:<br /><br /> — Буферизовано: сообщения запроса и ответа помещаются в буфер.<br />— Потоковая передача. сообщения запроса и ответа передаются в потоковом режиме.<br />-Стреамедрекуест: сообщение запроса передается в потоковую передачу, а ответное сообщение — в буфер.<br />-Стреамедреспонсе: сообщение запроса буферизовано, а ответное сообщение передается в потоковую передачу.<br /><br /> Значение по умолчанию - Buffered. Это атрибут типа <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Логическое значение, указывающее, разрешено ли на сервере совместное использование небезопасных подключений. Значение по умолчанию: `false`. Если оно разрешено, проверка подлинности NTLM выполняется один раз для каждого подключения по протоколу TCP.|  
|useDefaultWebProxy|Логическое значение, указывающее, используются ли настройки прокси-сервера компьютера или пользователя. Значение по умолчанию: `true`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствуют  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[> привязки \<](bindings.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Заметки  
 Элемент `httpTransport` является начальной точкой для создания пользовательской привязки, реализующей транспортный протокол HTTP. Протокол HTTP является основным транспортом, используемым в целях взаимодействия. Этот транспорт поддерживается Windows Communication Foundation (WCF) для обеспечения взаимодействия с другими стеками веб-служб, отличными от WCF.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.HttpTransportElement>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Транспорты](../../../wcf/feature-details/transports.md)
- [Выбор транспорта](../../../wcf/feature-details/choosing-a-transport.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
