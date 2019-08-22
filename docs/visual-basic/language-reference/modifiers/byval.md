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
ms.openlocfilehash: 1fa4c1fa0a2def02dd56fa3728a8df4b5ff16b7f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666851"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="26815-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26815-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="26815-103">Указывает, что аргумент передается [по значению](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), поэтому вызываемая процедура или свойство не может изменить значение переменной, которая является базовым аргументом в вызывающем коде.</span><span class="sxs-lookup"><span data-stu-id="26815-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="26815-104">Если модификатор не указан, по умолчанию используется значение ByVal.</span><span class="sxs-lookup"><span data-stu-id="26815-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="26815-105">Поскольку это значение по умолчанию, нет необходимости явно указывать `ByVal` ключевое слово в сигнатурах метода.</span><span class="sxs-lookup"><span data-stu-id="26815-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="26815-106">Он, как правило, создает шум и часто ведет к нестандартному `ByRef` ключевому слову.</span><span class="sxs-lookup"><span data-stu-id="26815-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="26815-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="26815-107">Remarks</span></span>
 <span data-ttu-id="26815-108">Модификатор `ByVal` можно использовать в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="26815-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="26815-109">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="26815-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

 [<span data-ttu-id="26815-110">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="26815-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [<span data-ttu-id="26815-111">Оператор Statement</span><span class="sxs-lookup"><span data-stu-id="26815-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [<span data-ttu-id="26815-112">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="26815-112">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [<span data-ttu-id="26815-113">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="26815-113">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="26815-114">Пример</span><span class="sxs-lookup"><span data-stu-id="26815-114">Example</span></span>
 <span data-ttu-id="26815-115">В следующем примере демонстрируется использование `ByVal` механизма передачи параметров с аргументом ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="26815-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="26815-116">В примере аргумент — это `c1`экземпляр класса. `Class1`</span><span class="sxs-lookup"><span data-stu-id="26815-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="26815-117">`ByVal`запрещает коду в процедурах изменять базовое значение ссылочного аргумента, `c1`, но не защищает доступные поля и `c1`свойства.</span><span class="sxs-lookup"><span data-stu-id="26815-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="26815-118">См. также</span><span class="sxs-lookup"><span data-stu-id="26815-118">See also</span></span>

- [<span data-ttu-id="26815-119">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="26815-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="26815-120">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="26815-120">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
