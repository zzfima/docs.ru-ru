---
title: Ключевые слова как имена элементов в коде (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 53c3172e8518115d001c23be2430fbc87ae1b60f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a><span data-ttu-id="8519a-102">Ключевые слова как имена элементов в коде (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8519a-102">Keywords as Element Names in Code (Visual Basic)</span></span>
<span data-ttu-id="8519a-103">Любой элемент программы, такие как переменная, класс или член, может иметь имя, совпадающее с именем служебное слово.</span><span class="sxs-lookup"><span data-stu-id="8519a-103">Any program element — such as a variable, class, or member — can have the same name as a restricted keyword.</span></span> <span data-ttu-id="8519a-104">Например, можно создать переменную с именем `Loop`.</span><span class="sxs-lookup"><span data-stu-id="8519a-104">For example, you can create a variable named `Loop`.</span></span> <span data-ttu-id="8519a-105">Тем не менее для обращения к вашей версии, который имеет то же имя, как и служебное `Loop` ключевое слово — необходимо добавить перед ее именем полное имя пространства имен или заключите его в квадратные скобки (`[ ]`), как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8519a-105">However, to refer to your version of it — which has the same name as the restricted `Loop` keyword — you must either precede it with a full qualification string or enclose it in square brackets (`[ ]`), as the following example shows.</span></span>  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 <span data-ttu-id="8519a-106">Если этого не сделать, либо из указанных, то Visual Basic предполагает использование встроенного `Loop` ключевое слово и приводит к ошибке, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8519a-106">If you do not do either of these, then Visual Basic assumes use of the intrinsic `Loop` keyword and produces an error, as in the following example:</span></span>  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 <span data-ttu-id="8519a-107">Можно использовать квадратные скобки, при ссылке на формах и элементах управления, а также при объявлении переменной или определении процедуры с тем же именем, как служебное слово.</span><span class="sxs-lookup"><span data-stu-id="8519a-107">You can use square brackets when referring to forms and controls, and when declaring a variable or defining a procedure with the same name as a restricted keyword.</span></span> <span data-ttu-id="8519a-108">Его можно легко забыть квалифицировать имена или содержать квадратные скобки и таким образом приведет к ошибкам в коде и затруднять чтение.</span><span class="sxs-lookup"><span data-stu-id="8519a-108">It can be easy to forget to qualify names or include square brackets, and thus introduce errors into your code and make it harder to read.</span></span> <span data-ttu-id="8519a-109">По этой причине рекомендуется не использовать служебные ключевые слова как имена элементов программы.</span><span class="sxs-lookup"><span data-stu-id="8519a-109">For this reason, we recommend that you not use restricted keywords as the names of program elements.</span></span> <span data-ttu-id="8519a-110">Тем не менее если будущей версии Visual Basic определяет новое ключевое слово конфликтует с существующим именем формы или элемента управления, то вы может использовать этот метод при обновлении кода для работы с новой версией.</span><span class="sxs-lookup"><span data-stu-id="8519a-110">However, if a future version of Visual Basic defines a new keyword that conflicts with an existing form or control name, then you can use this technique when updating your code to work with the new version.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8519a-111">Программа также могут содержаться имена элементов, предоставляемых других сборок.</span><span class="sxs-lookup"><span data-stu-id="8519a-111">Your program also might include element names provided by other referenced assemblies.</span></span> <span data-ttu-id="8519a-112">Если эти имена конфликтуют с ограниченными ключевыми словами, квадратные скобки вокруг них вызывает Visual Basic, чтобы интерпретировать их как определенные вами элементы.</span><span class="sxs-lookup"><span data-stu-id="8519a-112">If these names conflict with restricted keywords, then placing square brackets around them causes Visual Basic to interpret them as your defined elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8519a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8519a-113">See Also</span></span>  
 [<span data-ttu-id="8519a-114">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8519a-114">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="8519a-115">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="8519a-115">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="8519a-116">Ключевые слова</span><span class="sxs-lookup"><span data-stu-id="8519a-116">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
