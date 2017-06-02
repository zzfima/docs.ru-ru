---
title: "Основные сведения о проблемах и исключениях WebRequest | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 74a361a5-e912-42d3-8f2e-8e9a96880a2b
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Основные сведения о проблемах и исключениях WebRequest
<xref:System.Net.WebRequest> и его производные классы \(<xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest> и <xref:System.Net.FileWebRequest>\) вызывают исключений для обозначения анормалное состояние.  Иногда разрешения этих проблем не очевидно.  
  
## Решения  
 Проверьте свойство <xref:System.Net.WebException.Status%2A><xref:System.Net.WebException>, чтобы определить проблему.  В следующей таблице показано несколько значений состояния и некоторые возможные разрешения.  
  
|Состояние|Подробные сведения|Решение|  
|---------------|------------------------|-------------|  
|<xref:System.Net.WebExceptionStatus><br /><br /> \-или\-<br /><br /> <xref:System.Net.WebExceptionStatus>|Проблема с основным гнездом.  Соединение может быть сброшено.|Повторное соединение и отправить запрос.<br /><br /> Убедитесь, что последний пакет обновления установить.<br /><br /> Увеличьте значение свойства <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A?displayProperty=fullName>.<br /><br /> Присвойте параметру <xref:System.Net.HttpWebRequest.KeepAlive%2A?displayProperty=fullName> значение `false`.<br /><br /> Увеличьте количество максимальных соединений с свойством <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>.<br /><br /> Проверьте конфигурацию учетной записи\-посредника.<br /><br /> Если используется протокол SSL, убедитесь, что серверный процесс имеет разрешения на доступ к хранилищу сертификатов.<br /><br /> Если отправка большого количества данных, установите <xref:System.Net.HttpWebRequest.AllowWriteStreamBuffering%2A> к `false`.|  
|<xref:System.Net.WebExceptionStatus>|Сертификат сервера не удалось проверить.|Попробуйте открыть универсальный код ресурса \(uri\) с помощью Internet Explorer.  Включить все предупреждения безопасности, отображаемые IE.  Если не удается разрешить предупреждение безопасности, можно создать класс, реализующий <xref:System.Net.ICertificatePolicy> политики сертификата, который возвращает `true` и передает его в <xref:System.Net.ServicePointManager.CertificatePolicy%2A>.<br /><br /> См. [http:\/\/support.microsoft.com\/?id\=823177](http://go.microsoft.com/fwlink/?LinkID=179653) раздел.<br /><br /> Убедитесь, что сертификат центра сертификации, сертификат сервера подписывало добавить в список надежных центра сертификации в Internet Explorer.<br /><br /> Убедитесь, что имя узла в url\-адресе соответствует общему имени для сертификата сервера.|  
|<xref:System.Net.WebExceptionStatus>|Произошла ошибка в транзакции по протоколу SSL или проблема сертификата.|В платформе .NET Framework версии 1.1 поддерживает только версию 3.0 протокола SSL.  Если сервер использует протокол TLS только версии 1.0 или версии 2.0 протокола SSL, выдается исключение.  Обновления к платформе .NET Framework версии 2.0 и набор <xref:System.Net.ServicePointManager.SecurityProtocol%2A> в соответствии с сервером.<br /><br /> Сертификат клиента был подписан центром сертификации \(центром сертификации, в течение которого сервер не доверяет.  Установите сертификат CA на сервере.  См. [http:\/\/support.microsoft.com\/?id\=332077](http://go.microsoft.com/fwlink/?LinkID=179654) раздел.<br /><br /> Убедитесь, чтобы получить последний пакет обновления быть задано.|  
|<xref:System.Net.WebExceptionStatus>|Сбой подключения.|Брандмауэр или отключить соединение прокси.  Измените брандмауэра или прокси, чтобы разрешить соединение.<br /><br /> Явное задание меток для <xref:System.Net.WebProxy> в клиентском приложении, вызвав конструктор <xref:System.Net.WebProxy> \(WebServiceProxyClass.Proxy \= новые WebProxy \([http:\/\/server:80](http://server/) true\)\).<br /><br /> Запустите Filemon или Regmon, чтобы убедиться, что идентификатор рабочего процесса имеет необходимые разрешения на доступ к WSPWSP.dll, HKLM\\System\\CurrentControlSet\\Services\\DnsCache или HKLM\\System\\CurrentControlSet\\Services\\WinSock2.|  
|<xref:System.Net.WebExceptionStatus>|Служба имени домена не может разрешить данное имя узла.|Настройте учетную запись\-посредник.  См. [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655) раздел.<br /><br /> Убедитесь, что они заданы программное обеспечение или брандмауэр антивируса не блокируются соединение.|  
|<xref:System.Net.WebExceptionStatus>|<xref:System.Net.WebRequest.Abort%2A> было вызываются или произошла ошибка.|Эта проблема может быть вызвана тяжелой нагрузке на стороне клиента или сервера.  Уменьшите нагрузку.<br /><br /> Увеличьте устанавливать <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>.<br /><br /> См. [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656) для изменения параметров производительности веб\-службы.|  
|<xref:System.Net.WebExceptionStatus>|Приложение пытался записать в гнезду, которое уже было закрыто.|Клиент или сервер перегружатьы.  Уменьшите нагрузку.<br /><br /> Увеличьте устанавливать <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A>.<br /><br /> См. [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656) для изменения параметров производительности веб\-службы.|  
|<xref:System.Net.WebExceptionStatus>|Превышен набор ограничений на длину \(<xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>\) сообщения.|Увеличьте значение свойства <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>.|  
|<xref:System.Net.WebExceptionStatus>|Служба имени домена не может разрешить данное имя узла прокси\-сервера.|Настройте учетную запись\-посредник.  См. [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655) раздел.<br /><br /> Обеспечьте <xref:System.Net.HttpWebRequest> для использования без прокси путем задания свойства <xref:System.Net.HttpWebRequest.Proxy%2A> к `null`.|  
|<xref:System.Net.WebExceptionStatus>|Ответ от сервера не является допустимым ответа HTTP.  Эта проблема возникает, если платформа .NET Framework обнаруживает, что ответ сервера не соответствует требованиям стандарта RFC HTTP 1.1.  Эта проблема может возникнуть, когда ответ содержит неверные заголовки или неправильный заголовок HTTP delimiters.RFC 2616 указывает 1.1 и допустимый формат ответа от сервера.  Дополнительные сведения см. в разделе [http:\/\/www.ietf.org](http://go.microsoft.com/fwlink/?LinkID=147388).|Получите трассировки сети транзакций и просмотрите заголовки в ответе.<br /><br /> Если приложение требует ответ сервера без разбора \(это может быть проблемой безопасности\), установите `useUnsafeHeaderParsing` к `true` в файле конфигурации.  Дополнительные сведения см. в разделе [Элемент \<httpWebRequest\> \(параметры сети\)](../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md).|  
  
## См. также  
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.Dns>