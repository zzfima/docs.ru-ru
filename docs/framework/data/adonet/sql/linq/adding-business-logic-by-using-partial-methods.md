---
title: Добавление бизнес-логики с использованием разделяемых методов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: ed440f3315fc25e82b648f21410acb7a2c2a08f9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743670"
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="6f3f1-102">Добавление бизнес-логики с использованием разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="6f3f1-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="6f3f1-103">Вы можете настроить Visual Basic и C# созданный код в ваш [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проектов с помощью *разделяемые методы*.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-103">You can customize Visual Basic and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="6f3f1-104">Код, созданный [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], определяет сигнатуры как одну часть разделяемого метода.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="6f3f1-105">Если необходимо реализовать метод, можно добавить собственный разделяемый метод.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="6f3f1-106">Если собственная реализация не добавляется, компилятор отменяет сигнатуру разделяемых методов и вызывает в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] методы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f3f1-107">Если вы используете Visual Studio, чтобы добавить проверки и другие пользовательские настройки в классы сущностей можно использовать реляционный конструктор объектов.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-107">If you are using Visual Studio, you can use the Object Relational Designer to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="6f3f1-108">Например, применяемое по умолчанию сопоставление для класса `Customer` в образце базы данных Northwind включает следующий разделяемый метод:</span><span class="sxs-lookup"><span data-stu-id="6f3f1-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="6f3f1-109">Можно реализовать собственный метод путем добавления кода, подобного представленному далее, в собственный разделяемый класс `Customer`.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="6f3f1-110">Этот подход обычно используется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для переопределения методов по умолчанию для `Insert`, `Update`, `Delete`и для проверки свойств во время событий жизненного цикла объекта.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="6f3f1-111">Дополнительные сведения см. в разделе [разделяемые методы](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) или [разделяемый (метод) (C# ссылку)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="6f3f1-111">For more information, see [Partial Methods](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) or [partial (Method) (C# Reference)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f3f1-112">Пример</span><span class="sxs-lookup"><span data-stu-id="6f3f1-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6f3f1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6f3f1-113">Description</span></span>  
 <span data-ttu-id="6f3f1-114">В примере кода `ExampleClass` сначала отображается так, как если бы он был определен с помощью средства создания кода, например SQLMetal, а затем так, как при реализации только одного из двух методов.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6f3f1-115">Код</span><span class="sxs-lookup"><span data-stu-id="6f3f1-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="6f3f1-116">Пример</span><span class="sxs-lookup"><span data-stu-id="6f3f1-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="6f3f1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="6f3f1-117">Description</span></span>  
 <span data-ttu-id="6f3f1-118">В следующем примере используется связь между сущностями `Shipper` и `Order`.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="6f3f1-119">Среди прочих методов обратите внимание на разделяемые - `InsertShipper` и `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="6f3f1-120">Эти методы переопределения разделяемые методы по умолчанию, предоставленные [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставления.</span><span class="sxs-lookup"><span data-stu-id="6f3f1-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6f3f1-121">Код</span><span class="sxs-lookup"><span data-stu-id="6f3f1-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6f3f1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6f3f1-122">See also</span></span>

- [<span data-ttu-id="6f3f1-123">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="6f3f1-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
- [<span data-ttu-id="6f3f1-124">Настройка операций вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="6f3f1-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
