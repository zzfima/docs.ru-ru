---
title: Сравнение веб-служб ASP.NET с веб-службами на основе WCF по назначению и используемым стандартам
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 9ceb28fece3cc17aa4ac2329dc101eac8e89bd77
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576883"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Сравнение веб-служб ASP.NET с веб-службами на основе WCF по назначению и используемым стандартам
Веб-службы ASP.NET были разработаны для создания приложений, которые отправляют и получают сообщения с использованием протокола SOAP (Simple Object Access Protocol) через HTTP. Структуру сообщений можно определить с помощью схемы XML, а для сериализации сообщений в объекты .NET Framework и обратно предусмотрено специальное средство. Эта технология позволяет автоматически создавать метаданные для описания веб-служб на языке WSDL (языке описания веб-служб), а второе средство предоставляется для создания клиентов для веб-служб из WSDL.  
  
 WCF — для включения приложений .NET Framework для обмена сообщениями с другими программными сущностями. По умолчанию используется протокол SOAP, но сообщения могут иметь любой формат и передаваться с использованием любого транспортного протокола. Структуру сообщений можно определить с помощью схемы XML, а для сериализации сообщений в объекты .NET Framework и обратно имеется несколько параметров. WCF может автоматически создавать метаданные для описания приложений, созданных с использованием технологии в WSDL, а также предоставляет средство для создания клиентов для этих приложений из WSDL.  
  
 Стандартов, поддерживаемых веб-службами ASP.NET, описаны в [XML Web Services, созданные с помощью ASP.NET](https://go.microsoft.com/fwlink/?LinkId=94872). Более полный список стандартов, поддерживаемых WCF, перечислены в [Web Services протоколов, поддерживаемых System-Provided Bindings взаимодействие](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>См. также  
 [Сравнение веб-служб ASP.NET с веб-службами на основе WCF по процессу разработки](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
