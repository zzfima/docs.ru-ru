---
title: Локальные вызовы методов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
ms.openlocfilehash: ec288d5ac2f6466860362be82c619c89204e8f31
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781417"
---
# <a name="local-method-calls"></a><span data-ttu-id="3184c-102">Локальные вызовы методов</span><span class="sxs-lookup"><span data-stu-id="3184c-102">Local Method Calls</span></span>
<span data-ttu-id="3184c-103">Локальным вызовом метода называется вызов, который выполняется в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="3184c-103">A local method call is one that is executed within the object model.</span></span> <span data-ttu-id="3184c-104">Удаленный вызов метода - это вызов, который [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует в команды SQL и передает в ядро базы данных для выполнения.</span><span class="sxs-lookup"><span data-stu-id="3184c-104">A remote method call is one that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates to SQL and transmits to the database engine for execution.</span></span> <span data-ttu-id="3184c-105">Локальные вызовы методов необходимы, когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не удается перевести вызов в SQL.</span><span class="sxs-lookup"><span data-stu-id="3184c-105">Local method calls are needed when [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot translate the call into SQL.</span></span> <span data-ttu-id="3184c-106">В противном случае возникает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="3184c-106">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="3184c-107">Пример 1</span><span class="sxs-lookup"><span data-stu-id="3184c-107">Example 1</span></span>  
 <span data-ttu-id="3184c-108">В следующем примере класс `Order` сопоставлен с таблицей "Orders" базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="3184c-108">In the following example, an `Order` class is mapped to the Orders table in the Northwind sample database.</span></span> <span data-ttu-id="3184c-109">К классу добавлен локальный экземпляр метода.</span><span class="sxs-lookup"><span data-stu-id="3184c-109">A local instance method has been added to the class.</span></span>  
  
 <span data-ttu-id="3184c-110">В запросе 1 конструктор для класса `Order` выполняется локально.</span><span class="sxs-lookup"><span data-stu-id="3184c-110">In Query 1, the constructor for the `Order` class is executed locally.</span></span> <span data-ttu-id="3184c-111">В запросе 2, если бы технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] попыталась преобразовать метод `LocalInstanceMethod()`в команды SQL, попытка закончилась бы неудачей и было бы создано исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="3184c-111">In Query 2, if [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tried to translate `LocalInstanceMethod()`into SQL, the attempt would fail and an <xref:System.InvalidOperationException> exception would be thrown.</span></span> <span data-ttu-id="3184c-112">Однако поскольку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обеспечивает поддержку локальных вызовов метода, в запросе 2 не создается исключение.</span><span class="sxs-lookup"><span data-stu-id="3184c-112">But because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides support for local method calls, Query2 will not throw an exception.</span></span>  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3184c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3184c-113">See also</span></span>

- [<span data-ttu-id="3184c-114">Основные сведения</span><span class="sxs-lookup"><span data-stu-id="3184c-114">Background Information</span></span>](background-information.md)
