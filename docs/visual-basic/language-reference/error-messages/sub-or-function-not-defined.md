---
title: Sub или Function не определена (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 58e90d769d5a7f2d88b5c27d1ec7d0d28c8d7b03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="175eb-102">Sub или Function не определена (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="175eb-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="175eb-103">Объект `Sub` или `Function` должен быть определен для вызываться.</span><span class="sxs-lookup"><span data-stu-id="175eb-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="175eb-104">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="175eb-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="175eb-105">Ошибка в написании имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="175eb-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="175eb-106">Попытка вызова процедуры из другого проекта без явного добавления ссылки на этот проект в **ссылки** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="175eb-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="175eb-107">Задание процедуры, которая не видна в вызывающую процедуру.</span><span class="sxs-lookup"><span data-stu-id="175eb-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="175eb-108">Объявление процедуры библиотеки динамической компоновки (DLL) для Windows или Macintosh ресурс кода подпрограмму, которая не находится в указанный ресурс библиотеки или кода.</span><span class="sxs-lookup"><span data-stu-id="175eb-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="175eb-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="175eb-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="175eb-110">Проверьте правильность написания имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="175eb-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="175eb-111">Найдите имя проекта, содержащего процедуру, которую требуется вызывать в **ссылки** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="175eb-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="175eb-112">Если он не отображается, нажмите кнопку **Обзор** кнопку, чтобы найти его.</span><span class="sxs-lookup"><span data-stu-id="175eb-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="175eb-113">Установите флажок слева от имени проекта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="175eb-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="175eb-114">Проверьте имя подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="175eb-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="175eb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="175eb-115">See Also</span></span>  
 [<span data-ttu-id="175eb-116">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="175eb-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="175eb-117">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="175eb-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="175eb-118">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="175eb-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="175eb-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="175eb-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
