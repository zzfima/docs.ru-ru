---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 414998b4bef526060e7ba4f584fa071fbd0acaa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="auto-visual-basic"></a><span data-ttu-id="b9cc1-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9cc1-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="b9cc1-103">Указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework на основе внешнего имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="b9cc1-104">При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="b9cc1-105">Эти сведения включают которой находится процедура, ее идентификатор, последовательность вызова и тип возвращаемого значения и строки кодировку.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="b9cc1-106">[Инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="b9cc1-107">`charsetmodifier` Часть — в `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="b9cc1-108">Оно также влияет как поиска Visual Basic во внешнем файле имя внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="b9cc1-109">`Auto` Модификатор указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework, его следует определить базовый кодировки платформы во время выполнения и, возможно, изменить имя внешней процедуры начального поиска не выполняется.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="b9cc1-110">Дополнительные сведения см. в разделе «Наборы символов» в [инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b9cc1-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="b9cc1-111">Если указан никакой модификатор набор символов, `Ansi` значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9cc1-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9cc1-112">Remarks</span></span>  
 <span data-ttu-id="b9cc1-113">`Auto` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="b9cc1-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="b9cc1-114">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="b9cc1-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="b9cc1-115">Примечания для разработчиков интеллектуальных устройств</span><span class="sxs-lookup"><span data-stu-id="b9cc1-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="b9cc1-116">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b9cc1-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9cc1-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b9cc1-117">See Also</span></span>  
 [<span data-ttu-id="b9cc1-118">ANSI</span><span class="sxs-lookup"><span data-stu-id="b9cc1-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [<span data-ttu-id="b9cc1-119">Юникод</span><span class="sxs-lookup"><span data-stu-id="b9cc1-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [<span data-ttu-id="b9cc1-120">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="b9cc1-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
