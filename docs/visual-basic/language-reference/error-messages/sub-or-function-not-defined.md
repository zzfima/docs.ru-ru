---
title: "Sub или Function не определена (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID35
dev_langs:
- VB
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 837beec039e1fb8f8a796b2781d93de6d4cfb33a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="sub-or-function-not-defined-visual-basic"></a><span data-ttu-id="4f06b-102">Sub или Function не определена (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f06b-102">Sub or Function not defined (Visual Basic)</span></span>
<span data-ttu-id="4f06b-103">Объект `Sub` или `Function` должны быть определены для вызываться.</span><span class="sxs-lookup"><span data-stu-id="4f06b-103">A `Sub` or `Function` must be defined in order to be called.</span></span> <span data-ttu-id="4f06b-104">Возможные причины этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="4f06b-104">Possible causes of this error include:</span></span>  
  
-   <span data-ttu-id="4f06b-105">Неправильное написание имени процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f06b-105">Misspelling the procedure name.</span></span>  
  
-   <span data-ttu-id="4f06b-106">Попытка вызова процедуры из другого проекта без явного добавления ссылки на этот проект в **ссылки** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="4f06b-106">Trying to call a procedure from another project without explicitly adding a reference to that project in the **References** dialog box.</span></span>  
  
-   <span data-ttu-id="4f06b-107">Задание процедуры, которая невидима для вызывающей процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f06b-107">Specifying a procedure that is not visible to the calling procedure.</span></span>  
  
-   <span data-ttu-id="4f06b-108">Объявление подпрограммы Windows библиотеки динамической компоновки (DLL) или процедуры из источника кода Macintosh, которого нет в указанной библиотеке или источнике кода.</span><span class="sxs-lookup"><span data-stu-id="4f06b-108">Declaring a Windows dynamic-link library (DLL) routine or Macintosh code-resource routine that is not in the specified library or code resource.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4f06b-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4f06b-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="4f06b-110">Убедитесь, что имя процедуры указано правильно.</span><span class="sxs-lookup"><span data-stu-id="4f06b-110">Make sure that the procedure name is spelled correctly.</span></span>  
  
2.  <span data-ttu-id="4f06b-111">Найдите имя проекта, содержащего процедуру, которую требуется вызывать в **ссылки** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="4f06b-111">Find the name of the project containing the procedure you want to call in the **References** dialog box.</span></span> <span data-ttu-id="4f06b-112">Если не отображается, нажмите кнопку **Обзор** кнопку, чтобы найти его.</span><span class="sxs-lookup"><span data-stu-id="4f06b-112">If it does not appear, click the **Browse** button to search for it.</span></span> <span data-ttu-id="4f06b-113">Установите флажок слева от имени проекта и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4f06b-113">Select the check box to the left of the project name, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="4f06b-114">Проверьте имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="4f06b-114">Check the name of the routine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f06b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4f06b-115">See Also</span></span>  
 <span data-ttu-id="4f06b-116">[Типы ошибок](../../../visual-basic/programming-guide/language-features/error-types.md) </span><span class="sxs-lookup"><span data-stu-id="4f06b-116">[Error Types](../../../visual-basic/programming-guide/language-features/error-types.md) </span></span>  
<span data-ttu-id="4f06b-117"> [Управление ссылками проекта](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="4f06b-117"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="4f06b-118"> [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4f06b-118"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="4f06b-119"> [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)</span><span class="sxs-lookup"><span data-stu-id="4f06b-119"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)</span></span>
