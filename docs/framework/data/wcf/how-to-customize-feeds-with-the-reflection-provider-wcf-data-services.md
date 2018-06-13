---
title: Практическое руководство. Настройка каналов с поставщиком отражения (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: 984a4aac43689be0ec80e7f6c289e8d5229e9e1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358012"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>Практическое руководство. Настройка каналов с поставщиком отражения (службы данных WCF)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют настроить сериализацию Atom в ответе службы данных так, чтобы свойства сущности сопоставлялись с неиспользуемыми элементами, определенными в протоколе AtomPub. Этот раздел показывает, как настроить атрибуты сопоставления типов сущностей в модели данных, определенной с помощью поставщика отражения. Дополнительные сведения см. в разделе [настройки веб-канал](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 Модели данных в этом примере определяется в разделе [как: создание службы данных с помощью поставщика отражения](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
  
## <a name="example"></a>Пример  
 В следующем примере оба свойства типа `Order` отображаются на существующие элементы Atom. Свойство `Product` типа `Item` отображается на специализированный атрибут канала в отдельном пространстве имен.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>Пример  
 Предыдущий пример возвращает следующий результат для URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>См. также  
 [Поставщик отражений](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
