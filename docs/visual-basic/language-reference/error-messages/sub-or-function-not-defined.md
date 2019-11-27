---
title: Подпрограмма или функция не определена
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 8b81460eccb6be8baa2ea7bc68d0f80c9d16398e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349580"
---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="2e4d1-102">Sub или Function не определена (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e4d1-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="2e4d1-103">Для вызова необходимо определить `Sub` или `Function`.</span><span class="sxs-lookup"><span data-stu-id="2e4d1-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="2e4d1-104">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="2e4d1-104">Possible causes of this error include:</span></span>  
  
- <span data-ttu-id="2e4d1-105">Ошибка написания имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="2e4d1-105">Misspelling the procedure name.</span></span>  
  
- <span data-ttu-id="2e4d1-106">Попытка вызвать процедуру из другого проекта без явного добавления ссылки на этот проект в диалоговом окне " **ссылки** ".</span><span class="sxs-lookup"><span data-stu-id="2e4d1-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
- <span data-ttu-id="2e4d1-107">Указание процедуры, которая не является видимой для вызывающей процедуры.</span><span class="sxs-lookup"><span data-stu-id="2e4d1-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
- <span data-ttu-id="2e4d1-108">Объявление подпрограммы библиотеки динамической компоновки Windows (DLL) или служебной программы-ресурса для Macintosh, которая не находится в указанной библиотеке или ресурсе кода.</span><span class="sxs-lookup"><span data-stu-id="2e4d1-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2e4d1-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2e4d1-109">To correct this error</span></span>  
  
1. <span data-ttu-id="2e4d1-110">Убедитесь, что имя процедуры написано правильно.</span><span class="sxs-lookup"><span data-stu-id="2e4d1-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2. <span data-ttu-id="2e4d1-111">Найдите имя проекта, содержащего процедуру, которую необходимо вызвать, в диалоговом окне **ссылки** .</span><span class="sxs-lookup"><span data-stu-id="2e4d1-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="2e4d1-112">Если она не отображается, нажмите кнопку **Обзор** , чтобы найти ее.</span><span class="sxs-lookup"><span data-stu-id="2e4d1-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="2e4d1-113">Установите флажок слева от имени проекта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2e4d1-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="2e4d1-114">Проверьте имя подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="2e4d1-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e4d1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2e4d1-115">See also</span></span>

- [<span data-ttu-id="2e4d1-116">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="2e4d1-116">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
- [<span data-ttu-id="2e4d1-117">Управление ссылками в проекте</span><span class="sxs-lookup"><span data-stu-id="2e4d1-117">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="2e4d1-118">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="2e4d1-118">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="2e4d1-119">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="2e4d1-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
