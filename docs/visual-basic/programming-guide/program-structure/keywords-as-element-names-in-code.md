---
title: Ключевые слова как имена элементов в коде (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 0d52df42b00abfa364762d97c162eb143e511f06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649496"
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="6fefb-102">Ключевые слова как имена элементов в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fefb-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="6fefb-103">Любым элементам программы, такие как переменная, класс или член — может иметь имя, совпадающее с именем служебное слово.</span><span class="sxs-lookup"><span data-stu-id="6fefb-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="6fefb-104">Например, можно создать переменную с именем `Loop`.</span><span class="sxs-lookup"><span data-stu-id="6fefb-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="6fefb-105">Тем не менее для ссылки на переменную, который имеет то же имя, что ограниченных `Loop` ключевое слово — необходимо поставили полной строки или заключите его в квадратные скобки (`[ ]`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6fefb-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 <span data-ttu-id="6fefb-106">Если вы этого не сделать этого, то Visual Basic предполагается, что используется встроенная `Loop` ключевое слово и выводит сообщение об ошибке, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6fefb-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="6fefb-107">Можно использовать квадратные скобки, при ссылке на формах и элементах управления, а также при объявлении переменной или определении процедуры с тем же именем, как только ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="6fefb-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="6fefb-108">Его можно легко забыть определить имена или включать квадратные скобки и таким образом привести к ошибкам в код и сделать его труднее читаться.</span><span class="sxs-lookup"><span data-stu-id="6fefb-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="6fefb-109">По этой причине рекомендуется не использовать служебные ключевые слова как имена элементов программы.</span><span class="sxs-lookup"><span data-stu-id="6fefb-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="6fefb-110">Тем не менее если следующей версии Visual Basic определяет новое ключевое слово конфликтует с существующим именем формы или элемента управления, затем воспользуйтесь этот метод при обновлении кода для работы с новой версией.</span><span class="sxs-lookup"><span data-stu-id="6fefb-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fefb-111">Программы также могут содержаться имена элементов, предоставляемых в других сборках.</span><span class="sxs-lookup"><span data-stu-id="6fefb-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="6fefb-112">Если эти имена конфликтуют с ограниченным доступом ключевые слова, квадратные скобки вокруг них приводит к Visual Basic, чтобы интерпретировать их как определенные вами элементы.</span><span class="sxs-lookup"><span data-stu-id="6fefb-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fefb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6fefb-113">See also</span></span>
- [<span data-ttu-id="6fefb-114">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6fefb-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
- [<span data-ttu-id="6fefb-115">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="6fefb-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="6fefb-116">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="6fefb-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
