---
title: "Сравнение веб-служб ASP.NET с веб-службами на основе WCF по назначению и используемым стандартам"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b43fe9cf66fc9ccf72d12c6a617a1b4c0b44def
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a><span data-ttu-id="5fd5a-102">Сравнение веб-служб ASP.NET с веб-службами на основе WCF по назначению и используемым стандартам</span><span class="sxs-lookup"><span data-stu-id="5fd5a-102">Comparing ASP.NET Web Services to WCF Based on Purpose and Standards Used</span></span>
<span data-ttu-id="5fd5a-103">Веб-службы ASP.NET были разработаны для создания приложений, которые отправляют и получают сообщения с использованием протокола SOAP (Simple Object Access Protocol) через HTTP.</span><span class="sxs-lookup"><span data-stu-id="5fd5a-103">ASP.NET Web services was developed for building applications that send and receive messages by using the Simple Object Access Protocol (SOAP) over HTTP.</span></span> <span data-ttu-id="5fd5a-104">Структуру сообщений можно определить с помощью схемы XML, а для сериализации сообщений в объекты .NET Framework и обратно предусмотрено специальное средство.</span><span class="sxs-lookup"><span data-stu-id="5fd5a-104">The structure of the messages can be defined using an XML Schema, and a tool is provided to facilitate serializing the messages to and from .NET Framework objects.</span></span> <span data-ttu-id="5fd5a-105">Эта технология позволяет автоматически создавать метаданные для описания веб-служб на языке WSDL (языке описания веб-служб), а второе средство предоставляется для создания клиентов для веб-служб из WSDL.</span><span class="sxs-lookup"><span data-stu-id="5fd5a-105">The technology can automatically generate metadata to describe Web services in the Web Services Description Language (WSDL), and a second tool is provided for generating clients for Web services from the WSDL.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5fd5a-106"> позволяет приложениям .NET Framework обмениваться сообщениями с другими программными сущностями.</span><span class="sxs-lookup"><span data-stu-id="5fd5a-106"> is for enabling .NET Framework applications to exchange messages with other software entities.</span></span> <span data-ttu-id="5fd5a-107">По умолчанию используется протокол SOAP, но сообщения могут иметь любой формат и передаваться с использованием любого транспортного протокола.</span><span class="sxs-lookup"><span data-stu-id="5fd5a-107">SOAP is used by default, but the messages can be in any format, and conveyed by using any transport protocol.</span></span> <span data-ttu-id="5fd5a-108">Структуру сообщений можно определить с помощью схемы XML, а для сериализации сообщений в объекты .NET Framework и обратно имеется несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="5fd5a-108">The structure of the messages can be defined using an XML Schema, and there are various options for serializing the messages to and from .NET Framework objects.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="5fd5a-109"> может автоматически создавать метаданные для описания приложений, созданных с использованием этой технологии в WSDL, а также предоставляет средство для создания клиентов для этих приложений из WSDL.</span><span class="sxs-lookup"><span data-stu-id="5fd5a-109"> can automatically generate metadata to describe applications built using the technology in WSDL, and it also provides a tool for generating clients for those applications from the WSDL.</span></span>  
  
 <span data-ttu-id="5fd5a-110">Описание стандартов, поддерживаемых веб-службами ASP.NET, описаны в [XML Web Services созданные с помощью ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872).</span><span class="sxs-lookup"><span data-stu-id="5fd5a-110">The standards supported by ASP.NET Web services are documented in [XML Web Services Created Using ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872).</span></span> <span data-ttu-id="5fd5a-111">Более подробный список поддерживаемых стандартов [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] перечислены в [протоколы веб-служб поддерживаемые привязками привязка, предоставляемая](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="5fd5a-111">The more extensive list of standards supported by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] are listed at [Web Services Protocols Supported by System-Provided Interoperability Bindings](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd5a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="5fd5a-112">See Also</span></span>  
 [<span data-ttu-id="5fd5a-113">Сравнение веб-служб ASP.NET с веб-службами на основе WCF по процессу разработки</span><span class="sxs-lookup"><span data-stu-id="5fd5a-113">Comparing ASP.NET Web Services to WCF Based on Development</span></span>](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
