---
title: "Добавление бизнес-логики с использованием разделяемых методов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f9cbaa156fd794a6f9faf44d8d980159f8ae520e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="adding-business-logic-by-using-partial-methods"></a><span data-ttu-id="cfa97-102">Добавление бизнес-логики с использованием разделяемых методов</span><span class="sxs-lookup"><span data-stu-id="cfa97-102">Adding Business Logic By Using Partial Methods</span></span>
<span data-ttu-id="cfa97-103">Вы можете настроить [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] и C# кода в ваш [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проектов с помощью *разделяемые методы*.</span><span class="sxs-lookup"><span data-stu-id="cfa97-103">You can customize [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# generated code in your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects by using *partial methods*.</span></span> <span data-ttu-id="cfa97-104">Код, созданный [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], определяет сигнатуры как одну часть разделяемого метода.</span><span class="sxs-lookup"><span data-stu-id="cfa97-104">The code that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates defines signatures as one part of a partial method.</span></span> <span data-ttu-id="cfa97-105">Если необходимо реализовать метод, можно добавить собственный разделяемый метод.</span><span class="sxs-lookup"><span data-stu-id="cfa97-105">If you want to implement the method, you can add your own partial method.</span></span> <span data-ttu-id="cfa97-106">Если собственная реализация не добавляется, компилятор отменяет сигнатуру разделяемых методов и вызывает в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] методы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cfa97-106">If you do not add your own implementation, the compiler discards the partial methods signature and calls the default methods in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfa97-107">При использовании среды [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] можно с помощью конструктора [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] добавить проверки и другие пользовательские настройки в классы сущностей.</span><span class="sxs-lookup"><span data-stu-id="cfa97-107">If you are using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to add validation and other customizations to entity classes.</span></span>  
  
 <span data-ttu-id="cfa97-108">Например, применяемое по умолчанию сопоставление для класса `Customer` в образце базы данных Northwind включает следующий разделяемый метод:</span><span class="sxs-lookup"><span data-stu-id="cfa97-108">For example, the default mapping for the `Customer` class in the Northwind sample database includes the following partial method:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 <span data-ttu-id="cfa97-109">Можно реализовать собственный метод путем добавления кода, подобного представленному далее, в собственный разделяемый класс `Customer`.</span><span class="sxs-lookup"><span data-stu-id="cfa97-109">You can implement your own method by adding code such as the following to your own partial `Customer` class:</span></span>  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 <span data-ttu-id="cfa97-110">Такой подход обычно используется в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] переопределение методов по умолчанию для `Insert`, `Update`, `Delete`и для проверки свойств во время событий жизненного цикла объекта.</span><span class="sxs-lookup"><span data-stu-id="cfa97-110">This approach is typically used in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] to override default methods for `Insert`, `Update`, `Delete`, and to validate properties during object life-cycle events.</span></span>  
  
 <span data-ttu-id="cfa97-111">Дополнительные сведения см. в разделе [разделяемые методы](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) или [разделяемый (метод) (Справочник по C#)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span><span class="sxs-lookup"><span data-stu-id="cfa97-111">For more information, see [Partial Methods](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md) ([!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) or [partial (Method) (C# Reference)](~/docs/csharp/language-reference/keywords/partial-method.md) (C#).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfa97-112">Пример</span><span class="sxs-lookup"><span data-stu-id="cfa97-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cfa97-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cfa97-113">Description</span></span>  
 <span data-ttu-id="cfa97-114">В примере кода `ExampleClass` сначала отображается так, как если бы он был определен с помощью средства создания кода, например SQLMetal, а затем так, как при реализации только одного из двух методов.</span><span class="sxs-lookup"><span data-stu-id="cfa97-114">The following example shows `ExampleClass` first as it might be defined by a code-generating tool such as SQLMetal, and then how you might implement only one of the two methods.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cfa97-115">Код</span><span class="sxs-lookup"><span data-stu-id="cfa97-115">Code</span></span>  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="cfa97-116">Пример</span><span class="sxs-lookup"><span data-stu-id="cfa97-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cfa97-117">Описание</span><span class="sxs-lookup"><span data-stu-id="cfa97-117">Description</span></span>  
 <span data-ttu-id="cfa97-118">В следующем примере используется связь между сущностями `Shipper` и `Order`.</span><span class="sxs-lookup"><span data-stu-id="cfa97-118">The following example uses the relationship between `Shipper` and `Order` entities.</span></span> <span data-ttu-id="cfa97-119">Среди прочих методов обратите внимание на разделяемые - `InsertShipper` и `DeleteShipper`.</span><span class="sxs-lookup"><span data-stu-id="cfa97-119">Note among the methods the partial methods, `InsertShipper` and `DeleteShipper`.</span></span> <span data-ttu-id="cfa97-120">По умолчанию разделяемые методы, предоставленные переопределить эти методы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставления.</span><span class="sxs-lookup"><span data-stu-id="cfa97-120">These methods override the default partial methods supplied by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] mapping.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cfa97-121">Код</span><span class="sxs-lookup"><span data-stu-id="cfa97-121">Code</span></span>  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="cfa97-122">См. также</span><span class="sxs-lookup"><span data-stu-id="cfa97-122">See Also</span></span>  
 [<span data-ttu-id="cfa97-123">Внесение и отправка изменений данных</span><span class="sxs-lookup"><span data-stu-id="cfa97-123">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="cfa97-124">Настройка вставки, обновления и удаления</span><span class="sxs-lookup"><span data-stu-id="cfa97-124">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
