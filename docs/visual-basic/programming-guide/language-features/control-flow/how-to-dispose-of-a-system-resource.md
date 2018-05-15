---
title: Практическое руководство. Удаление системного ресурса (Visual Basic)
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
ms.openlocfilehash: cbb66934833da2bd6f0b797944dbb9c4df267cfc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-dispose-of-a-system-resource-visual-basic"></a><span data-ttu-id="cbc4e-102">Практическое руководство. Удаление системного ресурса (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbc4e-102">How to: Dispose of a System Resource (Visual Basic)</span></span>
<span data-ttu-id="cbc4e-103">Можно использовать `Using` блок, чтобы гарантировать, что система удаляет ресурс, когда код выходит из блока.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-103">You can use a `Using` block to guarantee that the system disposes of a resource when your code exits the block.</span></span> <span data-ttu-id="cbc4e-104">Это полезно, если вы используете системный ресурс, который потребляет большой объем памяти или другие компоненты также планируете использовать.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-104">This is useful if you are using a system resource that consumes a large amount of memory, or that other components also want to use.</span></span>  
  
### <a name="to-dispose-of-a-database-connection-when-your-code-is-finished-with-it"></a><span data-ttu-id="cbc4e-105">Чтобы освободить подключения к базе данных, когда она завершает ваш код</span><span class="sxs-lookup"><span data-stu-id="cbc4e-105">To dispose of a database connection when your code is finished with it</span></span>  
  
1.  <span data-ttu-id="cbc4e-106">Убедитесь, что включены соответствующие [оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для подключения к базе данных в начале файла исходного кода (в данном случае <xref:System.Data.SqlClient>).</span><span class="sxs-lookup"><span data-stu-id="cbc4e-106">Make sure you include the appropriate [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the database connection at the beginning of your source file (in this case, <xref:System.Data.SqlClient>).</span></span>  
  
2.  <span data-ttu-id="cbc4e-107">Создание `Using` блоке с `Using` и `End Using` инструкции.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-107">Create a `Using` block with the `Using` and `End Using` statements.</span></span> <span data-ttu-id="cbc4e-108">Внутри блока поместите код, который реагирует на подключение к базе данных.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-108">Inside the block, put the code that deals with the database connection.</span></span>  
  
3.  <span data-ttu-id="cbc4e-109">Объявите соединение и создайте его экземпляр как часть `Using` инструкции.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-109">Declare the connection and create an instance of it as part of the `Using` statement.</span></span>  
  
    ```  
    ' Insert the following line at the beginning of your source file.  
    Imports System.Data.SqlClient  
    Public Sub AccessSql(ByVal s As String)  
        Using sqc As New System.Data.SqlClient.SqlConnection(s)  
            MsgBox("Connected with string """ & sqc.ConnectionString & """")  
        End Using  
    End Sub  
    ```  
  
     <span data-ttu-id="cbc4e-110">Система удаляет ресурс независимо от способа выхода из блоков, включая регистр необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-110">The system disposes of the resource no matter how you exit the block, including the case of an unhandled exception.</span></span>  
  
     <span data-ttu-id="cbc4e-111">Обратите внимание, что не удается получить доступ к `sqc` из вне `Using` заблокировать, так как его область ограничена блока.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-111">Note that you cannot access `sqc` from outside the `Using` block, because its scope is limited to the block.</span></span>  
  
     <span data-ttu-id="cbc4e-112">Этот же способ можно использовать на системный ресурс, такие как дескриптор файла или оболочки COM.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-112">You can use this same technique on a system resource such as a file handle or a COM wrapper.</span></span> <span data-ttu-id="cbc4e-113">Вы используете `Using` заблокировать, если нужно чтобы оставить ресурс доступным для других компонентов после закрытия `Using` блока.</span><span class="sxs-lookup"><span data-stu-id="cbc4e-113">You use a `Using` block when you want to be sure to leave the resource available for other components after you have exited the `Using` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc4e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cbc4e-114">See Also</span></span>  
 <xref:System.Data.SqlClient.SqlConnection>  
 [<span data-ttu-id="cbc4e-115">Поток управления</span><span class="sxs-lookup"><span data-stu-id="cbc4e-115">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="cbc4e-116">Структуры решений</span><span class="sxs-lookup"><span data-stu-id="cbc4e-116">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="cbc4e-117">Циклические структуры</span><span class="sxs-lookup"><span data-stu-id="cbc4e-117">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="cbc4e-118">Другие структуры управления</span><span class="sxs-lookup"><span data-stu-id="cbc4e-118">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="cbc4e-119">Вложенные структуры управления</span><span class="sxs-lookup"><span data-stu-id="cbc4e-119">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [<span data-ttu-id="cbc4e-120">Оператор Using</span><span class="sxs-lookup"><span data-stu-id="cbc4e-120">Using Statement</span></span>](../../../../visual-basic/language-reference/statements/using-statement.md)
