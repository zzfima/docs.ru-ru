---
title: Практическое руководство. Удаление системного ресурса
ms.date: 07/20/2015
helpviewer_keywords:
- Using statement [Visual Basic], disposing of system resources
- Visual Basic code, control flow
- system resources, disposing of
- resources [Visual Basic], disposing of system
- system resources
- Using statement [Visual Basic], Using...End Using
- Using block
ms.assetid: 8be2b239-8090-419b-8e7e-bcaa75b0ecc8
ms.openlocfilehash: c493051050442597196ba484fb9ce8e99249dbb7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353946"
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="ec4ef-102">Практическое руководство. Удаление системного ресурса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ec4ef-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="ec4ef-103">Можно использовать блок `Using`, чтобы гарантировать, что система удаляет ресурс, когда код выходит из блока.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="ec4ef-104">Это полезно, если вы используете системный ресурс, который потребляет большой объем памяти или что другие компоненты также хотят использовать.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="ec4ef-105">Удаление подключения к базе данных после завершения работы с ним кода</span><span class="sxs-lookup"><span data-stu-id="ec4ef-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1. <span data-ttu-id="ec4ef-106">Убедитесь, что вы включили соответствующий [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для подключения к базе данных в начале исходного файла (в данном случае <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="ec4ef-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2. <span data-ttu-id="ec4ef-107">Создайте блок `Using` с инструкциями `Using` и `End Using`.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="ec4ef-108">Внутри блока разместите код, который работает с подключением к базе данных.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3. <span data-ttu-id="ec4ef-109">Объявите соединение и создайте его экземпляр в составе оператора `Using`.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```vb  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="ec4ef-110">Система уничтожает ресурс независимо от того, как вы выйдете из блока, включая случай необработанного исключения.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="ec4ef-111">Обратите внимание, что доступ к `sqc` извне блока `Using` невозможен, так как его область ограничена блоком.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="ec4ef-112">Эту же методику можно использовать для системных ресурсов, таких как файловый обработчик или оболочка COM.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="ec4ef-113">Используйте блок `Using`, если вы хотите оставить ресурс доступным для других компонентов после выхода из блока `Using`.</span><span class="sxs-lookup"><span data-stu-id="ec4ef-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec4ef-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ec4ef-114">See also</span></span>

- <xref:System.Data.SqlClient.SqlConnection>
- [<span data-ttu-id="ec4ef-115">Поток управления</span><span class="sxs-lookup"><span data-stu-id="ec4ef-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="ec4ef-116">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="ec4ef-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="ec4ef-117">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="ec4ef-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="ec4ef-118">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="ec4ef-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="ec4ef-119">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="ec4ef-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="ec4ef-120">Оператор Using</span><span class="sxs-lookup"><span data-stu-id="ec4ef-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
