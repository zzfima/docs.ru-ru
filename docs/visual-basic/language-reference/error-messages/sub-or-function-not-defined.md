---
title: Sub или Function не определена (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 397648618ea3764efafb5cff41deaef320bbeff3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59294682"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="d0fdf-102">Sub или Function не определена (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0fdf-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="d0fdf-103">Объект `Sub` или `Function` должны быть определены для вызываться.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="d0fdf-104">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="d0fdf-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="d0fdf-105">Неправильное написание имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="d0fdf-106">Попытка вызова процедуры из другого проекта без явного добавления ссылки на этот проект в **ссылки** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="d0fdf-107">Задание процедуры, которая не отображается в вызывающую процедуру.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="d0fdf-108">Объявление процедуры библиотеки динамической компоновки (DLL) для Windows или Macintosh ресурс кода подпрограмму, которая не находится в указанный ресурс библиотеки или кода.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0fdf-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d0fdf-109">To correct this error</span></span>  
  
1. <span data-ttu-id="d0fdf-110">Убедитесь, что имя процедуры указано правильно.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2. <span data-ttu-id="d0fdf-111">Найдите имя проекта, содержащего процедуру, которую требуется вызывать в **ссылки** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="d0fdf-112">Если он не отображается, нажмите кнопку **Обзор** кнопку, чтобы найти его.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="d0fdf-113">Установите флажок слева от имени проекта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="d0fdf-114">Проверьте имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="d0fdf-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0fdf-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d0fdf-115">See also</span></span>

- [<span data-ttu-id="d0fdf-116">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="d0fdf-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="d0fdf-117">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="d0fdf-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="d0fdf-118">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="d0fdf-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d0fdf-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="d0fdf-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
