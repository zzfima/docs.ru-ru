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
ms.openlocfilehash: c128ab9982ae7ccd5fff34020f2750f703da16a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664607"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="ef8d6-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef8d6-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="ef8d6-103">Указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework, на основе внешнего имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="ef8d6-104">При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="ef8d6-105">Эти сведения включают местонахождения процедуры, ее идентификатор, его последовательность вызова и тип возвращаемого значения и строки кодировку.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="ef8d6-106">[Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="ef8d6-107">`charsetmodifier` В `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="ef8d6-108">Оно также влияет, как Visual Basic выполняет внешнем файле имя внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="ef8d6-109">`Auto` Модификатор указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework, его следует определить базовый кодировки среды выполнения платформы и, возможно, изменить имя внешней процедуры, если начальный поиск происходит сбой.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="ef8d6-110">Дополнительные сведения см. в разделе «Наборы символов» в [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ef8d6-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="ef8d6-111">Если указан никакой модификатор набора символов, `Ansi` используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef8d6-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef8d6-112">Remarks</span></span>  
 <span data-ttu-id="ef8d6-113">`Auto` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="ef8d6-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="ef8d6-114">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="ef8d6-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="ef8d6-115">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="ef8d6-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="ef8d6-116">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ef8d6-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef8d6-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ef8d6-117">See also</span></span>
- [<span data-ttu-id="ef8d6-118">ANSI</span><span class="sxs-lookup"><span data-stu-id="ef8d6-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="ef8d6-119">Юникод</span><span class="sxs-lookup"><span data-stu-id="ef8d6-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="ef8d6-120">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="ef8d6-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
