---
title: Аргументы типа не могут быть выведены от делегата
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 1024cf6f2c1fa112db29cb710eef190a5022d3af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013638"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a><span data-ttu-id="053ad-102">Аргументы типа не могут быть выведены от делегата</span><span class="sxs-lookup"><span data-stu-id="053ad-102">Type arguments could not be inferred from the delegate</span></span>
<span data-ttu-id="053ad-103">Оператор назначения использует `AddressOf` для назначения делегату адреса универсальной процедуры, но он не предоставляет универсальной процедуре никакие аргументы типа.</span><span class="sxs-lookup"><span data-stu-id="053ad-103">An assignment statement uses `AddressOf` to assign the address of a generic procedure to a delegate, but it does not supply any type arguments to the generic procedure.</span></span>  
  
 <span data-ttu-id="053ad-104">Как правило, при вызове универсального типа указывается аргумент типа для каждого параметра типа, определяемого этим универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="053ad-104">Normally, when you invoke a generic type, you supply a type argument for each type parameter that the generic type defines.</span></span> <span data-ttu-id="053ad-105">Если вы не предоставляете никакие аргументы типов, компилятор пытается вывести типы, которые должны быть переданы в параметры типов.</span><span class="sxs-lookup"><span data-stu-id="053ad-105">If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters.</span></span> <span data-ttu-id="053ad-106">Если контекст не предоставляет достаточно сведений, чтобы компилятор мог вывести типы, возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="053ad-106">If the context does not provide enough information for the compiler to infer the types, an error is generated.</span></span>  
  
 <span data-ttu-id="053ad-107">**Идентификатор ошибки:** BC36564</span><span class="sxs-lookup"><span data-stu-id="053ad-107">**Error ID:** BC36564</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="053ad-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="053ad-108">To correct this error</span></span>  
  
- <span data-ttu-id="053ad-109">Укажите аргументы типа для универсальной процедуры в выражении `AddressOf` .</span><span class="sxs-lookup"><span data-stu-id="053ad-109">Specify the type arguments for the generic procedure in the `AddressOf` expression.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053ad-110">См. также</span><span class="sxs-lookup"><span data-stu-id="053ad-110">See also</span></span>

- [<span data-ttu-id="053ad-111">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="053ad-111">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="053ad-112">Оператор AddressOf</span><span class="sxs-lookup"><span data-stu-id="053ad-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="053ad-113">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="053ad-113">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [<span data-ttu-id="053ad-114">Список типов</span><span class="sxs-lookup"><span data-stu-id="053ad-114">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="053ad-115">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="053ad-115">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
