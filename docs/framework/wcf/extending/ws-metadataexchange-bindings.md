---
title: "Привязки WS-MetadataExchange"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8d305f3bf34b3b14da566fa792552e24e695ef33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="8ded6-102">Привязки WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="8ded6-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="8ded6-103">В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.</span><span class="sxs-lookup"><span data-stu-id="8ded6-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="8ded6-104">Привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8ded6-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="8ded6-105">Имя привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8ded6-105">Default Binding Name</span></span>|<span data-ttu-id="8ded6-106">Создание привязки</span><span class="sxs-lookup"><span data-stu-id="8ded6-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="8ded6-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="8ded6-107">MexHttpBinding</span></span>|<span data-ttu-id="8ded6-108">Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="8ded6-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="8ded6-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="8ded6-109">MexHttpsBinding</span></span>|<span data-ttu-id="8ded6-110">Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="8ded6-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="8ded6-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="8ded6-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="8ded6-112">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8ded6-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="8ded6-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="8ded6-113">MexTcpBinding</span></span>|<span data-ttu-id="8ded6-114">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8ded6-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
