---
title: "Функция &quot;&lt;procedurename&gt;&quot; возвращает значение не для всех путей кода | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
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
ms.openlocfilehash: cec047644bfbf82c5c3c206b23af6b0fc37f834d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="6f3f4-102">Функция "&lt;procedurename&gt;" возвращает значение не для всех путей кода</span><span class="sxs-lookup"><span data-stu-id="6f3f4-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="6f3f4-103">Функция "\<procedurename настроек" возвращает значение не для всех ветвей кода.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="6f3f4-104">Отсутствует оператор «Return»?</span><span class="sxs-lookup"><span data-stu-id="6f3f4-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="6f3f4-105">A `Function` процедура имеет хотя бы один возможный путь во всем коде, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="6f3f4-106">Может возвращать значение из `Function` процедура в любой из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="6f3f4-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="6f3f4-107">Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6f3f4-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="6f3f4-108">Присвойте значение `Function` процедуры имя, а затем выполнить `Exit Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="6f3f4-109">Присвойте значение `Function` процедуры имя, а затем выполнить `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="6f3f4-110">Если управление передается `Exit Function` или `End Function` и не были назначены любое значение имени процедуры, процедура возвращает значение по умолчанию типа возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="6f3f4-111">Дополнительные сведения см. в разделе «Поведение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6f3f4-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="6f3f4-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-112">By default, this message is a warning.</span></span> <span data-ttu-id="6f3f4-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6f3f4-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="6f3f4-114">**Идентификатор ошибки:** BC42105</span><span class="sxs-lookup"><span data-stu-id="6f3f4-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f3f4-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6f3f4-115">To correct this error</span></span>  
  
-   <span data-ttu-id="6f3f4-116">Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждым оператором, вызывающим возврат.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="6f3f4-117">Проще гарантировать, что каждое возвращение из процедуры возвращает значение, если всегда использовать `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="6f3f4-118">После этого, последним оператором перед `End Function` должно быть `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="6f3f4-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f3f4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6f3f4-119">See Also</span></span>  
 <span data-ttu-id="6f3f4-120">[Процедуры функций](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="6f3f4-120">[Function Procedures](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) </span></span>  
<span data-ttu-id="6f3f4-121"> [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="6f3f4-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="6f3f4-122"> [Страница "Компиляция" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="6f3f4-122"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)</span></span>
