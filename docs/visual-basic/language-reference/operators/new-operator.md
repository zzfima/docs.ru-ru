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
ms.openlocfilehash: dda23ef3ff49bd32474f39f5ae1807e57bdc2a62
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980468"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="0c08b-102">Оператор New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c08b-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="0c08b-103">Представляет `New` предложение, чтобы создать новый экземпляр объекта, задает для параметра типа ограничение конструктора, либо определяет `Sub` процедуры как конструктор класса.</span><span class="sxs-lookup"><span data-stu-id="0c08b-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c08b-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c08b-104">Remarks</span></span>  
 <span data-ttu-id="0c08b-105">В операторе объявления или назначения `New` предложение необходимо указать определенный класс, из которого может быть создан экземпляр.</span><span class="sxs-lookup"><span data-stu-id="0c08b-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="0c08b-106">Это означает, что класс должен предоставлять один или несколько конструкторов, вызывающий код может получить доступ.</span><span class="sxs-lookup"><span data-stu-id="0c08b-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="0c08b-107">Можно использовать `New` предложение в операторе объявления или присваивания.</span><span class="sxs-lookup"><span data-stu-id="0c08b-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="0c08b-108">При выполнении оператора вызывается соответствующий конструктор указанного класса, передав любые аргументы, заданные.</span><span class="sxs-lookup"><span data-stu-id="0c08b-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="0c08b-109">В следующем примере показано это путем создания экземпляров `Customer` класс, который имеет два конструктора, который не принимает никаких параметров, а другой принимает строковый параметр.</span><span class="sxs-lookup"><span data-stu-id="0c08b-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="0c08b-110">Поскольку массивы являются классами, `New` можно создать новый экземпляр массива, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="0c08b-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="0c08b-111">Общеязыковая среда выполнения (CLR) создает <xref:System.OutOfMemoryException> ошибки, если недостаточно памяти для создания нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0c08b-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c08b-112">`New` Ключевое слово также используется в списках параметров типа для указания, что тип должен предоставлять доступ к конструктору без параметров.</span><span class="sxs-lookup"><span data-stu-id="0c08b-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="0c08b-113">Дополнительные сведения о параметров типа и ограничений, см. в разделе [список типов](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="0c08b-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="0c08b-114">Чтобы создать процедуру конструктора для класса, задайте имя `Sub` процедура `New` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0c08b-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="0c08b-115">Дополнительные сведения см. в разделе [время жизни объекта: Как создаются и удаляются объекты](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="0c08b-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="0c08b-116">Ключевое слово `New` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="0c08b-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="0c08b-117">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="0c08b-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="0c08b-118">Of</span><span class="sxs-lookup"><span data-stu-id="0c08b-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="0c08b-119">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="0c08b-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="0c08b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0c08b-120">See also</span></span>
- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="0c08b-121">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="0c08b-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="0c08b-122">Список типов</span><span class="sxs-lookup"><span data-stu-id="0c08b-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="0c08b-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c08b-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="0c08b-124">Время существования: Способ создания и уничтожения объектов</span><span class="sxs-lookup"><span data-stu-id="0c08b-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
