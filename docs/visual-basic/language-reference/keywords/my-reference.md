---
title: "Ссылка My (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My feature
- My reference
ms.assetid: 6f803bd7-21ff-4569-b1fe-b00a6678b1e3
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9cf23a3cc435f3ddea778b368716a35dde90656c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="my-reference-visual-basic"></a><span data-ttu-id="d08f2-102">Ссылка My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d08f2-102">My Reference (Visual Basic)</span></span>
<span data-ttu-id="d08f2-103">`My` Программирование быстрее и проще благодаря функции, предоставляя интуитивно понятный доступ к часто используемые методы, свойства и события.</span><span class="sxs-lookup"><span data-stu-id="d08f2-103">The `My` feature makes programming faster and easier by giving you intuitive access to commonly used methods, properties, and events.</span></span> <span data-ttu-id="d08f2-104">В этой таблице перечислены объекты, содержащиеся в `My`и действия, которые могут быть выполнены с каждым.</span><span class="sxs-lookup"><span data-stu-id="d08f2-104">This table lists the objects contained in `My`, and the actions that can be performed with each.</span></span>  
  
|<span data-ttu-id="d08f2-105">**Действие**</span><span class="sxs-lookup"><span data-stu-id="d08f2-105">**Action**</span></span>|<span data-ttu-id="d08f2-106">**Объект**</span><span class="sxs-lookup"><span data-stu-id="d08f2-106">**Object**</span></span>|  
|----------------|----------------|  
|<span data-ttu-id="d08f2-107">Сведения о доступе к приложения и службы.</span><span class="sxs-lookup"><span data-stu-id="d08f2-107">Accessing application information and services.</span></span>|<span data-ttu-id="d08f2-108">Объект `My.Application` состоит из следующих классов:</span><span class="sxs-lookup"><span data-stu-id="d08f2-108">The `My.Application` object consists of the following classes:</span></span><br /><br /> <span data-ttu-id="d08f2-109"><xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> включает элементы, доступные во всех проектах;</span><span class="sxs-lookup"><span data-stu-id="d08f2-109"><xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> provides members that are available in all projects.</span></span><br /><br /> <span data-ttu-id="d08f2-110"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> включает элементы, доступные в приложениях Windows Forms;</span><span class="sxs-lookup"><span data-stu-id="d08f2-110"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> provides members available in Windows Forms applications.</span></span><br /><br /> <span data-ttu-id="d08f2-111"><xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> включает элементы, доступные в консольных приложениях.</span><span class="sxs-lookup"><span data-stu-id="d08f2-111"><xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> provides members available in console applications.</span></span>|  
|<span data-ttu-id="d08f2-112">Доступ к главного компьютера и его ресурсов, служб и данных.</span><span class="sxs-lookup"><span data-stu-id="d08f2-112">Accessing the host computer and its resources, services, and data.</span></span>|<span data-ttu-id="d08f2-113">`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)</span><span class="sxs-lookup"><span data-stu-id="d08f2-113">`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)</span></span>|  
|<span data-ttu-id="d08f2-114">Доступ к формам в текущем проекте.</span><span class="sxs-lookup"><span data-stu-id="d08f2-114">Accessing the forms in the current project.</span></span>|[<span data-ttu-id="d08f2-115">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="d08f2-115">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="d08f2-116">Доступ к журналу приложений.</span><span class="sxs-lookup"><span data-stu-id="d08f2-116">Accessing the application log.</span></span>|<span data-ttu-id="d08f2-117">`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)</span><span class="sxs-lookup"><span data-stu-id="d08f2-117">`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)</span></span>|  
|<span data-ttu-id="d08f2-118">Доступ к текущей веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="d08f2-118">Accessing the current web request.</span></span>|[<span data-ttu-id="d08f2-119">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="d08f2-119">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)|  
|<span data-ttu-id="d08f2-120">Доступ к ресурсам элементов.</span><span class="sxs-lookup"><span data-stu-id="d08f2-120">Accessing resource elements.</span></span>|[<span data-ttu-id="d08f2-121">Объект My.Resources</span><span class="sxs-lookup"><span data-stu-id="d08f2-121">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)|  
|<span data-ttu-id="d08f2-122">Доступ к текущей веб-ответа.</span><span class="sxs-lookup"><span data-stu-id="d08f2-122">Accessing the current web response.</span></span>|[<span data-ttu-id="d08f2-123">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="d08f2-123">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)|  
|<span data-ttu-id="d08f2-124">Доступ к уровня параметров пользователя и приложения.</span><span class="sxs-lookup"><span data-stu-id="d08f2-124">Accessing user and application level settings.</span></span>|[<span data-ttu-id="d08f2-125">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="d08f2-125">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)|  
|<span data-ttu-id="d08f2-126">Доступ к контексту безопасности текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="d08f2-126">Accessing the current user's security context.</span></span>|<span data-ttu-id="d08f2-127">`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)</span><span class="sxs-lookup"><span data-stu-id="d08f2-127">`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)</span></span>|  
|<span data-ttu-id="d08f2-128">Доступ к веб-служб XML ссылается текущий проект.</span><span class="sxs-lookup"><span data-stu-id="d08f2-128">Accessing XML Web services referenced by the current project.</span></span>|[<span data-ttu-id="d08f2-129">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="d08f2-129">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
  
## <a name="see-also"></a><span data-ttu-id="d08f2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d08f2-130">See Also</span></span>  
 [<span data-ttu-id="d08f2-131">Обзор модели приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d08f2-131">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 [<span data-ttu-id="d08f2-132">Разработка с использованием My</span><span class="sxs-lookup"><span data-stu-id="d08f2-132">Development with My</span></span>](../../../visual-basic/developing-apps/development-with-my/index.md)
