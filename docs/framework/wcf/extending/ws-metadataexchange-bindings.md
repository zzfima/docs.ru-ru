---
title: Привязки WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488628"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="33b3c-102">Привязки WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="33b3c-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="33b3c-103">В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.</span><span class="sxs-lookup"><span data-stu-id="33b3c-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="33b3c-104">Привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="33b3c-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="33b3c-105">Имя привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="33b3c-105">Default Binding Name</span></span>|<span data-ttu-id="33b3c-106">Создание привязки</span><span class="sxs-lookup"><span data-stu-id="33b3c-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="33b3c-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="33b3c-107">MexHttpBinding</span></span>|<span data-ttu-id="33b3c-108">Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="33b3c-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="33b3c-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="33b3c-109">MexHttpsBinding</span></span>|<span data-ttu-id="33b3c-110">Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="33b3c-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="33b3c-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="33b3c-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="33b3c-112">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33b3c-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="33b3c-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="33b3c-113">MexTcpBinding</span></span>|<span data-ttu-id="33b3c-114">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="33b3c-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
