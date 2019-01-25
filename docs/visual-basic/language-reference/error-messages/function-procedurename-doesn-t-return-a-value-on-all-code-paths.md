---
title: Функция &#39; &lt;имя_процедуры&gt; &#39; &#39;t возвращает значение на всех путях кода
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: b6cc5143aafb6c2554b183a1fc5fb3b1331ec5d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552194"
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="4cb9f-102">Функция &#39; &lt;имя_процедуры&gt; &#39; &#39;t возвращает значение на всех путях кода</span><span class="sxs-lookup"><span data-stu-id="4cb9f-102">Function &#39;&lt;procedurename&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="4cb9f-103">Функция "\<имя_процедуры >" не возвращает значение на всех путях кода.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-103">Function '\<procedurename>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="4cb9f-104">Возможно, отсутствует оператор «Return»?</span><span class="sxs-lookup"><span data-stu-id="4cb9f-104">Are you missing a 'Return' statement?</span></span>  
  
 <span data-ttu-id="4cb9f-105">Объект `Function` процедура имеет по крайней мере один возможный путь во всем коде, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-105">A `Function` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="4cb9f-106">Может возвращать значение из `Function` процедуры в любой из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="4cb9f-106">You can return a value from a `Function` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="4cb9f-107">Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4cb9f-107">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
-   <span data-ttu-id="4cb9f-108">Присвойте значение `Function` процедуры имя, а затем выполнить `Exit Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-108">Assign the value to the `Function` procedure name and then perform an `Exit Function` statement.</span></span>  
  
-   <span data-ttu-id="4cb9f-109">Присвойте значение `Function` процедуры имя, а затем выполнить `End Function` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-109">Assign the value to the `Function` procedure name and then perform the `End Function` statement.</span></span>  
  
 <span data-ttu-id="4cb9f-110">Если управление передается `Exit Function` или `End Function` и которые не были назначены любое значение для имени процедуры, процедура возвращает значение по умолчанию тип возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-110">If control passes to `Exit Function` or `End Function` and you have not assigned any value to the procedure name, the procedure returns the default value of the return data type.</span></span> <span data-ttu-id="4cb9f-111">Дополнительные сведения см. в разделе «Поведение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4cb9f-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="4cb9f-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-112">By default, this message is a warning.</span></span> <span data-ttu-id="4cb9f-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4cb9f-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="4cb9f-114">**Идентификатор ошибки:** BC42105</span><span class="sxs-lookup"><span data-stu-id="4cb9f-114">**Error ID:** BC42105</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4cb9f-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4cb9f-115">To correct this error</span></span>  
  
-   <span data-ttu-id="4cb9f-116">Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждой инструкции, которая вызывает возврат.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="4cb9f-117">Проще гарантировать, что каждое возвращение из процедуры возвращает значение, если всегда использовать `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="4cb9f-118">После этого, последней инструкцией перед `End Function` должно быть `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4cb9f-118">If you do this, the last statement before `End Function` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb9f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4cb9f-119">See also</span></span>
- [<span data-ttu-id="4cb9f-120">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="4cb9f-120">Function Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [<span data-ttu-id="4cb9f-121">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="4cb9f-121">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="4cb9f-122">Страница "Компиляция" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4cb9f-122">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
