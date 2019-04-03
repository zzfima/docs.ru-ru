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
ms.openlocfilehash: e4beb320b3aa0cadb790dd3ab92255496bc32f05
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843842"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="81822-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81822-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="81822-103">Указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework, на основе внешнего имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="81822-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="81822-104">При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="81822-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="81822-105">Эти сведения включают местонахождения процедуры, ее идентификатор, его последовательность вызова и тип возвращаемого значения и строки кодировку.</span><span class="sxs-lookup"><span data-stu-id="81822-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="81822-106">[Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.</span><span class="sxs-lookup"><span data-stu-id="81822-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="81822-107">`charsetmodifier` В `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="81822-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="81822-108">Оно также влияет, как Visual Basic выполняет внешнем файле имя внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="81822-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="81822-109">`Auto` Модификатор указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework, его следует определить базовый кодировки среды выполнения платформы и, возможно, изменить имя внешней процедуры, если начальный поиск происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="81822-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="81822-110">Дополнительные сведения см. в разделе «Наборы символов» в [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="81822-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="81822-111">Если указан никакой модификатор набора символов, `Ansi` используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="81822-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81822-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="81822-112">Remarks</span></span>  
 <span data-ttu-id="81822-113">`Auto` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="81822-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="81822-114">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="81822-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="81822-115">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="81822-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="81822-116">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="81822-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81822-117">См. также</span><span class="sxs-lookup"><span data-stu-id="81822-117">See also</span></span>

- [<span data-ttu-id="81822-118">ANSI</span><span class="sxs-lookup"><span data-stu-id="81822-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="81822-119">Юникод</span><span class="sxs-lookup"><span data-stu-id="81822-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="81822-120">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="81822-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
