---
title: Практическое руководство. Настройка веб-каналов с помощью поставщика отражения (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: 43f46729ba84356bcb6507779bef9e4fd35bc315
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790671"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="a5eb8-102">Практическое руководство. Настройка веб-каналов с помощью поставщика отражения (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="a5eb8-102">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>
<span data-ttu-id="a5eb8-103">Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют настроить сериализацию Atom в ответе службы данных так, чтобы свойства сущности сопоставлялись с неиспользуемыми элементами, определенными в протоколе AtomPub.</span><span class="sxs-lookup"><span data-stu-id="a5eb8-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="a5eb8-104">Этот раздел показывает, как настроить атрибуты сопоставления типов сущностей в модели данных, определенной с помощью поставщика отражения.</span><span class="sxs-lookup"><span data-stu-id="a5eb8-104">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="a5eb8-105">Дополнительные сведения см. в разделе [Настройка веб-канала](feed-customization-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a5eb8-105">For more information, see [Feed Customization](feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="a5eb8-106">Модель данных для этого примера определяется в разделе [как: Создание службы данных с помощью поставщика отражения](create-a-data-service-using-rp-wcf-data-services.md)</span><span class="sxs-lookup"><span data-stu-id="a5eb8-106">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5eb8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="a5eb8-107">Example</span></span>  
 <span data-ttu-id="a5eb8-108">В следующем примере оба свойства типа `Order` отображаются на существующие элементы Atom.</span><span class="sxs-lookup"><span data-stu-id="a5eb8-108">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="a5eb8-109">Свойство `Product` типа `Item` отображается на специализированный атрибут канала в отдельном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="a5eb8-109">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="a5eb8-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a5eb8-110">Example</span></span>  
 <span data-ttu-id="a5eb8-111">Предыдущий пример возвращает следующий результат для URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span><span class="sxs-lookup"><span data-stu-id="a5eb8-111">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="a5eb8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a5eb8-112">See also</span></span>

- [<span data-ttu-id="a5eb8-113">Поставщик отражений</span><span class="sxs-lookup"><span data-stu-id="a5eb8-113">Reflection Provider</span></span>](reflection-provider-wcf-data-services.md)
