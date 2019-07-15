---
ms.openlocfilehash: 8d058d3297471e67459164f18358b1d143465712
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803238"
---
### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a>ASP.NET MVC теперь экранирует пробелы в строках, переданных через параметры маршрута

|   |   |
|---|---|
|Подробные сведения|Чтобы соответствовать стандарту RFC 2396, пробелы в путях маршрута теперь экранируются при заполнении параметров действий из маршрута. Таким образом, в то время как <code>/controller/action/some data</code> ранее соответствовал маршруту <code>/controller/action/{data}</code> и предоставлял <code>some data</code> в качестве параметра данных, теперь он будет предоставлять <code>some%20data</code>.|
|Предложение|Код должен быть обновлен для неэкранирования строковых параметров из маршрута. Если необходим исходный URI, доступ к нему можно получить с помощью API <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString.|
|Область|Дополнительный номер|
|Версия|4.5.2|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|

