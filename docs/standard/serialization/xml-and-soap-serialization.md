---
title: Сериализация XML и SOAP
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: dcb2ed1703473be582a12f430d2e051d8a420230
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588376"
---
# <a name="xml-and-soap-serialization"></a><span data-ttu-id="2453c-102">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="2453c-102">XML and SOAP serialization</span></span>

<span data-ttu-id="2453c-103">XML сериализация преобразует (сериализирует) публичные поля и свойства объекта, а также параметры и значения возврата методов в поток XML, который соответствует определенному языку определения XML Schema (XSD).</span><span class="sxs-lookup"><span data-stu-id="2453c-103">XML serialization converts (serializes) the public fields and properties of an object, and the parameters and return values of methods, into an XML stream that conforms to a specific XML Schema definition language (XSD) document.</span></span> <span data-ttu-id="2453c-104">XML-сериализация приводит к образованию строго типизированных классов с открытыми свойствами и полями, которые преобразуются в серийный формат (в данном случае - XML) для хранения и передачи.</span><span class="sxs-lookup"><span data-stu-id="2453c-104">XML serialization results in strongly typed classes with public properties and fields that are converted to a serial format (in this case, XML) for storage or transport.</span></span>

<span data-ttu-id="2453c-105">Поскольку стандарт XML является открытым, поток XML может обработать любое необходимое приложение независимо от платформы.</span><span class="sxs-lookup"><span data-stu-id="2453c-105">Because XML is an open standard, the XML stream can be processed by any application, as needed, regardless of platform.</span></span> <span data-ttu-id="2453c-106">Например, XML-веб-службы, созданные с помощью ASP.NET, используют класс <xref:System.Xml.Serialization.XmlSerializer>, чтобы создавать потоки XML, которые передают данные между приложениями веб-службы XML через Интернет или интрасети.</span><span class="sxs-lookup"><span data-stu-id="2453c-106">For example, XML Web services created using ASP.NET use the <xref:System.Xml.Serialization.XmlSerializer> class to create XML streams that pass data between XML Web service applications throughout the Internet or on intranets.</span></span> <span data-ttu-id="2453c-107">И наоборот, при десериализации используется такой поток и воссоздается объект.</span><span class="sxs-lookup"><span data-stu-id="2453c-107">Conversely, deserialization takes such an XML stream and reconstructs the object.</span></span>

<span data-ttu-id="2453c-108">XML-сериализация может также использоваться для сериализации объектов в потоки XML, которые соответствуют спецификации SOAP.</span><span class="sxs-lookup"><span data-stu-id="2453c-108">XML serialization can also be used to serialize objects into XML streams that conform to the SOAP specification.</span></span> <span data-ttu-id="2453c-109">SOAP - это протокол, основанный на XML и созданный специально для передачи вызовов процедур с использованием XML.</span><span class="sxs-lookup"><span data-stu-id="2453c-109">SOAP is a protocol based on XML, designed specifically to transport procedure calls using XML.</span></span>

<span data-ttu-id="2453c-110">Чтобы сериализовать и десериализовать объекты, используйте класс <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="2453c-110">To serialize or deserialize objects, use the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span> <span data-ttu-id="2453c-111">Чтобы создать классы для их последующей сериализации, используйте инструмент определения схемы XML.</span><span class="sxs-lookup"><span data-stu-id="2453c-111">To create the classes to be serialized, use the XML Schema Definition tool.</span></span>

## <a name="see-also"></a><span data-ttu-id="2453c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2453c-112">See also</span></span>

- [<span data-ttu-id="2453c-113">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="2453c-113">Binary Serialization</span></span>](binary-serialization.md)
- <span data-ttu-id="2453c-114">[XML Web Services, созданные с использованием клиентов ASP.NET и XML Web Service](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2453c-114">[XML Web Services created using ASP.NET and XML Web Service clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>
