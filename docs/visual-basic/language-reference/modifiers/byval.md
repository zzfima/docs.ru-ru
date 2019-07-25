---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: abfe1489cb7e0d06b03c308e0704ce6f69ee55da
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433806"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="660c4-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="660c4-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="660c4-103">Указывает, что аргумент передается [по значению](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), поэтому вызываемая процедура или свойство не может изменить значение переменной, которая является базовым аргументом в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="660c4-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="660c4-104">Если модификатор не указан, по умолчанию используется значение ByVal.</span><span class="sxs-lookup"><span data-stu-id="660c4-104">If no modifier is specified, ByVal is the default.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="660c4-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="660c4-105">Remarks</span></span>  
 <span data-ttu-id="660c4-106">Модификатор `ByVal` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="660c4-106">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="660c4-107">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="660c4-107">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="660c4-108">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="660c4-108">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="660c4-109">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="660c4-109">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="660c4-110">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="660c4-110">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="660c4-111">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="660c4-111">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="660c4-112">Пример</span><span class="sxs-lookup"><span data-stu-id="660c4-112">Example</span></span>  
 <span data-ttu-id="660c4-113">В следующем примере демонстрируется использование `ByVal` механизма передачи параметров с аргументом ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="660c4-113">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="660c4-114">В примере аргумент — это `c1`экземпляр класса. `Class1`</span><span class="sxs-lookup"><span data-stu-id="660c4-114">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="660c4-115">`ByVal`запрещает коду в процедурах изменять базовое значение ссылочного аргумента, `c1`, но не защищает доступные поля и `c1`свойства.</span><span class="sxs-lookup"><span data-stu-id="660c4-115">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="660c4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="660c4-116">See also</span></span>

- [<span data-ttu-id="660c4-117">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="660c4-117">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="660c4-118">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="660c4-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
