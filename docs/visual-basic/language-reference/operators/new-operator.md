---
title: Оператор New (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 0fe511b2c16681d7bab7eeda7c121fcbbaa2f5dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603643"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="1a2ea-102">Оператор New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a2ea-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="1a2ea-103">Представляет `New` предложений, чтобы создать новый экземпляр объекта, задает ограничение конструктору по параметру типа, либо определяет `Sub` процедуры как конструктор класса.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a2ea-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="1a2ea-104">Remarks</span></span>  
 <span data-ttu-id="1a2ea-105">В объявлении или оператор присваивания `New` предложения необходимо указать определенный класс, из которого может быть создан экземпляр.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="1a2ea-106">Это означает, что класс должен предоставлять один или несколько конструкторов, которые вызывающий код может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="1a2ea-107">Можно использовать `New` предложение в операторе объявления или присваивания.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="1a2ea-108">При выполнении оператора вызывается соответствующий конструктор указанного класса, передавая все аргументы, которые вы задали.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="1a2ea-109">В следующем примере демонстрируется это путем создания экземпляров `Customer` класс, который имеет два конструктора, один, который не имеет параметров, а другой принимает строковый параметр.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 <span data-ttu-id="1a2ea-110">Поскольку массивы являются классами, `New` можно создать новый экземпляр массива, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 <span data-ttu-id="1a2ea-111">Общеязыковая среда выполнения (CLR) создает <xref:System.OutOfMemoryException> ошибки, если недостаточно памяти для создания нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a2ea-112">`New` Ключевое слово также используется в списках параметров типа для указания, что данный тип должен предоставлять доступ к конструктору без параметров.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="1a2ea-113">Дополнительные сведения о параметрах типа и ограничениях см. в разделе [список типов](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="1a2ea-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="1a2ea-114">Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="1a2ea-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="1a2ea-115">Дополнительные сведения см. в разделе [время существования объекта: как объекты, создание и удаление](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="1a2ea-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="1a2ea-116">Ключевое слово `New` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="1a2ea-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="1a2ea-117">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="1a2ea-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="1a2ea-118">Of</span><span class="sxs-lookup"><span data-stu-id="1a2ea-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="1a2ea-119">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="1a2ea-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="1a2ea-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1a2ea-120">See Also</span></span>  
 <xref:System.OutOfMemoryException>  
 [<span data-ttu-id="1a2ea-121">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="1a2ea-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="1a2ea-122">Список типов</span><span class="sxs-lookup"><span data-stu-id="1a2ea-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="1a2ea-123">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1a2ea-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="1a2ea-124">Время существования. Создание и уничтожение объектов</span><span class="sxs-lookup"><span data-stu-id="1a2ea-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
