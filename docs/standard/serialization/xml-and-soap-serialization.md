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
# <a name="xml-and-soap-serialization"></a>Сериализация XML и SOAP

XML сериализация преобразует (сериализирует) публичные поля и свойства объекта, а также параметры и значения возврата методов в поток XML, который соответствует определенному языку определения XML Schema (XSD). XML-сериализация приводит к образованию строго типизированных классов с открытыми свойствами и полями, которые преобразуются в серийный формат (в данном случае - XML) для хранения и передачи.

Поскольку стандарт XML является открытым, поток XML может обработать любое необходимое приложение независимо от платформы. Например, XML-веб-службы, созданные с помощью ASP.NET, используют класс <xref:System.Xml.Serialization.XmlSerializer>, чтобы создавать потоки XML, которые передают данные между приложениями веб-службы XML через Интернет или интрасети. И наоборот, при десериализации используется такой поток и воссоздается объект.

XML-сериализация может также использоваться для сериализации объектов в потоки XML, которые соответствуют спецификации SOAP. SOAP - это протокол, основанный на XML и созданный специально для передачи вызовов процедур с использованием XML.

Чтобы сериализовать и десериализовать объекты, используйте класс <xref:System.Xml.Serialization.XmlSerializer>. Чтобы создать классы для их последующей сериализации, используйте инструмент определения схемы XML.

## <a name="see-also"></a>См. также

- [Двоичная сериализация](binary-serialization.md)
- [XML Web Services, созданные с использованием клиентов ASP.NET и XML Web Service](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
