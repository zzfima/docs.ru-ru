---
title: Синдикация WCF
ms.date: 03/30/2017
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
ms.openlocfilehash: c7fefb49cf70b9f3c55937e7be06eca212af364d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530909"
---
# <a name="wcf-syndication"></a><span data-ttu-id="11a3f-102">Синдикация WCF</span><span class="sxs-lookup"><span data-stu-id="11a3f-102">WCF Syndication</span></span>
<span data-ttu-id="11a3f-103">Windows Communication Foundation (WCF) обеспечивает поддержку для удобной работы с каналами Atom, RSS и других нестандартных форматах, что позволяет считывать и создавать их, а также предоставлять к ним доступ в конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="11a3f-103">Windows Communication Foundation (WCF) provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="11a3f-104">В подразделах этого раздела подробно описывается модель программирования синдикации.</span><span class="sxs-lookup"><span data-stu-id="11a3f-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11a3f-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="11a3f-105">In This Section</span></span>  
 [<span data-ttu-id="11a3f-106">Общие сведения о синдикации WCF</span><span class="sxs-lookup"><span data-stu-id="11a3f-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="11a3f-107">Предоставляет общие сведения о поддержке синдикации в WCF.</span><span class="sxs-lookup"><span data-stu-id="11a3f-107">Provides an overview of syndication support provided by WCF.</span></span>  
  
 [<span data-ttu-id="11a3f-108">Архитектура синдикации</span><span class="sxs-lookup"><span data-stu-id="11a3f-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="11a3f-109">Описание классов объектной модели и расширяемости синдикации.</span><span class="sxs-lookup"><span data-stu-id="11a3f-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="11a3f-110">Сопоставление объектной модели синдикации WCF моделям Atom и RSS</span><span class="sxs-lookup"><span data-stu-id="11a3f-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="11a3f-111">Представление веб-каналов в объектной модели синдикации WCF и их преобразование в веб-каналы RSS и Atom.</span><span class="sxs-lookup"><span data-stu-id="11a3f-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="11a3f-112">Практическое руководство. Создание базового RSS-канала</span><span class="sxs-lookup"><span data-stu-id="11a3f-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="11a3f-113">Создание службы, которая предоставляет доступ к базовому RSS-каналу.</span><span class="sxs-lookup"><span data-stu-id="11a3f-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="11a3f-114">Практическое руководство. Создание базового канала Atom</span><span class="sxs-lookup"><span data-stu-id="11a3f-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="11a3f-115">Создание службы, которая предоставляет доступ к базовому ATOM-каналу.</span><span class="sxs-lookup"><span data-stu-id="11a3f-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="11a3f-116">Практическое руководство. Публикация канала в форматах Atom и RSS</span><span class="sxs-lookup"><span data-stu-id="11a3f-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="11a3f-117">Создание службы, которая предоставляет доступ к одному и тому же каналу в форматах ATOM и RSS.</span><span class="sxs-lookup"><span data-stu-id="11a3f-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="11a3f-118">Расширяемость синдикации</span><span class="sxs-lookup"><span data-stu-id="11a3f-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="11a3f-119">Описание методов добавления в канал синдикации пользовательских элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="11a3f-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="11a3f-120">Ссылка</span><span class="sxs-lookup"><span data-stu-id="11a3f-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="11a3f-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="11a3f-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a3f-122">См. также</span><span class="sxs-lookup"><span data-stu-id="11a3f-122">See also</span></span>
- [<span data-ttu-id="11a3f-123">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="11a3f-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="11a3f-124">Частичное доверие</span><span class="sxs-lookup"><span data-stu-id="11a3f-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
