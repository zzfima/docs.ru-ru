---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 0c38c2b81af7b4cb8fd1723853a09c5413f805af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344738"
---
# <a name="ansi-visual-basic"></a><span data-ttu-id="7b586-102">Ansi (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b586-102">Ansi (Visual Basic)</span></span>
<span data-ttu-id="7b586-103">Указывает, что Visual Basic должны маршалировать все строки в значения Американский национальный институт стандартов (ANSI) (ANSI) независимо от имени объявляемой внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="7b586-103">Specifies that Visual Basic should marshal all strings to American National Standards Institute (ANSI) values regardless of the name of the external procedure being declared.</span></span>  
  
 <span data-ttu-id="7b586-104">При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="7b586-104">When you call a procedure defined outside your project, the Visual Basic compiler does not have access to the information it needs to call the procedure correctly.</span></span> <span data-ttu-id="7b586-105">Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку.</span><span class="sxs-lookup"><span data-stu-id="7b586-105">This information includes where the procedure is located, how it is identified, its calling sequence and return type, and the string character set it uses.</span></span> <span data-ttu-id="7b586-106">[Инструкция DECLARE](../../../visual-basic/language-reference/statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.</span><span class="sxs-lookup"><span data-stu-id="7b586-106">The [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) creates a reference to an external procedure and supplies this necessary information.</span></span>  
  
 <span data-ttu-id="7b586-107">`charsetmodifier` часть в инструкции `Declare` предоставляет сведения о кодировке для упаковки строк во время вызова внешней процедуры.</span><span class="sxs-lookup"><span data-stu-id="7b586-107">The `charsetmodifier` part in the `Declare` statement supplies the character set information for marshaling strings during a call to the external procedure.</span></span> <span data-ttu-id="7b586-108">Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле.</span><span class="sxs-lookup"><span data-stu-id="7b586-108">It also affects how Visual Basic searches the external file for the external procedure name.</span></span> <span data-ttu-id="7b586-109">Модификатор `Ansi` указывает, что Visual Basic должен маршалировать все строки в значения ANSI и выполнять поиск процедуры, не изменяя ее имя во время поиска.</span><span class="sxs-lookup"><span data-stu-id="7b586-109">The `Ansi` modifier specifies that Visual Basic should marshal all strings to ANSI values and should look up the procedure without modifying its name during the search.</span></span>  
  
 <span data-ttu-id="7b586-110">Если модификатор кодировки не указан, по умолчанию используется `Ansi`.</span><span class="sxs-lookup"><span data-stu-id="7b586-110">If no character set modifier is specified, `Ansi` is the default.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b586-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="7b586-111">Remarks</span></span>  
 <span data-ttu-id="7b586-112">Модификатор `Ansi` можно использовать в этом контексте:</span><span class="sxs-lookup"><span data-stu-id="7b586-112">The `Ansi` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="7b586-113">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="7b586-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="7b586-114">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="7b586-114">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="7b586-115">Это ключевое слово не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7b586-115">This keyword is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b586-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7b586-116">See also</span></span>

- [<span data-ttu-id="7b586-117">Auto</span><span class="sxs-lookup"><span data-stu-id="7b586-117">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="7b586-118">Юникод</span><span class="sxs-lookup"><span data-stu-id="7b586-118">Unicode</span></span>](../../../visual-basic/language-reference/modifiers/unicode.md)
- [<span data-ttu-id="7b586-119">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="7b586-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
