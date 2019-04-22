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
ms.openlocfilehash: 4fc4fd36fb6b057195e9d8a79eb0a5b3ac9ff95c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832025"
---
# <a name="end-statement"></a><span data-ttu-id="76218-102">Оператор End</span><span class="sxs-lookup"><span data-stu-id="76218-102">End Statement</span></span>
<span data-ttu-id="76218-103">Немедленно прекращает выполнение.</span><span class="sxs-lookup"><span data-stu-id="76218-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76218-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76218-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="76218-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="76218-105">Remarks</span></span>  
 <span data-ttu-id="76218-106">Вы можете поместить `End` инструкции в любом месте процедуры, чтобы принудительно остановить работу всего приложения.</span><span class="sxs-lookup"><span data-stu-id="76218-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="76218-107">`End` Закрывает все файлы, открытые с `Open` инструкции и очищает все переменные приложения.</span><span class="sxs-lookup"><span data-stu-id="76218-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="76218-108">Приложение закрывается сразу нет других программ, поддерживающих ссылки на его объекты и выполняется код.</span><span class="sxs-lookup"><span data-stu-id="76218-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76218-109">`End` Инструкция немедленно прерывается выполнение кода и не вызывает `Dispose` или `Finalize` метода или любого другого кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="76218-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="76218-110">Ссылки на объекты, хранящиеся в других программах, становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="76218-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="76218-111">Если `End` встречается в `Try` или `Catch` блок, элемент управления не проходит в соответствующий `Finally` блока.</span><span class="sxs-lookup"><span data-stu-id="76218-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="76218-112">`Stop` Инструкция приостанавливает выполнение, но в отличие от `End`, закройте все файлы или не удаляет переменные, в том случае, если только встречается в файле скомпилированный исполняемый файл (.exe).</span><span class="sxs-lookup"><span data-stu-id="76218-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="76218-113">Так как `End` завершает работу приложения, не обращая внимания к любым ресурсам, которые могут быть открыты, следует попытаться закрытием аккуратно, перед его использованием.</span><span class="sxs-lookup"><span data-stu-id="76218-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="76218-114">Например, если приложение содержит открытые формы, их следует закрыть перед управления достигает `End` инструкции.</span><span class="sxs-lookup"><span data-stu-id="76218-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="76218-115">Следует использовать `End` только в случае необходимости и только при необходимости для немедленной остановки.</span><span class="sxs-lookup"><span data-stu-id="76218-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="76218-116">Обычным способом, чтобы завершить процедуру ([оператор Return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрыть процедуру, но также дают возможность закрытия аккуратно вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="76218-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="76218-117">В консольном приложении, например, можно просто `Return` из `Main` процедуры.</span><span class="sxs-lookup"><span data-stu-id="76218-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="76218-118">`End` Инструкция вызывает <xref:System.Environment.Exit%2A> метод <xref:System.Environment> в класс <xref:System> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="76218-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="76218-119"><xref:System.Environment.Exit%2A> необходимо иметь `UnmanagedCode` разрешение.</span><span class="sxs-lookup"><span data-stu-id="76218-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="76218-120">Если вы этого не сделать, <xref:System.Security.SecurityException> возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="76218-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="76218-121">Если за ним дополнительных ключевых слов, следует [окончания \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md) отделяет конец определения соответствующей процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="76218-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="76218-122">Например `End Function` завершает определение `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="76218-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76218-123">Пример</span><span class="sxs-lookup"><span data-stu-id="76218-123">Example</span></span>  
 <span data-ttu-id="76218-124">В следующем примере используется `End` инструкции для завершения выполнения кода в том случае, если пользователь запрашивает его.</span><span class="sxs-lookup"><span data-stu-id="76218-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="76218-125">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="76218-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="76218-126">Эта инструкция не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="76218-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76218-127">См. также</span><span class="sxs-lookup"><span data-stu-id="76218-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="76218-128">Оператор Stop</span><span class="sxs-lookup"><span data-stu-id="76218-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="76218-129">Конец \<ключевое слово > инструкции</span><span class="sxs-lookup"><span data-stu-id="76218-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
