---
title: Оператор Implements
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 5afc7e4e3a03dfab1288e50e65e5076bdd438f7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="implements-statement"></a><span data-ttu-id="beb04-102">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="beb04-102">Implements Statement</span></span>
<span data-ttu-id="beb04-103">Указывает один или несколько интерфейсов, или членов интерфейса, которые должны быть реализованы в классе или определение структуры, в котором он отображается.</span><span class="sxs-lookup"><span data-stu-id="beb04-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beb04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beb04-104">Syntax</span></span>  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="beb04-105">Части</span><span class="sxs-lookup"><span data-stu-id="beb04-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="beb04-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="beb04-106">Required.</span></span> <span data-ttu-id="beb04-107">Интерфейс, свойства, процедуры и события, должны быть реализованы соответствующие элементы в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="beb04-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="beb04-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="beb04-108">Required.</span></span> <span data-ttu-id="beb04-109">Член интерфейса, который реализуется.</span><span class="sxs-lookup"><span data-stu-id="beb04-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beb04-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="beb04-110">Remarks</span></span>  
 <span data-ttu-id="beb04-111">Интерфейс — это коллекция прототипов, представляющих члены (свойства, процедуры и события) инкапсулирует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="beb04-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="beb04-112">Интерфейсы содержат только объявления членов. классы и структуры реализуют эти члены.</span><span class="sxs-lookup"><span data-stu-id="beb04-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="beb04-113">Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="beb04-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="beb04-114">`Implements` Инструкции следует непосредственно за `Class` или `Structure` инструкции.</span><span class="sxs-lookup"><span data-stu-id="beb04-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="beb04-115">При реализации интерфейса необходимо реализовать все члены, объявленные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="beb04-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="beb04-116">Пропуск любого элемента считается синтаксическую ошибку.</span><span class="sxs-lookup"><span data-stu-id="beb04-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="beb04-117">Чтобы реализовать отдельные члены, необходимо указать [реализует](../../../visual-basic/language-reference/statements/implements-clause.md) ключевое слово (отделен от `Implements` инструкции) при объявлении члена в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="beb04-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="beb04-118">Дополнительные сведения см. в разделе [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="beb04-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="beb04-119">Классы могут использовать [закрытый](../../../visual-basic/language-reference/modifiers/private.md) реализации свойства и процедуры, однако эти члены доступны только путем приведения экземпляра реализующего класса в переменной, объявленной как типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="beb04-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beb04-120">Пример</span><span class="sxs-lookup"><span data-stu-id="beb04-120">Example</span></span>  
 <span data-ttu-id="beb04-121">В следующем примере показано, как использовать `Implements` инструкции для реализации членов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="beb04-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="beb04-122">Он определяет интерфейс с именем `ICustomerInfo` с событием, свойства и процедуры.</span><span class="sxs-lookup"><span data-stu-id="beb04-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="beb04-123">Класс `customerInfo` реализует все члены, определенные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="beb04-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_1.vb)]  
  
 <span data-ttu-id="beb04-124">Обратите внимание, что класс `customerInfo` использует `Implements` инструкции на отдельной строке исходного кода, чтобы указать, что класс реализует все члены `ICustomerInfo` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="beb04-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="beb04-125">Затем каждый член класса использует `Implements` ключевое слово как часть объявления, чтобы указать, что он реализует член этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="beb04-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="beb04-126">Пример</span><span class="sxs-lookup"><span data-stu-id="beb04-126">Example</span></span>  
 <span data-ttu-id="beb04-127">В следующих двух процедурах показано, как можно использовать интерфейс, реализованный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="beb04-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="beb04-128">Чтобы проверить реализацию, добавьте эти процедуры в проекте и вызовите `testImplements` процедуры.</span><span class="sxs-lookup"><span data-stu-id="beb04-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/implements-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="beb04-129">См. также</span><span class="sxs-lookup"><span data-stu-id="beb04-129">See Also</span></span>  
 [<span data-ttu-id="beb04-130">Implements</span><span class="sxs-lookup"><span data-stu-id="beb04-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)  
 [<span data-ttu-id="beb04-131">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="beb04-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="beb04-132">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="beb04-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
