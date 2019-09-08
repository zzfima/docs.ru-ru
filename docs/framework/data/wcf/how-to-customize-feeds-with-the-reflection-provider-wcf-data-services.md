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
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>Практическое руководство. Настройка веб-каналов с помощью поставщика отражения (WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют настроить сериализацию Atom в ответе службы данных так, чтобы свойства сущности сопоставлялись с неиспользуемыми элементами, определенными в протоколе AtomPub. Этот раздел показывает, как настроить атрибуты сопоставления типов сущностей в модели данных, определенной с помощью поставщика отражения. Дополнительные сведения см. в разделе [Настройка веб-канала](feed-customization-wcf-data-services.md).  
  
 Модель данных для этого примера определяется в разделе [как: Создание службы данных с помощью поставщика отражения](create-a-data-service-using-rp-wcf-data-services.md)  
  
## <a name="example"></a>Пример  
 В следующем примере оба свойства типа `Order` отображаются на существующие элементы Atom. Свойство `Product` типа `Item` отображается на специализированный атрибут канала в отдельном пространстве имен.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>Пример  
 Предыдущий пример возвращает следующий результат для URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>См. также

- [Поставщик отражений](reflection-provider-wcf-data-services.md)
