---
title: Практическое руководство. Как получить сведения о конфликтах элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
ms.openlocfilehash: 40caa07488cb40ca8e9e3eb3a570c325b92de491
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793305"
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="8c739-102">Практическое руководство. Как получить сведения о конфликтах элементов</span><span class="sxs-lookup"><span data-stu-id="8c739-102">How to: Retrieve Member Conflict Information</span></span>
<span data-ttu-id="8c739-103">Класс <xref:System.Data.Linq.MemberChangeConflict> можно использовать для получения сведений об отдельных членах конфликта.</span><span class="sxs-lookup"><span data-stu-id="8c739-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="8c739-104">В этом же контексте можно предусмотреть пользовательскую обработку конфликта для любого члена.</span><span class="sxs-lookup"><span data-stu-id="8c739-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="8c739-105">Дополнительные сведения см. в [разделе оптимистичный параллелизм. Обзор](optimistic-concurrency-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8c739-105">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c739-106">Пример</span><span class="sxs-lookup"><span data-stu-id="8c739-106">Example</span></span>  
 <span data-ttu-id="8c739-107">Следующий код выполняет итерацию объектов <xref:System.Data.Linq.ObjectChangeConflict>.</span><span class="sxs-lookup"><span data-stu-id="8c739-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="8c739-108">Итерация выполняется для каждого объекта <xref:System.Data.Linq.MemberChangeConflict>.</span><span class="sxs-lookup"><span data-stu-id="8c739-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c739-109">Для предоставления сведений <xref:System.Reflection> добавьте пространство имен <xref:System.Data.Linq.MemberChangeConflict.Member%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c739-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8c739-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8c739-110">See also</span></span>

- [<span data-ttu-id="8c739-111">Практическое руководство. Управление конфликтами изменений</span><span class="sxs-lookup"><span data-stu-id="8c739-111">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
