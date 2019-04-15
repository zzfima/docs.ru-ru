---
ms.openlocfilehash: c9d6111edcfeec6852f23cc0768833de32e61022
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235554"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>Коды ошибок для maxRequestLength или maxReceivedMessageSize различаются

|   |   |
|---|---|
|Подробные сведения|Если длина сообщений в веб-службах WCF, размещенных в службах IIS или на сервере ASP.NET Development Server, превышает maxRequestLength (в ASP.NET) или maxReceivedMessageSize (в WCF), им присваиваются разные коды ошибок. Код состояния HTTP изменился с 400 (неверный запрос) на 413 (слишком большая сущность запроса), а для сообщений, длина которых превышает maxRequestLength или maxReceivedMessageSize, теперь создается исключение <xref:System.ServiceModel.ProtocolException?displayProperty=name>. Сюда входят случаи, в которых режимом передачи является Streamed.|
|Предложение|Это изменение облегчает отладку в тех случаях, когда длина сообщения превышает ограничения, установленные ASP.NET или WCF. Необходимо внести изменения во весь код, который выполняет обработку на основании кода состояния HTTP 400.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
