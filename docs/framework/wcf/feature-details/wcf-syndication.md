---
title: Синдикация WCF
ms.date: 03/30/2017
helpviewer_keywords:
- syndication [WCF]
ms.assetid: ebf80384-0fc9-4919-a1e8-23ca2a13e300
ms.openlocfilehash: 627de6431c641e48367a97e3f80f3d05d185ab45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499171"
---
# <a name="wcf-syndication"></a><span data-ttu-id="d946a-102">Синдикация WCF</span><span class="sxs-lookup"><span data-stu-id="d946a-102">WCF Syndication</span></span>
<span data-ttu-id="d946a-103">Windows Communication Foundation (WCF) обеспечивает поддержку для удобной работы с веб-каналами синдикации в форматах Atom, RSS и других нестандартных форматах, что позволяет обрабатывать и создавать их, а также предоставлять к ним доступ в конечной точке службы.</span><span class="sxs-lookup"><span data-stu-id="d946a-103">Windows Communication Foundation (WCF) provides support to easily work with syndication feeds in Atom, RSS or other custom formats, which allows you to read and create them as well as expose them on a service endpoint.</span></span> <span data-ttu-id="d946a-104">В подразделах этого раздела подробно описывается модель программирования синдикации.</span><span class="sxs-lookup"><span data-stu-id="d946a-104">The topics in this section describe this programming model for syndication in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d946a-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="d946a-105">In This Section</span></span>  
 [<span data-ttu-id="d946a-106">Общие сведения о синдикации WCF</span><span class="sxs-lookup"><span data-stu-id="d946a-106">WCF Syndication Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-syndication-overview.md)  
 <span data-ttu-id="d946a-107">Общие сведения о поддержке синдикации WCF.</span><span class="sxs-lookup"><span data-stu-id="d946a-107">Provides an overview of syndication support provided by WCF.</span></span>  
  
 [<span data-ttu-id="d946a-108">Архитектура синдикации</span><span class="sxs-lookup"><span data-stu-id="d946a-108">Architecture of Syndication</span></span>](../../../../docs/framework/wcf/feature-details/architecture-of-syndication.md)  
 <span data-ttu-id="d946a-109">Описание классов объектной модели и расширяемости синдикации.</span><span class="sxs-lookup"><span data-stu-id="d946a-109">Describes the classes in the object model and the extensibility of syndication.</span></span>  
  
 [<span data-ttu-id="d946a-110">Сопоставление объектной модели синдикации WCF моделям Atom и RSS</span><span class="sxs-lookup"><span data-stu-id="d946a-110">How the WCF Syndication Object Model Maps to Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md)  
 <span data-ttu-id="d946a-111">Представление веб-каналов в объектной модели синдикации WCF и их преобразование в веб-каналы RSS и Atom.</span><span class="sxs-lookup"><span data-stu-id="d946a-111">Describes how feeds are represented within the WCF Syndication Object Model and how they are converted to RSS and Atom feeds.</span></span>  
  
 [<span data-ttu-id="d946a-112">Практическое руководство. Создание базового RSS-канала</span><span class="sxs-lookup"><span data-stu-id="d946a-112">How to: Create a Basic RSS Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-rss-feed.md)  
 <span data-ttu-id="d946a-113">Создание службы, которая предоставляет доступ к базовому RSS-каналу.</span><span class="sxs-lookup"><span data-stu-id="d946a-113">Shows how to create a service that makes a basic RSS feed available.</span></span>  
  
 [<span data-ttu-id="d946a-114">Практическое руководство. Создание базового канала Atom</span><span class="sxs-lookup"><span data-stu-id="d946a-114">How to: Create a Basic Atom Feed</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-atom-feed.md)  
 <span data-ttu-id="d946a-115">Создание службы, которая предоставляет доступ к базовому ATOM-каналу.</span><span class="sxs-lookup"><span data-stu-id="d946a-115">Shows how to create a service that makes a basic ATOM feed available.</span></span>  
  
 [<span data-ttu-id="d946a-116">Практическое руководство. Публикация канала в форматах Atom и RSS</span><span class="sxs-lookup"><span data-stu-id="d946a-116">How to: Expose a Feed as Both Atom and RSS</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-feed-as-both-atom-and-rss.md)  
 <span data-ttu-id="d946a-117">Создание службы, которая предоставляет доступ к одному и тому же каналу в форматах ATOM и RSS.</span><span class="sxs-lookup"><span data-stu-id="d946a-117">Shows how to create a service that makes the same feed available with ATOM and RSS.</span></span>  
  
 [<span data-ttu-id="d946a-118">Расширяемость синдикации</span><span class="sxs-lookup"><span data-stu-id="d946a-118">Syndication Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/syndication-extensibility.md)  
 <span data-ttu-id="d946a-119">Описание методов добавления в канал синдикации пользовательских элементов и атрибутов.</span><span class="sxs-lookup"><span data-stu-id="d946a-119">Describes the methods of adding custom elements and attributes to a syndication feed.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d946a-120">Ссылка</span><span class="sxs-lookup"><span data-stu-id="d946a-120">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d946a-121">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d946a-121">Related Sections</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d946a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d946a-122">See Also</span></span>  
 [<span data-ttu-id="d946a-123">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="d946a-123">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [<span data-ttu-id="d946a-124">Частичное доверие</span><span class="sxs-lookup"><span data-stu-id="d946a-124">Partial Trust</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust.md)
