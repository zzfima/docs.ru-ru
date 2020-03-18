---
title: Наследование от класса WebResponse
ms.date: 03/30/2017
helpviewer_keywords:
- Deriving from WebResponse
ms.assetid: f11d4866-a199-4087-9306-a5a4c18b13db
ms.openlocfilehash: bd06928b08eb085ef13371687fb1e5b92c6c1d86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048583"
---
# <a name="deriving-from-webresponse"></a>Наследование от класса WebResponse
<xref:System.Net.WebResponse> — это абстрактный базовый класс, который предоставляет базовые методы и свойства для создания обработчика ответов определенного протокола в соответствии с требованиями модели подключаемых протоколов .NET Framework. Приложения, использующие класс <xref:System.Net.WebRequest> для запроса данных ресурсов, получают ответы в **WebResponse**. Потомки класса **WebResponse** для определенных протоколов должны реализовывать абстрактные члены класса **WebResponse**.  
  
 Связанный класс **WebRequest** должен создавать потомки **WebResponse**. Например, экземпляры <xref:System.Net.HttpWebResponse> создаются только в результате вызова <xref:System.Net.HttpWebRequest.GetResponse%2A?displayProperty=nameWithType> или <xref:System.Net.HttpWebRequest.EndGetResponse%2A?displayProperty=nameWithType>. Каждый **WebResponse** содержит результат запроса к ресурсу и не предназначен для повторного использования.  
  
## <a name="contentlength-property"></a>Свойство ContentLength  
 Свойство <xref:System.Net.WebResponse.ContentLength%2A> указывает число байтов данных, доступных в потоке, возвращенном методом <xref:System.Net.WebResponse.GetResponseStream%2A>. Свойство **ContentLength** не учитывает число байтов в заголовке или метаданных, возвращаемых сервером. Оно определяет только размер данных в самом запрошенном ресурсе.  
  
## <a name="contenttype-property"></a>Свойство ContentType  
 Свойство <xref:System.Net.WebResponse.ContentType%2A> предоставляет особые сведения, которые необходимы протоколу для отправки клиенту, чтобы идентифицировать тип отправляемого сервером содержимого. Обычно это тип MIME возвращаемых данных.  
  
## <a name="headers-property"></a>Свойство Headers  
 Свойство <xref:System.Net.WebResponse.Headers%2A> содержит произвольную коллекцию пар "имя-значение" для метаданных, связанных с ответом. В свойство **Headers** можно включать любые метаданные для протокола, которые могут быть выражены в виде пар "имя-значение".  
  
 Чтобы использовать метаданные заголовка, применять свойство **Headers** необязательно. Относящиеся к протоколу метаданные могут предоставляться в виде свойств. Например, свойство <xref:System.Net.HttpWebResponse.LastModified%2A?displayProperty=nameWithType> предоставляет заголовок HTTP **Last-Modified**. Если метаданные заголовка предоставляются в виде свойства, необходимо запретить установку этого свойства с использованием свойства **Headers**.  
  
## <a name="responseuri-property"></a>Свойство ResponseUri  
 Свойство <xref:System.Net.WebResponse.ResponseUri%2A> содержит URI ресурса, который фактически предоставил ответ. Для протоколов, которые не поддерживают перенаправление, свойство **ResponseUri** будет иметь то же значение, что и свойство <xref:System.Net.WebRequest.RequestUri%2A> объекта **WebRequest**, который создал ответ. Если протокол поддерживает перенаправление запроса, свойство **ResponseUri** будет содержать URI ответа.  
  
## <a name="close-method"></a>Метод Close  
 Метод <xref:System.Net.WebResponse.Close%2A> закрывает любые подключения, установленные запросом или ответом, и освобождает ресурсы, используемые ответом. Метод **Close** закрывает любые экземпляры потока, используемые ответом, однако не вызывает исключение, если поток ответа был ранее закрыт посредством вызова метода <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.  
  
## <a name="getresponsestream-method"></a>Метод GetResponseStream  
 Метод <xref:System.Net.WebResponse.GetResponseStream%2A> возвращает поток, содержащий ответ от запрошенного ресурса. Поток ответа содержит только данные, возвращаемые ресурсом. Заголовок и любые метаданные, включаемые в ответ, должны быть исключены и предоставляются приложению с помощью свойств определенного протокола или свойства **Headers**.  
  
 Экземпляр потока, возвращаемый методом **GetResponseStream**, принадлежит приложению. Его можно закрыть, не закрывая **WebResponse**. По соглашению вызов метода **WebResponse.Close** также закрывает поток, возвращаемый методом **GetResponse**.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.WebResponse>
- <xref:System.Net.HttpWebResponse>
- <xref:System.Net.FileWebResponse>
- [Программирование подключаемых протоколов](programming-pluggable-protocols.md)
- [Наследование от WebResponse](deriving-from-webrequest.md)
