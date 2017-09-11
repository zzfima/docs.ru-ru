---
title: "Доступ к формам приложения (Visual Basic)"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- forms, communicating between
- application forms, accessing
- forms, accessing one from another
- My.Forms object
- forms, accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 37c8aa78d945a4d13ce00239d6b0707977f2571e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="d7a85-102">Доступ к формам приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7a85-102">Accessing Application Forms (Visual Basic)</span></span>
<span data-ttu-id="d7a85-103">Объект `My.Forms` предоставляет простой способ доступа к экземпляру каждой формы Windows, объявленной в проекте приложения.</span><span class="sxs-lookup"><span data-stu-id="d7a85-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="d7a85-104">Для доступа к экрану-заставке и основной форме приложения, а также для получения списка открытых форм приложения можно также использовать свойства объекта `My.Application`.</span><span class="sxs-lookup"><span data-stu-id="d7a85-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="d7a85-105">Задачи</span><span class="sxs-lookup"><span data-stu-id="d7a85-105">Tasks</span></span>  
 <span data-ttu-id="d7a85-106">Приведенная ниже таблица содержит примеры, показывающие, как получить доступ к формам приложения.</span><span class="sxs-lookup"><span data-stu-id="d7a85-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="d7a85-107">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="d7a85-107">To</span></span>|<span data-ttu-id="d7a85-108">См.</span><span class="sxs-lookup"><span data-stu-id="d7a85-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="d7a85-109">Доступ к одной форме приложения из другой</span><span class="sxs-lookup"><span data-stu-id="d7a85-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="d7a85-110">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="d7a85-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="d7a85-111">Отображение заголовков всех открытых форм приложения</span><span class="sxs-lookup"><span data-stu-id="d7a85-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="d7a85-112">Обновление данных о состоянии на экране-заставке при запуске приложения</span><span class="sxs-lookup"><span data-stu-id="d7a85-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="d7a85-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d7a85-113">See Also</span></span>  
 <span data-ttu-id="d7a85-114"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A></span><span class="sxs-lookup"><span data-stu-id="d7a85-114"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A></span></span>   
 <span data-ttu-id="d7a85-115"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A></span><span class="sxs-lookup"><span data-stu-id="d7a85-115"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A></span></span>   
 [<span data-ttu-id="d7a85-116">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="d7a85-116">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)

