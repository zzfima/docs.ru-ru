---
title: Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fd08dca74ddb3f77e37a3aa4d67cf6d495bf5d16
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="f7141-102">Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1</span><span class="sxs-lookup"><span data-stu-id="f7141-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="f7141-103">Для настройки конечной точки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] таким образом, чтобы она могла взаимодействовать с клиентами веб-службы [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], необходимо:</span><span class="sxs-lookup"><span data-stu-id="f7141-103">To configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients:</span></span>  
  
-   <span data-ttu-id="f7141-104">использовать в качестве типа привязки для конечной точки службы тип <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>;</span><span class="sxs-lookup"><span data-stu-id="f7141-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
-   <span data-ttu-id="f7141-105">не использовать возможности обратного вызова и сеансового контракта и не управлять поведением транзакций на конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="f7141-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="f7141-106">В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="f7141-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="f7141-107">Следующие функции класса <xref:System.ServiceModel.BasicHttpBinding> требуют функциональность, выходящую за рамки спецификации WS-I Basic Profile, версия 1.1.</span><span class="sxs-lookup"><span data-stu-id="f7141-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
-   <span data-ttu-id="f7141-108">Кодирование сообщения подсистемы оптимизации передачи сообщений MTOM управляется свойством <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f7141-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f7141-109">Не изменяйте значение этого свойства по умолчанию - <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> (не использовать MTOM).</span><span class="sxs-lookup"><span data-stu-id="f7141-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
-   <span data-ttu-id="f7141-110">Безопасность сообщения управляется значением <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> и обеспечивает поддержку WS-Security, совместимую с основным профилем безопасности WS-I версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="f7141-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="f7141-111">Не изменяйте значение этого свойства по умолчанию - <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> (не использовать WS-Security).</span><span class="sxs-lookup"><span data-stu-id="f7141-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="f7141-112">Чтобы сделать метаданные для [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] службу, доступную [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], используйте инструменты создания клиента службы Web: [инструмент языка описания веб-служб (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [(средство обнаружения веб-служб DISCO.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979)и `Add Web Reference` компонент в Visual Studio; необходимо включить публикацию метаданных.</span><span class="sxs-lookup"><span data-stu-id="f7141-112">To make the metadata for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service available to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](http://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88), [Web Services Discovery Tool (Disco.exe)](http://msdn.microsoft.com/library/acd88078-c581-42bc-94ca-6633e2851979), and the `Add Web Reference` feature in Visual Studio; you must enable metadata publication.</span></span> <span data-ttu-id="f7141-113">Дополнительные сведения см. в разделе [публикация конечных точек метаданных](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="f7141-113">For more information, see [Publishing Metadata Endpoints](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7141-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f7141-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f7141-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f7141-115">Description</span></span>  
 <span data-ttu-id="f7141-116">В следующем примере кода показано, как добавить [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] конечную точку, совместимую с [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] клиентами веб-службы в коде и, кроме того, в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f7141-116">The following example code demonstrates how to add a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] endpoint that is compatible with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f7141-117">Код</span><span class="sxs-lookup"><span data-stu-id="f7141-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f7141-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f7141-118">See Also</span></span>  
 [<span data-ttu-id="f7141-119">Взаимодействие с веб-службами ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f7141-119">Interoperability with ASP.NET Web Services</span></span>](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
