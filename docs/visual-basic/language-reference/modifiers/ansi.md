---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: c7037acac58de56a396bd89f595ef897743ff4e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595083"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="f7571-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7571-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="f7571-103">Указывает, что Visual Basic должен маршалировать все строки в значения Американский национальный институт стандартов (ANSI), независимо от имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="f7571-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="f7571-104">При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="f7571-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="f7571-105">Эти сведения включают которой находится процедура, ее идентификатор, последовательность вызова и тип возвращаемого значения и строки кодировку.</span><span class="sxs-lookup"><span data-stu-id="f7571-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="f7571-106">[Инструкции Declare](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.</span><span class="sxs-lookup"><span data-stu-id="f7571-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="f7571-107">`charsetmodifier` Часть — в `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="f7571-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="f7571-108">Оно также влияет как поиска Visual Basic во внешнем файле имя внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="f7571-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="f7571-109">`Ansi` Модификатор указывает, что Visual Basic должен маршалировать все строки в значения ANSI и должен найти процедуру без изменения имени во время поиска.</span><span class="sxs-lookup"><span data-stu-id="f7571-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="f7571-110">Если указан никакой модификатор набор символов, `Ansi` значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f7571-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7571-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7571-111">Remarks</span></span>  
 <span data-ttu-id="f7571-112">`Ansi` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="f7571-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="f7571-113">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="f7571-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="f7571-114">Примечания для разработчиков интеллектуальных устройств</span><span class="sxs-lookup"><span data-stu-id="f7571-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="f7571-115">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f7571-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7571-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f7571-116">See Also</span></span>  
 [<span data-ttu-id="f7571-117">Auto</span><span class="sxs-lookup"><span data-stu-id="f7571-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="f7571-118">Юникод</span><span class="sxs-lookup"><span data-stu-id="f7571-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [<span data-ttu-id="f7571-119">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="f7571-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
