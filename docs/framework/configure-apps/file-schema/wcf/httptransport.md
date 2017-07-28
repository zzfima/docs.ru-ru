---
title: "&lt;httpTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 8b30c065-b32a-4fa3-8eb4-5537a9c6b897
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;httpTransport&gt;
Задает транспорт HTTP для передачи сообщений протокола SOAP для пользовательской привязки.  
  
## Синтаксис  
  
```  
  
<httpTransport  
    allowCookies=Boolean"  
    authenticationScheme="Digest/Negotiate/Ntlm/Basic/Anonymous"  
    bypassProxyOnLocal=Boolean"  
    hostnameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
    keepAliveEnabled="Boolean"  
    maxBufferSize="Integer"  
    proxyAddress="Uri"  
    proxyAuthenticationScheme="None/Digest/Negotiate/Ntlm/Basic/Anonymous"  
IntegratedWindowsAuthentication: Specifies Windows authentication"  
    realm="String"  
    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"  
        unsafeConnectionNtlmAuthentication="Boolean"  
        useDefaultWebProxy="Boolean" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|allowCookies|Логическое значение, указывающее, принимает ли клиент файлы cookie и распространяет ли он их на будущие запросы.  Значение по умолчанию — `false`.<br /><br /> Этот атрибут можно использовать при взаимодействии с веб\-службами ASMX, которые используют файлы Cookie.  В этом случае можно быть уверенным, что файлы cookie, возвращаемые с сервера, автоматически копируются во все последующие клиентские запросы к этой службе.|  
|authenticationScheme|Задает протокол, используемый для проверки подлинности клиентских запросов, обрабатываемых прослушивателем HTTP.  Допустимы следующие значения:<br /><br /> -   Digest: задает дайджест\-проверку подлинности.<br />-   Negotiate: проводит согласование с клиентом для определения схемы проверки подлинности.  Если и клиент, и сервер поддерживают Kerberos, используется именно этот протокол; в противном случае используется NTLM.<br />-   Ntlm: задает проверку подлинности NTLM.<br />-   Basic: задает обычную проверку подлинности.<br />-   Anonymous: задает анонимную проверку подлинности.<br /><br /> Значение по умолчанию \- Anonymous.  Это атрибут типа <xref:System.Net.AuthenticationSchemes>.  Этот атрибут может быть задан лишь один раз.|  
|bypassProxyOnLocal|Логическое значение, определяющее, будет ли выполняться обход прокси\-сервера для локальных адресов.  Значение по умолчанию — `false`.<br /><br /> Локальный адрес — это адрес, находящийся в локальной сети или в интрасети.<br /><br /> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] всегда пропускает прокси, если адрес службы начинается с http:\/\/localhost.<br /><br /> Следует использовать имя узла \(а не localhost\), если необходимо, чтобы клиенты проходили через прокси при взаимодействии со службами на том же компьютере.|  
|hostnameComparisonMode|Задает режим сравнения имен узлов HTTP для анализа универсальных кодов ресурсов \(URI\).  Допустимы следующие значения:<br /><br /> -   StrongWildcard: \(«\+»\) соответствует всем возможным именам узлов в контексте заданной схемы, порта и относительного универсального кода ресурса \(URI\).<br />-   Exact: подстановочные знаки отсутствуют<br />-   WeakWildcard: \(\*\) соответствует всем возможным именам узлов в контексте заданной схемы, порта и относительного универсального кода ресурса \(URI\), которые не соответствовали явным образом или посредством строгого механизма подстановочных знаков.<br /><br /> Значение по умолчанию \- StrongWildcard.  Это атрибут типа <xref:System.ServiceModel.HostnameComparisonMode>.|  
|keepAliveEnabled|Логическое значение, указывающее, следует ли устанавливать постоянное подключение к интернет\-ресурсу.|  
|maxBufferSize|Положительное целое число, указывающее максимальный размер буфера.  Значение по умолчанию \- 524 288|  
|proxyAddress|Универсальный код ресурса \(URI\), задающий адрес прокси\-сервера HTTP.  Если параметр `useSystemWebProxy` имеет значение `true`, данный параметр должен иметь значение `null`.  Значение по умолчанию — `null`.|  
|proxyAuthenticationScheme|Задает протокол, используемый для проверки подлинности клиентских запросов, обрабатываемых прокси\-сервером HTTP.  Допустимы следующие значения:<br /><br /> -   None: проверка подлинности не выполняется.<br />-   Digest: задает дайджест\-проверку подлинности.<br />-   Negotiate: проводит согласование с клиентом для определения схемы проверки подлинности.  Если и клиент, и сервер поддерживают Kerberos, используется именно этот протокол; в противном случае используется NTLM.<br />-   Ntlm: задает проверку подлинности NTLM.<br />-   Basic: задает обычную проверку подлинности.<br />-   Anonymous: задает анонимную проверку подлинности.<br />-   IntegratedWindowsAuthentication: задает проверку подлинности Windows.<br /><br /> Значение по умолчанию \- Anonymous.  Это атрибут типа <xref:System.Net.AuthenticationSchemes>.|  
|realm|Строка, задающая область для использования на прокси\-сервере.  Значение по умолчанию \- пустая строка.<br /><br /> Серверы используют области для разделения защищенных ресурсов.  Каждый раздел может иметь свою собственную схему проверки подлинности и\/или базу данных авторизации.  Области используются только для обычной проверки подлинности и дайджест\-проверки подлинности.  После успешного прохождения клиентом проверки подлинности ее результаты действительны для всех ресурсов в данной области.  Подробное описание областей см. в документе RFC 2617 по адресу http:\/\/www.ietf.org.|  
|transferMode|Указывает, следует ли буферизировать сообщения или передавать их потоком по запросу или ответу.  Допустимы следующие значения:<br /><br /> -   Buffered: сообщения запроса и ответа буферизируются.<br />-   Streamed: сообщения запроса и ответа передаются потоком.<br />-   StreamedRequest: сообщение запроса передается потоком, а сообщение ответа буферизируется.<br />-   StreamedResponse: сообщение запроса буферизируется, а сообщение ответа передается потоком.<br /><br /> Значение по умолчанию \- Buffered.  Это атрибут типа <xref:System.ServiceModel.TransferMode>.|  
|unsafeConnectionNtlmAuthentication|Логическое значение, указывающее, разрешено ли на сервере совместное использование небезопасных подключений.  Значение по умолчанию — `false`.  Если оно разрешено, проверка подлинности NTLM выполняется один раз для каждого подключения по протоколу TCP.|  
|useDefaultWebProxy|Логическое значение, указывающее, используются ли настройки прокси\-сервера компьютера или пользователя.  Значение по умолчанию — `true`.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Заметки  
 Элемент `httpTransport` является начальной точкой для создания пользовательской привязки, реализующей транспортный протокол HTTP.  Протокол HTTP является основным транспортом, используемым в целях взаимодействия.  Этот транспорт поддерживается службой [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], чтобы обеспечить взаимодействие с другими стеками веб\-служб, не относящимися к [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].  
  
## См. также  
 <xref:System.ServiceModel.Configuration.HttpTransportElement>   
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Выбор транспортов](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)