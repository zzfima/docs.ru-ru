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
ms.openlocfilehash: 84ac57bf1bcf60664e2b18fed16a3bbe6c03dc68
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2018
ms.locfileid: "42755012"
---
# <a name="performing-tasks-with-myapplication-mycomputer-and-myuser-visual-basic"></a><span data-ttu-id="030b0-102">Выполнение задач с My.Application, My.Computer и My.User (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="030b0-102">Performing Tasks with My.Application, My.Computer, and My.User (Visual Basic)</span></span>
<span data-ttu-id="030b0-103">Трех центральных `My` являются объекты, которые предоставляют доступ к информации и часто используемым функциям `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), и `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span><span class="sxs-lookup"><span data-stu-id="030b0-103">The three central `My` objects that provide access to information and commonly used functionality are `My.Application` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>), `My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>), and `My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>).</span></span> <span data-ttu-id="030b0-104">Эти объекты можно использовать для доступа к информации, который связан с текущего приложения, к которым приложение устанавливается на или текущего пользователя приложения, соответственно.</span><span class="sxs-lookup"><span data-stu-id="030b0-104">You can use these objects to access information that is related to the current application, the computer that the application is installed on, or the current user of the application, respectively.</span></span>  
  
## <a name="myapplication-mycomputer-and-myuser"></a><span data-ttu-id="030b0-105">My.Application, My.Computer и My.User</span><span class="sxs-lookup"><span data-stu-id="030b0-105">My.Application, My.Computer, and My.User</span></span>  
 <span data-ttu-id="030b0-106">В следующих примерах показано, как сведения можно получить с помощью `My`.</span><span class="sxs-lookup"><span data-stu-id="030b0-106">The following examples demonstrate how information can be retrieved using `My`.</span></span>  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_2.vb)]  
  
 <span data-ttu-id="030b0-107">В дополнение к сведениям, члены, доступные через эти три объекта также позволяют выполнять методы, связанные с этим объектом.</span><span class="sxs-lookup"><span data-stu-id="030b0-107">In addition to retrieving information, the members exposed through these three objects also allow you to execute methods related to that object.</span></span> <span data-ttu-id="030b0-108">К примеру, доступны разнообразные методы для управления файлами и обновить реестр через `My.Computer`.</span><span class="sxs-lookup"><span data-stu-id="030b0-108">For instance, you can access a variety of methods to manipulate files or update the registry through `My.Computer`.</span></span>  
  
 <span data-ttu-id="030b0-109">Файлового ввода-вывода значительно проще и быстрее с помощью `My`, который включает широкий набор методов и свойств для операции с файлами, каталогами и дисков.</span><span class="sxs-lookup"><span data-stu-id="030b0-109">File I/O is significantly easier and faster with `My`, which includes a variety of methods and properties for manipulating files, directories, and drives.</span></span> <span data-ttu-id="030b0-110"><xref:Microsoft.VisualBasic.FileIO.TextFieldParser> Объекта позволяет считывать из больших структурированных файлов с разделителями или поля фиксированной ширины.</span><span class="sxs-lookup"><span data-stu-id="030b0-110">The <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> object allows you to read from large structured files that have delimited or fixed-width fields.</span></span> <span data-ttu-id="030b0-111">В этом примере открывается `TextFieldParser` `reader` и использует его для чтения из `C:\TestFolder1\test1.txt`.</span><span class="sxs-lookup"><span data-stu-id="030b0-111">This example opens the `TextFieldParser` `reader` and uses it to read from `C:\TestFolder1\test1.txt`.</span></span>  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_3.vb)]  
  
 <span data-ttu-id="030b0-112">`My.Application` позволяет изменить язык и региональные параметры для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="030b0-112">`My.Application` allows you to change the culture for your application.</span></span> <span data-ttu-id="030b0-113">В следующем примере показано, как можно вызвать этот метод.</span><span class="sxs-lookup"><span data-stu-id="030b0-113">The following example demonstrates how this method can be called.</span></span>  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/performing-tasks-with-my-application-my-computer-and-my-user_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="030b0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="030b0-114">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="030b0-115">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="030b0-115">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
