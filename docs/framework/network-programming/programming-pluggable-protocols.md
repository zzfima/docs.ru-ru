---
title: программирование подключаемых протоколов
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, pluggable protocols
- WebRequest class, pluggable protocols
- response to Internet request, pluggable protocols
- WebResponse class, pluggable protocols
- sending data, pluggable protocols
- network resources, pluggable protocols
- Internet, pluggable protocols
- programming pluggable protocols
- pluggable protocols, programming
- requesting data from Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 66ef8456-7576-4e97-8956-959b216373db
ms.openlocfilehash: 94dfedd317782b9e518df02c84d9af55b1ef2b69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047392"
---
# <a name="programming-pluggable-protocols"></a><span data-ttu-id="cc18b-102">программирование подключаемых протоколов</span><span class="sxs-lookup"><span data-stu-id="cc18b-102">Programming Pluggable Protocols</span></span>
<span data-ttu-id="cc18b-103">Абстрактные классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> реализуют основу для подключаемых протоколов.</span><span class="sxs-lookup"><span data-stu-id="cc18b-103">The abstract <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide the base for pluggable protocols.</span></span> <span data-ttu-id="cc18b-104">Создавая производные классы для определенных протоколов на основе классов <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, приложение может запрашивать данные интернет-ресурса и считывать ответ, не указывая используемый протокол.</span><span class="sxs-lookup"><span data-stu-id="cc18b-104">By deriving protocol-specific classes from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>, an application can request data from an Internet resource and read the response without specifying the protocol being used.</span></span>  
  
 <span data-ttu-id="cc18b-105">Прежде чем создавать класс <xref:System.Net.WebRequest> для определенного протокола, необходимо зарегистрировать его метод Create.</span><span class="sxs-lookup"><span data-stu-id="cc18b-105">Before you can create a protocol-specific <xref:System.Net.WebRequest>, you must register its Create method.</span></span> <span data-ttu-id="cc18b-106">Используйте статический метод <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> класса <xref:System.Net.WebRequest> для регистрации потомка <xref:System.Net.WebRequest>, который будет обрабатывать набор запросов к конкретной интернет-схеме, к схеме и серверу либо к схеме, серверу и пути.</span><span class="sxs-lookup"><span data-stu-id="cc18b-106">Use the static <xref:System.Net.WebRequest.RegisterPrefix%28System.String%2CSystem.Net.IWebRequestCreate%29> method of <xref:System.Net.WebRequest> to register a <xref:System.Net.WebRequest> descendant to handle a set of requests to a particular Internet scheme, to a scheme and server, or to a scheme, server, and path.</span></span>  
  
 <span data-ttu-id="cc18b-107">В большинстве случаев можно отправлять и получать данные с помощью методов и свойств класса <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="cc18b-107">In most cases you will be able to send and receive data using the methods and properties of the <xref:System.Net.WebRequest> class.</span></span> <span data-ttu-id="cc18b-108">Однако если нужно получить доступ к свойствам определенного протокола, можно выполнить приведение типа <xref:System.Net.WebRequest> к конкретному экземпляру производного класса.</span><span class="sxs-lookup"><span data-stu-id="cc18b-108">However, if you need to access protocol-specific properties, you can typecast a <xref:System.Net.WebRequest> to a specific derived-class instance.</span></span>  
  
 <span data-ttu-id="cc18b-109">Чтобы использовать преимущества подключаемых протоколов, потомки класса <xref:System.Net.WebRequest> должны предоставлять применяемую по умолчанию операцию "запрос-ответ", для которой не требуется задавать свойства определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="cc18b-109">To take advantage of pluggable protocols, your <xref:System.Net.WebRequest> descendants must provide a default request-and-response transaction that does not require protocol-specific properties to be set.</span></span> <span data-ttu-id="cc18b-110">Например, класс <xref:System.Net.HttpWebRequest>, который реализует класс <xref:System.Net.WebRequest> для HTTP, предоставляет запрос `GET` по умолчанию и возвращает <xref:System.Net.HttpWebResponse>, который содержит поток, возвращенный веб-сервером.</span><span class="sxs-lookup"><span data-stu-id="cc18b-110">For example, the <xref:System.Net.HttpWebRequest> class, which implements the <xref:System.Net.WebRequest> class for HTTP, provides a `GET` request by default and returns an <xref:System.Net.HttpWebResponse> that contains the stream returned from the Web server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc18b-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc18b-111">See also</span></span>

- [<span data-ttu-id="cc18b-112">Наследование от WebResponse</span><span class="sxs-lookup"><span data-stu-id="cc18b-112">Deriving from WebRequest</span></span>](deriving-from-webrequest.md)
- [<span data-ttu-id="cc18b-113">Наследование от класса WebResponse</span><span class="sxs-lookup"><span data-stu-id="cc18b-113">Deriving from WebResponse</span></span>](deriving-from-webresponse.md)
- [<span data-ttu-id="cc18b-114">Сетевое программирование в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cc18b-114">Network Programming in the .NET Framework</span></span>](index.md)
- [<span data-ttu-id="cc18b-115">Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом</span><span class="sxs-lookup"><span data-stu-id="cc18b-115">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>](how-to-typecast-a-webrequest-to-access-protocol-specific-properties.md)
