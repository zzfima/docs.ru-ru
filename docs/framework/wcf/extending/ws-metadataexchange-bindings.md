---
title: Привязки WS-MetadataExchange
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 03e6e6d5ee7e69b397acd0f51b8037f02c1804ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795480"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="fec16-102">Привязки WS-MetadataExchange</span><span class="sxs-lookup"><span data-stu-id="fec16-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="fec16-103">В этом разделе описано, как создавать привязки обмена метаданными по умолчанию для различных транспортов.</span><span class="sxs-lookup"><span data-stu-id="fec16-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="fec16-104">Привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fec16-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="fec16-105">Имя привязки по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fec16-105">Default Binding Name</span></span>|<span data-ttu-id="fec16-106">Создание привязки</span><span class="sxs-lookup"><span data-stu-id="fec16-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="fec16-107">mexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="fec16-107">mexHttpBinding</span></span>|<span data-ttu-id="fec16-108">Привязка <xref:System.ServiceModel.WSHttpBinding> с отключенной безопасностью транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="fec16-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="fec16-109">mexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="fec16-109">mexHttpsBinding</span></span>|<span data-ttu-id="fec16-110">Привязка <xref:System.ServiceModel.WSHttpBinding> с поддержкой безопасности транспортного уровня.</span><span class="sxs-lookup"><span data-stu-id="fec16-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="fec16-111">mexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="fec16-111">mexNamedPipeBinding</span></span>|<span data-ttu-id="fec16-112">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fec16-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="fec16-113">mexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="fec16-113">mexTcpBinding</span></span>|<span data-ttu-id="fec16-114">Привязка <xref:System.ServiceModel.Channels.CustomBinding> с элементом <xref:System.ServiceModel.Channels.TcpTransportBindingElement> и значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fec16-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
