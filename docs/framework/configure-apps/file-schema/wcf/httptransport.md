---
title: '&lt;httpTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 8b30c065-b32a-4fa3-8eb4-5537a9c6b897
ms.openlocfilehash: d03b92dc1e7b53a182b8065a6d4ac652f76291ba
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147438"
---
# <a name="lthttptransportgt"></a>&lt;httpTransport&gt;
Задает транспорт HTTP для передачи сообщений протокола SOAP для пользовательской привязки.  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<httpTransport >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<httpTransport allowCookies="Boolean"
               authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"
               bypassProxyOnLocal="Boolean"
               hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"
               keepAliveEnabled="Boolean"
               maxBufferSize="Integer"
               proxyAddress="Uri"
               proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous/IntegratedWindowsAuthentication"
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
|allowCookies|Логическое значение, указывающее, принимает ли клиент файлы cookie и распространяет ли он их на будущие запросы. Значение по умолчанию — `false`.<br /><br /> Этот атрибут можно использовать при взаимодействии с веб-службами ASMX, которые используют файлы Cookie. В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.|  
|authenticationScheme|Задает протокол, используемый для проверки подлинности клиентских запросов, обрабатываемых прослушивателем HTTP. Допустимы следующие значения:<br /><br /> -Хэш-кода: Задает дайджест-проверку подлинности.<br />— Negotiate: Проводит согласование с клиентом для определения схемы проверки подлинности. Если и клиент, и сервер поддерживают Kerberos, используется именно этот протокол; в противном случае используется NTLM.<br />-Ntlm: Указывает проверку подлинности NTLM.<br />— Базовый: Задает обычную проверку подлинности.<br />-Анонимный: Задает анонимную проверку подлинности.<br /><br /> Значение по умолчанию - Anonymous. Это атрибут типа <xref:System.Net.AuthenticationSchemes>. Этот атрибут может быть задан лишь один раз.|  
|bypassProxyOnLocal|Логическое значение, определяющее, будет ли выполняться обход прокси-сервера для локальных адресов. Значение по умолчанию — `false`.<br /><br /> Локальный адрес — это адрес, находящийся в локальной сети или в интрасети.<br /><br /> Windows Communication Foundation (WCF), всегда пропускает прокси, если адрес службы начинается с `http://localhost`.<br /><br /> Следует использовать имя узла (а не localhost), если необходимо, чтобы клиенты проходили через прокси при взаимодействии со службами на том же компьютере.|  
|hostnameComparisonMode|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов (URI). Допустимы следующие значения:<br /><br /> -StrongWildcard: («+») соответствует всем возможным именам узлов в контексте заданной схемы, порта и относительного URI.<br />-Exact: подстановочные знаки не<br />-WeakWildcard: (»\*«) соответствует всем возможным именам узлов в контексте заданной схемы, порта и относительного UIR, не соответствовали явным образом или посредством строгого механизма подстановочных знаков.<br /><br /> Значение по умолчанию - StrongWildcard. Это атрибут типа `System.ServiceModel.HostnameComparisonMode`.|  
|keepAliveEnabled|Логическое значение, указывающее, следует ли устанавливать постоянное подключение к интернет-ресурсу.|  
|maxBufferSize|Положительное целое число, указывающее максимальный размер буфера. Значение по умолчанию - 524 288|  
|proxyAddress|Универсальный код ресурса (URI), задающий адрес прокси-сервера HTTP. Если параметр `useSystemWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`. Значение по умолчанию — `null`.|  
|proxyAuthenticationScheme|Задает протокол, используемый для проверки подлинности клиентских запросов, обрабатываемых прокси-сервером HTTP. Допустимы следующие значения:<br /><br /> -None: Проверка подлинности не выполняется.<br />-Хэш-кода: Задает дайджест-проверку подлинности.<br />— Negotiate: Проводит согласование с клиентом для определения схемы проверки подлинности. Если и клиент, и сервер поддерживают Kerberos, используется именно этот протокол; в противном случае используется NTLM.<br />-Ntlm: Указывает проверку подлинности NTLM.<br />— Базовый: Задает обычную проверку подлинности.<br />-Анонимный: Задает анонимную проверку подлинности.<br />-IntegratedWindowsAuthentication: Задает проверку подлинности Windows.<br /><br /> Значение по умолчанию - Anonymous. Это атрибут типа <xref:System.Net.AuthenticationSchemes>.|  
|realm|Строка, задающая область для использования на прокси-сервере. Значение по умолчанию - пустая строка.<br /><br /> Серверы используют области для разделения защищенных ресурсов. Каждый раздел может иметь свою собственную схему проверки подлинности и/или базу данных авторизации. Области используются только для обычной проверки подлинности и дайджест-проверки подлинности. После успешного прохождения клиентом проверки подлинности ее результаты действительны для всех ресурсов в данной области. Подробное описание областей, см. в разделе RFC 2617 по [веб-сайте IETF](https://www.ietf.org).|  
|transferMode|Указывает, следует ли буферизировать сообщения или передавать их потоком по запросу или ответу. Допустимы следующие значения:<br /><br /> -Buffered: Сообщения запроса и ответа буферизуются.<br />-Потоковой передачи: Сообщения запроса и ответа передаются потоком.<br />-StreamedRequest: Сообщение запроса передается потоком, а сообщение ответа буферизуется.<br />-StreamedResponse: Сообщение запроса буферизуется, а сообщение ответа передается потоком.<br /><br /> Значение по умолчанию - Buffered. Это атрибут типа <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Логическое значение, указывающее, разрешено ли на сервере совместное использование небезопасных подключений. Значение по умолчанию — `false`. Если оно разрешено, проверка подлинности NTLM выполняется один раз для каждого подключения по протоколу TCP.|  
|useDefaultWebProxy|Логическое значение, указывающее, используются ли настройки прокси-сервера компьютера или пользователя. Значение по умолчанию — `true`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Привязка >](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Элемент `httpTransport` является начальной точкой для создания пользовательской привязки, реализующей транспортный протокол HTTP. Протокол HTTP является основным транспортом, используемым в целях взаимодействия. Этот транспорт поддерживается с Windows Communication Foundation (WCF) для взаимодействия с другими стеки не WCF веб - служб.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.HttpTransportElement>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Выбор транспорта](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
