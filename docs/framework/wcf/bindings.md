---
title: "Привязки Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF]
ms.assetid: 845df323-be53-4848-92ef-ba67a406484d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 36924bdc79a9789a991befb53c0025b7ea1fd601
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="6b252-102">Привязки Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="6b252-102">Windows Communication Foundation Bindings</span></span>
<span data-ttu-id="6b252-103">Привязки указывают способ взаимодействия конечных точек службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] с другими конечными точками.</span><span class="sxs-lookup"><span data-stu-id="6b252-103">Bindings specify how a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service endpoint communicates with other endpoints.</span></span> <span data-ttu-id="6b252-104">В привязке должен быть указан как минимум используемый транспорт (например, HTTP или TCP).</span><span class="sxs-lookup"><span data-stu-id="6b252-104">At its most basic, a binding must specify the transport (for example, HTTP or TCP) to use.</span></span> <span data-ttu-id="6b252-105">Через привязки также можно задать другие характеристики, такие как поддержка безопасности и транспорта.</span><span class="sxs-lookup"><span data-stu-id="6b252-105">You can also set other characteristics, such as security and transaction support, through bindings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6b252-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="6b252-106">In This Section</span></span>  
 [<span data-ttu-id="6b252-107">Общие сведения о привязках WCF</span><span class="sxs-lookup"><span data-stu-id="6b252-107">WCF Bindings Overview</span></span>](../../../docs/framework/wcf/bindings-overview.md)  
 <span data-ttu-id="6b252-108">Общие сведения о функциях привязок [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], список предоставляемых системой привязок и способы их определения и изменения.</span><span class="sxs-lookup"><span data-stu-id="6b252-108">Overview of what [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bindings do, what bindings the system provides, and how you can define or modify them.</span></span>  
  
 [<span data-ttu-id="6b252-109">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="6b252-109">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 <span data-ttu-id="6b252-110">Список привязок, включенных в [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b252-110">A list of bindings included with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="6b252-111">Эти привязки охватывают большую часть требований по безопасности и шаблонам сообщений.</span><span class="sxs-lookup"><span data-stu-id="6b252-111">These bindings cover the majority of security and message pattern requirements.</span></span>  
  
 [<span data-ttu-id="6b252-112">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6b252-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="6b252-113">Привязка [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] содержит важную информацию, которую клиенты должны использовать для подключения к конечным точкам службы.</span><span class="sxs-lookup"><span data-stu-id="6b252-113">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] binding contains important information that clients must use to connect to service endpoints.</span></span>  
  
 [<span data-ttu-id="6b252-114">Настройка привязок для служб</span><span class="sxs-lookup"><span data-stu-id="6b252-114">Configuring Bindings for Services</span></span>](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 <span data-ttu-id="6b252-115">С помощью конфигурации администраторы и установщики могут настраивать привязки для конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="6b252-115">Configuration enables administrators and installers to customize the bindings for service endpoints.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6b252-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="6b252-116">Reference</span></span>  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="6b252-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6b252-117">Related Sections</span></span>  
 [<span data-ttu-id="6b252-118">Конечные точки: Адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="6b252-118">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
  
 [<span data-ttu-id="6b252-119">Привязки</span><span class="sxs-lookup"><span data-stu-id="6b252-119">Bindings</span></span>](../../../docs/framework/wcf/feature-details/bindings.md)  
  
## <a name="see-also"></a><span data-ttu-id="6b252-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6b252-120">See Also</span></span>  
 [<span data-ttu-id="6b252-121">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="6b252-121">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
