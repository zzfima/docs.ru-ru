---
title: Аргументы типа не могут быть выведены от делегата
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 17b65a39082ddaf54aabf12ca9b95e49af80f5f6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666310"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="ee3c3-102">Аргументы типа не могут быть выведены от делегата</span><span class="sxs-lookup"><span data-stu-id="ee3c3-102">Type arguments could not be inferred from the delegate</span></span>
<span data-ttu-id="ee3c3-103">Оператор назначения использует `AddressOf` для назначения делегату адреса универсальной процедуры, но он не предоставляет универсальной процедуре никакие аргументы типа.</span><span class="sxs-lookup"><span data-stu-id="ee3c3-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>  
  
 <span data-ttu-id="ee3c3-104">Как правило, при вызове универсального типа указывается аргумент типа для каждого параметра типа, определяемого этим универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="ee3c3-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="ee3c3-105">Если вы не предоставляете никакие аргументы типов, компилятор пытается вывести типы, которые должны быть переданы в параметры типов.</span><span class="sxs-lookup"><span data-stu-id="ee3c3-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="ee3c3-106">Если контекст не предоставляет достаточно сведений, чтобы компилятор мог вывести типы, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ee3c3-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>  
  
 <span data-ttu-id="ee3c3-107">**Идентификатор ошибки:** BC36564</span><span class="sxs-lookup"><span data-stu-id="ee3c3-107">**Error ID:** BC36564</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ee3c3-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ee3c3-108">To correct this error</span></span>  
  
-   <span data-ttu-id="ee3c3-109">Укажите аргументы типа для универсальной процедуры в выражении `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="ee3c3-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee3c3-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ee3c3-110">See also</span></span>
- [<span data-ttu-id="ee3c3-111">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ee3c3-111">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="ee3c3-112">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="ee3c3-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="ee3c3-113">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ee3c3-113">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="ee3c3-114">Список типов</span><span class="sxs-lookup"><span data-stu-id="ee3c3-114">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="ee3c3-115">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="ee3c3-115">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
