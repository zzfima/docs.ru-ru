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
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349240"
---
# <a name="accessing-application-forms-visual-basic"></a><span data-ttu-id="018a6-102">Доступ к формам приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="018a6-102">Accessing Application Forms (Visual Basic)</span></span>

<span data-ttu-id="018a6-103">Объект `My.Forms` предоставляет простой способ доступа к экземпляру каждой формы Windows, объявленной в проекте приложения.</span><span class="sxs-lookup"><span data-stu-id="018a6-103">The `My.Forms` object provides an easy way to access an instance of each Windows Form declared in the application's project.</span></span> <span data-ttu-id="018a6-104">Для доступа к экрану-заставке и основной форме приложения, а также для получения списка открытых форм приложения можно также использовать свойства объекта `My.Application`.</span><span class="sxs-lookup"><span data-stu-id="018a6-104">You can also use properties of the `My.Application` object to access the application's splash screen and main form, and get a list of the application's open forms.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="018a6-105">Задачи</span><span class="sxs-lookup"><span data-stu-id="018a6-105">Tasks</span></span>  

 <span data-ttu-id="018a6-106">Приведенная ниже таблица содержит примеры, показывающие, как получить доступ к формам приложения.</span><span class="sxs-lookup"><span data-stu-id="018a6-106">The following table lists examples showing how to access an application's forms.</span></span>  
  
|<span data-ttu-id="018a6-107">Кому</span><span class="sxs-lookup"><span data-stu-id="018a6-107">To</span></span>|<span data-ttu-id="018a6-108">См.</span><span class="sxs-lookup"><span data-stu-id="018a6-108">See</span></span>|  
|---|---|  
|<span data-ttu-id="018a6-109">Доступ к одной форме приложения из другой</span><span class="sxs-lookup"><span data-stu-id="018a6-109">Access one form from another form in an application.</span></span>|[<span data-ttu-id="018a6-110">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="018a6-110">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)|  
|<span data-ttu-id="018a6-111">Отображение заголовков всех открытых форм приложения</span><span class="sxs-lookup"><span data-stu-id="018a6-111">Display the titles of all the application's open forms.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>|  
|<span data-ttu-id="018a6-112">Обновление данных о состоянии на экране-заставке при запуске приложения</span><span class="sxs-lookup"><span data-stu-id="018a6-112">Update the splash screen with status information as the application starts.</span></span>|<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="018a6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="018a6-113">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.SplashScreen%2A>
- [<span data-ttu-id="018a6-114">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="018a6-114">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
