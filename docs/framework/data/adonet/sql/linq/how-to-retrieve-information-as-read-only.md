---
title: Как выполнить получать информацию в режиме только для чтения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
ms.openlocfilehash: 8b83a77adb02cc2bcc01b274867143887114bb1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669553"
---
# <a name="how-to-retrieve-information-as-read-only"></a>Как выполнить получать информацию в режиме только для чтения
Если не планируется изменять данные, можно повысить производительность запросов за счет поиска результатов, предназначенных только для чтения.  
  
 Чтобы реализовать обработку запросов только для чтения, установите для свойства <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> значение `false`.  
  
> [!NOTE]
>  Если для свойства <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> установлено значение `false`, то для свойства <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> неявно устанавливается значение `false`.  
  
## <a name="example"></a>Пример  
 В следующем примере кода извлекается коллекция дат приема на работу сотрудников, предназначенная только для чтения.  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>См. также
- [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [Запрос к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
- [Отложенная и немедленная загрузка](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
