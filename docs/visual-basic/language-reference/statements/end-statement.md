---
title: Оператор End
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
ms.openlocfilehash: 864ac5ef1713f8ffa93c18accede8ecd5b3b7a8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604436"
---
# <a name="end-statement"></a><span data-ttu-id="c5c62-102">Оператор End</span><span class="sxs-lookup"><span data-stu-id="c5c62-102">End Statement</span></span>
<span data-ttu-id="c5c62-103">Немедленно прекращает выполнение.</span><span class="sxs-lookup"><span data-stu-id="c5c62-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5c62-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5c62-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="c5c62-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5c62-105">Remarks</span></span>  
 <span data-ttu-id="c5c62-106">Можно поместить `End` инструкции в любом месте процедуры для принудительного завершения работы всего приложения.</span><span class="sxs-lookup"><span data-stu-id="c5c62-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="c5c62-107">`End` Закрывает все файлы, открытые с `Open` инструкции и очищает все переменные приложения.</span><span class="sxs-lookup"><span data-stu-id="c5c62-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="c5c62-108">Приложение закрывается сразу нет других программ, поддерживающих ссылки на его объекты, и его код не выполняются.</span><span class="sxs-lookup"><span data-stu-id="c5c62-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5c62-109">`End` Инструкция немедленно прекращает выполнение кода и не вызывает `Dispose` или `Finalize` метода или любого другого кода в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c5c62-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="c5c62-110">Ссылки на объекты, хранящиеся в других программах, становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="c5c62-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="c5c62-111">Если `End` встречается в `Try` или `Catch` в соответствующий блок управления не проходит `Finally` блока.</span><span class="sxs-lookup"><span data-stu-id="c5c62-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="c5c62-112">`Stop` Оператор приостанавливает выполнение, но в отличие от `End`, не закрывает файлы и не удаляет переменные, если только встречается в компилируемый исполняемый файл (.exe) файл.</span><span class="sxs-lookup"><span data-stu-id="c5c62-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="c5c62-113">Поскольку `End` завершает приложение, не обращая внимания к ресурсам, которые могут быть открыты, следует попытаться закрытия без ошибок, перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="c5c62-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="c5c62-114">Например, если приложение имеет открытые формы, их следует закрыть перед управления достигает `End` инструкции.</span><span class="sxs-lookup"><span data-stu-id="c5c62-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="c5c62-115">Следует использовать `End` только в случае необходимости и только при необходимости для немедленной остановки.</span><span class="sxs-lookup"><span data-stu-id="c5c62-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="c5c62-116">Обычным способом, чтобы завершить процедуру ([оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрыть процедуры, но также предоставить возможность закрытия аккуратно вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="c5c62-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="c5c62-117">В консольном приложении, например, можно просто `Return` из `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="c5c62-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c5c62-118">`End` Инструкция вызывает <xref:System.Environment.Exit%2A> метод <xref:System.Environment> класса в <xref:System> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c5c62-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="c5c62-119"><xref:System.Environment.Exit%2A> требует наличия `UnmanagedCode` разрешение.</span><span class="sxs-lookup"><span data-stu-id="c5c62-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="c5c62-120">Если нет, <xref:System.Security.SecurityException> возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="c5c62-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="c5c62-121">Если за ним следует дополнительных ключевых слов, [окончания \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) отделяет конец определения соответствующей процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="c5c62-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="c5c62-122">Например `End Function` завершает определение `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="c5c62-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5c62-123">Пример</span><span class="sxs-lookup"><span data-stu-id="c5c62-123">Example</span></span>  
 <span data-ttu-id="c5c62-124">В следующем примере используется `End` инструкции для завершения выполнения по требованию пользователя.</span><span class="sxs-lookup"><span data-stu-id="c5c62-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="c5c62-125">Примечания для разработчиков интеллектуальных устройств</span><span class="sxs-lookup"><span data-stu-id="c5c62-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="c5c62-126">Эта инструкция не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="c5c62-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5c62-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c5c62-127">See Also</span></span>  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [<span data-ttu-id="c5c62-128">Оператор Stop</span><span class="sxs-lookup"><span data-stu-id="c5c62-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [<span data-ttu-id="c5c62-129">Конец \<ключевое слово > инструкции</span><span class="sxs-lookup"><span data-stu-id="c5c62-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
