---
title: Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application object [Visual Basic], developing applications
- rapid application development (RAD), My.Application
- rapid application development (RAD), My.Computer
- rapid application development (RAD), My.User
- My.Computer object [Visual Basic], developing applications
- My.User object [Visual Basic], developing applications
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
ms.openlocfilehash: bc2b0521598c00cdb398d936d61d65874a9cf274
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="666fc-102">Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="666fc-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="666fc-103">Три центральных `My` являются объекты, которые предоставляют доступ к информации и часто используемым функциям `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), и `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="666fc-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="666fc-104">Эти объекты можно использовать для доступа к информации, связанной с текущего приложения, установленного приложения на компьютере или текущего пользователя или приложения, соответственно.</span><span class="sxs-lookup"><span data-stu-id="666fc-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="666fc-105">My.Application, My.Computer и My.User</span><span class="sxs-lookup"><span data-stu-id="666fc-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="666fc-106">В следующих примерах демонстрируется, каким образом данные можно получить с помощью `My`.</span><span class="sxs-lookup"><span data-stu-id="666fc-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 <span data-ttu-id="666fc-107">В дополнение к сведениям, члены, доступные через эти три объекта также позволяют выполнять методы, связанные с этим объектом.</span><span class="sxs-lookup"><span data-stu-id="666fc-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="666fc-108">Например, доступ к различные методы для управления файлами и редактирования реестра через `My.Computer`.</span><span class="sxs-lookup"><span data-stu-id="666fc-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="666fc-109">Файловый ввод-вывод выполняется значительно проще и быстрее при использовании `My`, которая содержит разнообразные методы и свойства для управления файлы, папки и диски.</span><span class="sxs-lookup"><span data-stu-id="666fc-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="666fc-110"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Объектов позволяет считывать из больших структурированных файлов с разделителями или поля фиксированной ширины.</span><span class="sxs-lookup"><span data-stu-id="666fc-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="666fc-111">В этом примере открывается `TextFieldParser``reader` и использует его для чтения из `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="666fc-111">This example opens the `TextFieldParser``reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 <span data-ttu-id="666fc-112">`My.Application` позволяет изменять язык и региональные параметры для приложения.</span><span class="sxs-lookup"><span data-stu-id="666fc-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="666fc-113">В следующем примере показано, как можно вызвать этот метод.</span><span class="sxs-lookup"><span data-stu-id="666fc-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="666fc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="666fc-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="666fc-115">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="666fc-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
