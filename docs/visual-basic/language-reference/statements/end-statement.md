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
ms.openlocfilehash: cb2fb4abb21b7b9c6575cec4aca1374f63687607
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343726"
---
# <a name="end-statement"></a><span data-ttu-id="16072-102">Оператор End</span><span class="sxs-lookup"><span data-stu-id="16072-102">End Statement</span></span>
<span data-ttu-id="16072-103">Немедленно завершает выполнение.</span><span class="sxs-lookup"><span data-stu-id="16072-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16072-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16072-104">Syntax</span></span>  
  
```vb  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="16072-105">Заметки</span><span class="sxs-lookup"><span data-stu-id="16072-105">Remarks</span></span>  
 <span data-ttu-id="16072-106">Можно поместить оператор `End` в любую процедуру, чтобы принудительно отменить выполнение всего приложения.</span><span class="sxs-lookup"><span data-stu-id="16072-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="16072-107">`End` закрывает все файлы, открытые с помощью инструкции `Open`, и очищает все переменные приложения.</span><span class="sxs-lookup"><span data-stu-id="16072-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="16072-108">Приложение закрывается, как только другие программы не содержат ссылки на свои объекты, и ни один из его кода не выполняется.</span><span class="sxs-lookup"><span data-stu-id="16072-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16072-109">Оператор `End` неожиданно останавливает выполнение кода и не вызывает метод `Dispose` или `Finalize` или любой другой код Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="16072-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="16072-110">Ссылки на объекты, удерживаемые другими программами, становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="16072-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="16072-111">Если в блоке `Try` или `Catch` обнаруживается оператор `End`, управление не передается соответствующему блоку `Finally`.</span><span class="sxs-lookup"><span data-stu-id="16072-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="16072-112">Инструкция `Stop` приостанавливает выполнение, но в отличие от `End`, она не закрывает никакие файлы и не очищает переменные, если только она не обнаружена в скомпилированном исполняемом файле (exe).</span><span class="sxs-lookup"><span data-stu-id="16072-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="16072-113">Поскольку `End` прекращает работу приложения, не прибегая к каким-либо ресурсам, которые могут быть открыты, следует сначала попытаться закрыть его перед использованием.</span><span class="sxs-lookup"><span data-stu-id="16072-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="16072-114">Например, если приложение имеет открытые формы, необходимо закрыть их, прежде чем управление достигнет оператора `End`.</span><span class="sxs-lookup"><span data-stu-id="16072-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="16072-115">Следует использовать `End` с осторожностью и только тогда, когда необходимо немедленно останавливаться.</span><span class="sxs-lookup"><span data-stu-id="16072-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="16072-116">Обычные способы завершения процедуры ([инструкция return](../../../visual-basic/language-reference/statements/return-statement.md) и [оператор Exit](../../../visual-basic/language-reference/statements/exit-statement.md)) не только аккуратно закрывают процедуру, но и выдают вызывающему коду возможность аккуратно закрыться.</span><span class="sxs-lookup"><span data-stu-id="16072-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="16072-117">Например, консольное приложение может просто `Return` из процедуры `Main`.</span><span class="sxs-lookup"><span data-stu-id="16072-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="16072-118">Оператор `End` вызывает метод <xref:System.Environment.Exit%2A> класса <xref:System.Environment> в пространстве имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="16072-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="16072-119"><xref:System.Environment.Exit%2A> требуется разрешение `UnmanagedCode`.</span><span class="sxs-lookup"><span data-stu-id="16072-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="16072-120">В противном случае возникает ошибка <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="16072-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="16072-121">Если за ним следует дополнительное ключевое слово, [оператор end \<ключевое слово >](../../../visual-basic/language-reference/statements/end-keyword-statement.md) выделяют конец определения соответствующей процедуры или блока.</span><span class="sxs-lookup"><span data-stu-id="16072-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="16072-122">Например, `End Function` завершает определение `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="16072-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16072-123">Пример</span><span class="sxs-lookup"><span data-stu-id="16072-123">Example</span></span>  
 <span data-ttu-id="16072-124">В следующем примере оператор `End` используется для завершения выполнения кода, если пользователь запрашивает его.</span><span class="sxs-lookup"><span data-stu-id="16072-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="16072-125">Примечания для разработчиков смарт-устройств</span><span class="sxs-lookup"><span data-stu-id="16072-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="16072-126">Эта инструкция не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="16072-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16072-127">См. также</span><span class="sxs-lookup"><span data-stu-id="16072-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="16072-128">Оператор Stop</span><span class="sxs-lookup"><span data-stu-id="16072-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="16072-129">End \<ключевое слово ></span><span class="sxs-lookup"><span data-stu-id="16072-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
