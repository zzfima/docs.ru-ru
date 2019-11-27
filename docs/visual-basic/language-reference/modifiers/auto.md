---
title: Auto
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 7ea46e5f8b882bb986f23e792b240bad0c5be7a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351621"
---
# <a name="auto-visual-basic"></a><span data-ttu-id="bae92-102">Auto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bae92-102">Auto (Visual Basic)</span></span>
<span data-ttu-id="bae92-103">Указывает, что Visual Basic должны маршалировать строки согласно правилам .NET Framework, исходя из внешнего имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="bae92-103">Specifies that Visual Basic should marshal strings according to .NET Framework rules based on the external name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="bae92-104">При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="bae92-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it must have to call the procedure correctly.</span></span> <span data-ttu-id="bae92-105">Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку.</span><span class="sxs-lookup"><span data-stu-id="bae92-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="bae92-106">[Инструкция DECLARE](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="bae92-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="bae92-107">`charsetmodifier` часть в инструкции `Declare` предоставляет сведения о кодировке для упаковки строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="bae92-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="bae92-108">Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле.</span><span class="sxs-lookup"><span data-stu-id="bae92-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="bae92-109">Модификатор `Auto` указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework и определить базовый набор символов платформы времени выполнения и, возможно, изменить имя внешней процедуры в случае сбоя первоначального поиска.</span><span class="sxs-lookup"><span data-stu-id="bae92-109">The `Auto` modifier specifies that Visual Basic should marshal strings according to .NET Framework rules, and that it should determine the base character set of the run-time platform and possibly modify the external procedure name if the initial search fails.</span></span> <span data-ttu-id="bae92-110">Дополнительные сведения см. в разделе «Наборы символов» в [операторе Declare](../../../visual-basic/language-reference/statements/declare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="bae92-110">For more information, see "Character Sets" in [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md).</span></span>  
  
 <span data-ttu-id="bae92-111">Если модификатор кодировки не указан, по умолчанию используется `Ansi`.</span><span class="sxs-lookup"><span data-stu-id="bae92-111">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bae92-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="bae92-112">Remarks</span></span>  
 <span data-ttu-id="bae92-113">Модификатор `Auto` можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="bae92-113">The `Auto` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="bae92-114">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="bae92-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="bae92-115">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="bae92-115">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="bae92-116">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="bae92-116">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae92-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bae92-117">See also</span></span>

- [<span data-ttu-id="bae92-118">ANSI</span><span class="sxs-lookup"><span data-stu-id="bae92-118">Ansi</span></span>](../../../visual-basic/language-reference/modifiers/ansi.md)
- [<span data-ttu-id="bae92-119">Юникод</span><span class="sxs-lookup"><span data-stu-id="bae92-119">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="bae92-120">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="bae92-120">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
