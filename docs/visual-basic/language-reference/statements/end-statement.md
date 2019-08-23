---
title: Оператор End (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 9307cf10e6125441bd49baa0e663a5a13f234005
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944467"
---
# <a name="end-statement"></a><span data-ttu-id="6b8c3-102">Оператор End</span><span class="sxs-lookup"><span data-stu-id="6b8c3-102">End Statement</span></span>
<span data-ttu-id="6b8c3-103">Немедленно завершает выполнение.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b8c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b8c3-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="6b8c3-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b8c3-105">Remarks</span></span>  
 <span data-ttu-id="6b8c3-106">`End` Оператор можно разместить в любом месте процедуры, чтобы принудительно отменить выполнение всего приложения.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="6b8c3-107">`End`закрывает все файлы, открытые `Open` с помощью инструкции, и очищает все переменные приложения.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="6b8c3-108">Приложение закрывается, как только другие программы не содержат ссылки на свои объекты, и ни один из его кода не выполняется.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6b8c3-109">Инструкция останавливает выполнение кода внезапно и не `Dispose` вызывает метод или `Finalize` или любой другой Visual Basic код. `End`</span><span class="sxs-lookup"><span data-stu-id="6b8c3-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="6b8c3-110">Ссылки на объекты, удерживаемые другими программами, становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="6b8c3-111">Если оператор обнаруживается `Try` внутри блока или `Catch` , управление передается в соответствующий `Finally` блок. `End`</span><span class="sxs-lookup"><span data-stu-id="6b8c3-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="6b8c3-112">Инструкция приостанавливает выполнение, но в отличие от `End`этого она не закрывает никакие файлы и не очищает переменные, если она не обнаружена в скомпилированном исполняемом файле (exe). `Stop`</span><span class="sxs-lookup"><span data-stu-id="6b8c3-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="6b8c3-113">Поскольку `End` завершает работу приложения, не прибегая к открытым ресурсам, перед его использованием следует попытаться закрыться аккуратно.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="6b8c3-114">Например, если приложение имеет открытые формы, необходимо закрыть их, прежде чем управление достигнет `End` оператора.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="6b8c3-115">Следует использовать `End` с осторожностью и только тогда, когда необходимо немедленно приостанавливаться.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="6b8c3-116">Обычные способы завершения процедуры ([инструкция return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрывают процедуру, но и выдают вызывающему коду возможность аккуратно закрыться.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="6b8c3-117">Например, консольное приложение может просто `Return` `Main` выполнить процедуру.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6b8c3-118">`End` Оператор<xref:System.Environment.Exit%2A> вызывает метод<xref:System.Environment> класса в<xref:System> пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="6b8c3-119"><xref:System.Environment.Exit%2A>требует наличия `UnmanagedCode` разрешений.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="6b8c3-120">В <xref:System.Security.SecurityException> противном случае возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="6b8c3-121">Если за ним следует дополнительное ключевое слово, [оператор End \<ключевое_слово >](../../../visual-basic/language-reference/statements/end-keyword-statement.md) выделяют конец определения соответствующей процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="6b8c3-122">Например, `End Function` завершает определение `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b8c3-123">Пример</span><span class="sxs-lookup"><span data-stu-id="6b8c3-123">Example</span></span>  
 <span data-ttu-id="6b8c3-124">В следующем примере `End` оператор используется для завершения выполнения кода, если пользователь запрашивает его.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="6b8c3-125">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="6b8c3-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="6b8c3-126">Эта инструкция не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6b8c3-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8c3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6b8c3-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="6b8c3-128">Оператор Stop</span><span class="sxs-lookup"><span data-stu-id="6b8c3-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="6b8c3-129">End \<ключевое слово > оператор</span><span class="sxs-lookup"><span data-stu-id="6b8c3-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
