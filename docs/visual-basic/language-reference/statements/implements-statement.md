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
ms.openlocfilehash: e2e279b2c935dd082cbf832265a8ad09e6dffe9e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351151"
---
# <a name="implements-statement"></a><span data-ttu-id="5d5aa-102">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="5d5aa-102">Implements Statement</span></span>
<span data-ttu-id="5d5aa-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d5aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d5aa-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="5d5aa-105">Части</span><span class="sxs-lookup"><span data-stu-id="5d5aa-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="5d5aa-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-106">Required.</span></span> <span data-ttu-id="5d5aa-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="5d5aa-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-108">Required.</span></span> <span data-ttu-id="5d5aa-109">The member of an interface that is being implemented.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d5aa-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="5d5aa-110">Remarks</span></span>  
 <span data-ttu-id="5d5aa-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="5d5aa-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="5d5aa-113">Дополнительные сведения см. в статье [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="5d5aa-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="5d5aa-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="5d5aa-115">When you implement an interface, you must implement all the members declared in the interface.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="5d5aa-116">Omitting any member is considered to be a syntax error.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="5d5aa-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="5d5aa-118">Дополнительные сведения см. в статье [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="5d5aa-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="5d5aa-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d5aa-120">Пример</span><span class="sxs-lookup"><span data-stu-id="5d5aa-120">Example</span></span>  
 <span data-ttu-id="5d5aa-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="5d5aa-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="5d5aa-123">The class `customerInfo` implements all the members defined in the interface.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="5d5aa-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="5d5aa-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d5aa-126">Пример</span><span class="sxs-lookup"><span data-stu-id="5d5aa-126">Example</span></span>  
 <span data-ttu-id="5d5aa-127">The following two procedures show how you could use the interface implemented in the preceding example.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="5d5aa-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span><span class="sxs-lookup"><span data-stu-id="5d5aa-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="5d5aa-129">См. также</span><span class="sxs-lookup"><span data-stu-id="5d5aa-129">See also</span></span>

- [<span data-ttu-id="5d5aa-130">Implements</span><span class="sxs-lookup"><span data-stu-id="5d5aa-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)
- [<span data-ttu-id="5d5aa-131">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="5d5aa-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="5d5aa-132">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="5d5aa-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
