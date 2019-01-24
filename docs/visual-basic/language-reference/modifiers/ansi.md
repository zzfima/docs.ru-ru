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
ms.openlocfilehash: e474bd686cc753a0265df1fc2914a73d1b62f1b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737326"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="36ca0-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36ca0-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="36ca0-103">Указывает, что Visual Basic должен маршалировать все строки в Американский национальный институт стандартов (ANSI) независимо от имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="36ca0-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="36ca0-104">При вызове процедуры, определенные вне проекта, компилятор Visual Basic имеет доступ к сведениям, необходимым для корректного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="36ca0-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="36ca0-105">Эти сведения включают местонахождения процедуры, ее идентификатор, его последовательность вызова и тип возвращаемого значения и строки кодировку.</span><span class="sxs-lookup"><span data-stu-id="36ca0-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="36ca0-106">[Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет необходимую информацию.</span><span class="sxs-lookup"><span data-stu-id="36ca0-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="36ca0-107">`charsetmodifier` В `Declare` оператор содержит сведения для маршалинга строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="36ca0-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="36ca0-108">Оно также влияет, как Visual Basic выполняет внешнем файле имя внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="36ca0-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="36ca0-109">`Ansi` Модификатор указывает, что Visual Basic должен маршалировать все строки в значения ANSI и должен найти процедуру без изменения имени во время поиска.</span><span class="sxs-lookup"><span data-stu-id="36ca0-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="36ca0-110">Если указан никакой модификатор набора символов, `Ansi` используется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="36ca0-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36ca0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="36ca0-111">Remarks</span></span>  
 <span data-ttu-id="36ca0-112">`Ansi` Модификатор может использоваться в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="36ca0-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="36ca0-113">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="36ca0-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="36ca0-114">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="36ca0-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="36ca0-115">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="36ca0-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ca0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="36ca0-116">See also</span></span>
- [<span data-ttu-id="36ca0-117">Auto</span><span class="sxs-lookup"><span data-stu-id="36ca0-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="36ca0-118">Юникод</span><span class="sxs-lookup"><span data-stu-id="36ca0-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="36ca0-119">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="36ca0-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
