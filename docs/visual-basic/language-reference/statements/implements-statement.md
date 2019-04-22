---
title: Оператор Implements (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 1f0c6b052ead303e0b43465dac2067422abc4ef8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818877"
---
# <a name="implements-statement"></a><span data-ttu-id="b4134-102">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="b4134-102">Implements Statement</span></span>
<span data-ttu-id="b4134-103">Указывает один или несколько интерфейсов, или члены интерфейса, которые должны быть реализованы в классе или определение структуры, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="b4134-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4134-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4134-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="b4134-105">Части</span><span class="sxs-lookup"><span data-stu-id="b4134-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="b4134-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b4134-106">Required.</span></span> <span data-ttu-id="b4134-107">Интерфейс, свойства, процедуры и события должны реализовываться соответствующими членами в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="b4134-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="b4134-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b4134-108">Required.</span></span> <span data-ttu-id="b4134-109">Член интерфейса, который реализуется.</span><span class="sxs-lookup"><span data-stu-id="b4134-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4134-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4134-110">Remarks</span></span>  
 <span data-ttu-id="b4134-111">Интерфейс является коллекцией прототипов, представляющих члены (свойства, процедуры и события) инкапсулирует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b4134-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="b4134-112">Интерфейсы содержат только объявления членов. классы и структуры реализуют эти члены.</span><span class="sxs-lookup"><span data-stu-id="b4134-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="b4134-113">Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4134-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="b4134-114">`Implements` Оператора должно следовать сразу `Class` или `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b4134-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="b4134-115">При реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="b4134-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="b4134-116">Пропуск любого члена считается синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="b4134-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="b4134-117">Чтобы реализовать отдельные члены, необходимо указать [реализует](../../../visual-basic/language-reference/statements/implements-clause.md) ключевое слово (отдельными от `Implements` инструкции) при объявлении члена в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="b4134-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="b4134-118">Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4134-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="b4134-119">Классы могут использовать [частного](../../../visual-basic/language-reference/modifiers/private.md) реализации свойства и процедуры, однако эти члены доступны только путем приведения экземпляра реализации класса в переменной, объявленной как типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4134-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4134-120">Пример</span><span class="sxs-lookup"><span data-stu-id="b4134-120">Example</span></span>  
 <span data-ttu-id="b4134-121">В следующем примере показано, как использовать `Implements` инструкцию, чтобы реализовать члены интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4134-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="b4134-122">Он определяет интерфейс с именем `ICustomerInfo` события, свойства и процедуры.</span><span class="sxs-lookup"><span data-stu-id="b4134-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="b4134-123">Класс `customerInfo` реализует все члены, определенные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="b4134-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="b4134-124">Обратите внимание, что класс `customerInfo` использует `Implements` оператором в отдельной строке исходного кода для указания, что данный класс реализует все члены `ICustomerInfo` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b4134-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="b4134-125">Затем каждый член в класс использует `Implements` ключевое слово как часть объявления для указания, что он реализует член этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b4134-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4134-126">Пример</span><span class="sxs-lookup"><span data-stu-id="b4134-126">Example</span></span>  
 <span data-ttu-id="b4134-127">В следующих двух процедурах показано, как использовать интерфейс, реализованный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="b4134-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="b4134-128">Чтобы протестировать реализацию, добавьте эти процедуры в свой проект и вызовите `testImplements` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b4134-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="b4134-129">См. также</span><span class="sxs-lookup"><span data-stu-id="b4134-129">See also</span></span>

- [<span data-ttu-id="b4134-130">Implements</span><span class="sxs-lookup"><span data-stu-id="b4134-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)
- [<span data-ttu-id="b4134-131">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="b4134-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="b4134-132">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="b4134-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
