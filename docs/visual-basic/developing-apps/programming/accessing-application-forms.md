---
title: Доступ к формам приложения
ms.date: 07/20/2015
helpviewer_keywords:
- forms [Visual Basic], communicating between
- application forms [Visual Basic], accessing
- forms [Visual Basic], accessing one from another
- My.Forms object
- forms [Visual Basic], accessing all open
ms.assetid: 9aaf5aaf-2012-4f97-89c7-6e62b9d17863
ms.openlocfilehash: 332b6a7563160528b6c17210170af0db6e9bc0e7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349240"
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="48823-102">Доступ к формам приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48823-102">Accessing Application Forms (Visual Basic)</span></span>

<span data-ttu-id="48823-103">Объект `My.Forms` предоставляет простой способ доступа к экземпляру каждой формы Windows, объявленной в проекте приложения.</span><span class="sxs-lookup"><span data-stu-id="48823-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="48823-104">Для доступа к экрану-заставке и основной форме приложения, а также для получения списка открытых форм приложения можно также использовать свойства объекта `My.Application`.</span><span class="sxs-lookup"><span data-stu-id="48823-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="48823-105">Задания</span><span class="sxs-lookup"><span data-stu-id="48823-105">Tasks</span></span>  

 <span data-ttu-id="48823-106">Приведенная ниже таблица содержит примеры, показывающие, как получить доступ к формам приложения.</span><span class="sxs-lookup"><span data-stu-id="48823-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="48823-107">Чтобы</span><span class="sxs-lookup"><span data-stu-id="48823-107">To</span></span>|<span data-ttu-id="48823-108">См.</span><span class="sxs-lookup"><span data-stu-id="48823-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="48823-109">Доступ к одной форме приложения из другой</span><span class="sxs-lookup"><span data-stu-id="48823-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="48823-110">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="48823-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="48823-111">Отображение заголовков всех открытых форм приложения</span><span class="sxs-lookup"><span data-stu-id="48823-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="48823-112">Обновление данных о состоянии на экране-заставке при запуске приложения</span><span class="sxs-lookup"><span data-stu-id="48823-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="48823-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48823-113">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>
- [<span data-ttu-id="48823-114">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="48823-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
