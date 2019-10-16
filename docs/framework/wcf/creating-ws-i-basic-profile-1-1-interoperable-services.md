---
title: Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: eb1cd12c45a276d5c3cb14f89205fff618121abc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320129"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="6acdf-102">Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1</span><span class="sxs-lookup"><span data-stu-id="6acdf-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="6acdf-103">Чтобы настроить конечную точку службы WCF для взаимодействия с клиентами веб-службы ASP.NET, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6acdf-103">To configure a WCF service endpoint to be interoperable with ASP.NET Web service clients:</span></span>  
  
- <span data-ttu-id="6acdf-104">использовать в качестве типа привязки для конечной точки службы тип <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>;</span><span class="sxs-lookup"><span data-stu-id="6acdf-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
- <span data-ttu-id="6acdf-105">не использовать функции обратного вызова и сеансового контракта и не управлять поведением транзакций на конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="6acdf-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="6acdf-106">В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="6acdf-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="6acdf-107">Следующие функции класса <xref:System.ServiceModel.BasicHttpBinding> требуют функциональность, выходящую за рамки спецификации WS-I Basic Profile, версия 1.1.</span><span class="sxs-lookup"><span data-stu-id="6acdf-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
- <span data-ttu-id="6acdf-108">Кодирование сообщения подсистемы оптимизации передачи сообщений MTOM управляется свойством <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6acdf-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6acdf-109">Не изменяйте значение этого свойства по умолчанию - <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> (не использовать MTOM).</span><span class="sxs-lookup"><span data-stu-id="6acdf-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
- <span data-ttu-id="6acdf-110">Безопасность сообщения управляется значением <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> и обеспечивает поддержку WS-Security, совместимую с основным профилем безопасности WS-I версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="6acdf-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="6acdf-111">Не изменяйте значение этого свойства по умолчанию - <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> (не использовать WS-Security).</span><span class="sxs-lookup"><span data-stu-id="6acdf-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="6acdf-112">Чтобы сделать метаданные для службы WCF доступными для ASP.NET, используйте средства создания клиентов веб-службы: [средство языка описания веб-служб (WSDL. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [средство обнаружения веб-служб (Disco. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29)и компонент `Add Web Reference` в Visual Studio. необходимо включить публикацию метаданных.</span><span class="sxs-lookup"><span data-stu-id="6acdf-112">To make the metadata for a WCF service available to ASP.NET, use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [Web Services Discovery Tool (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29), and the `Add Web Reference` feature in Visual Studio; you must enable metadata publication.</span></span> <span data-ttu-id="6acdf-113">Дополнительные сведения см. в разделе [Публикация конечных точек метаданных](publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="6acdf-113">For more information, see [Publishing Metadata Endpoints](publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6acdf-114">Пример</span><span class="sxs-lookup"><span data-stu-id="6acdf-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6acdf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6acdf-115">Description</span></span>  
 <span data-ttu-id="6acdf-116">В следующем примере кода показано, как добавить конечную точку WCF, совместимую с клиентами веб-службы ASP.NET, в коде и, Кроме того, в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6acdf-116">The following example code demonstrates how to add a WCF endpoint that is compatible with ASP.NET Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6acdf-117">Код</span><span class="sxs-lookup"><span data-stu-id="6acdf-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6acdf-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6acdf-118">See also</span></span>

- [<span data-ttu-id="6acdf-119">Взаимодействие с веб-службами ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6acdf-119">Interoperability with ASP.NET Web Services</span></span>](./feature-details/interop-with-aspnet-web-services.md)
