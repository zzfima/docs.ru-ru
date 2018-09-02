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
ms.openlocfilehash: 805813506b957afb326c71ee4bbb15837726e4e5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425954"
---
# <a name="implements-statement"></a><span data-ttu-id="dca29-102">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="dca29-102">Implements Statement</span></span>
<span data-ttu-id="dca29-103">Указывает один или несколько интерфейсов, или члены интерфейса, которые должны быть реализованы в классе или определение структуры, в котором он находится.</span><span class="sxs-lookup"><span data-stu-id="dca29-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dca29-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="dca29-105">Части</span><span class="sxs-lookup"><span data-stu-id="dca29-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="dca29-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="dca29-106">Required.</span></span> <span data-ttu-id="dca29-107">Интерфейс, свойства, процедуры и события должны реализовываться соответствующими членами в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="dca29-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="dca29-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="dca29-108">Required.</span></span> <span data-ttu-id="dca29-109">Член интерфейса, который реализуется.</span><span class="sxs-lookup"><span data-stu-id="dca29-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dca29-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="dca29-110">Remarks</span></span>  
 <span data-ttu-id="dca29-111">Интерфейс является коллекцией прототипов, представляющих члены (свойства, процедуры и события) инкапсулирует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dca29-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="dca29-112">Интерфейсы содержат только объявления членов. классы и структуры реализуют эти члены.</span><span class="sxs-lookup"><span data-stu-id="dca29-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="dca29-113">Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="dca29-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="dca29-114">`Implements` Оператора должно следовать сразу `Class` или `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="dca29-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="dca29-115">При реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="dca29-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="dca29-116">Пропуск любого члена считается синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="dca29-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="dca29-117">Чтобы реализовать отдельные члены, необходимо указать [реализует](../../../visual-basic/language-reference/statements/implements-clause.md) ключевое слово (отдельными от `Implements` инструкции) при объявлении члена в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="dca29-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="dca29-118">Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="dca29-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="dca29-119">Классы могут использовать [частного](../../../visual-basic/language-reference/modifiers/private.md) реализации свойства и процедуры, однако эти члены доступны только путем приведения экземпляра реализации класса в переменной, объявленной как типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="dca29-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dca29-120">Пример</span><span class="sxs-lookup"><span data-stu-id="dca29-120">Example</span></span>  
 <span data-ttu-id="dca29-121">В следующем примере показано, как использовать `Implements` инструкцию, чтобы реализовать члены интерфейса.</span><span class="sxs-lookup"><span data-stu-id="dca29-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="dca29-122">Он определяет интерфейс с именем `ICustomerInfo` события, свойства и процедуры.</span><span class="sxs-lookup"><span data-stu-id="dca29-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="dca29-123">Класс `customerInfo` реализует все члены, определенные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="dca29-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 <span data-ttu-id="dca29-124">Обратите внимание, что класс `customerInfo` использует `Implements` оператором в отдельной строке исходного кода для указания, что данный класс реализует все члены `ICustomerInfo` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="dca29-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="dca29-125">Затем каждый член в класс использует `Implements` ключевое слово как часть объявления для указания, что он реализует член этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="dca29-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dca29-126">Пример</span><span class="sxs-lookup"><span data-stu-id="dca29-126">Example</span></span>  
 <span data-ttu-id="dca29-127">В следующих двух процедурах показано, как использовать интерфейс, реализованный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="dca29-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="dca29-128">Чтобы протестировать реализацию, добавьте эти процедуры в свой проект и вызовите `testImplements` процедуры.</span><span class="sxs-lookup"><span data-stu-id="dca29-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="dca29-129">См. также</span><span class="sxs-lookup"><span data-stu-id="dca29-129">See Also</span></span>  
 [<span data-ttu-id="dca29-130">Implements</span><span class="sxs-lookup"><span data-stu-id="dca29-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [<span data-ttu-id="dca29-131">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="dca29-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="dca29-132">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="dca29-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
