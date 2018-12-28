---
title: Привязки WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2018
ms.locfileid: "53767352"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="0b484-102">Привязки WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="0b484-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="0b484-103">В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.</span><span class="sxs-lookup"><span data-stu-id="0b484-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="0b484-104">Привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0b484-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="0b484-105">Имя привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0b484-105">Default Binding Name</span></span>|<span data-ttu-id="0b484-106">Создание привязки</span><span class="sxs-lookup"><span data-stu-id="0b484-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="0b484-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="0b484-107">mexHttpBinding</span></span>|<span data-ttu-id="0b484-108">Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="0b484-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="0b484-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="0b484-109">mexHttpsBinding</span></span>|<span data-ttu-id="0b484-110">Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="0b484-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="0b484-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="0b484-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="0b484-112">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b484-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="0b484-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="0b484-113">mexTcpBinding</span></span>|<span data-ttu-id="0b484-114">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0b484-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
