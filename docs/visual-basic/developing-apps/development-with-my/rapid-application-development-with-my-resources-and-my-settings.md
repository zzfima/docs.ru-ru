---
title: "Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7339afdc35341739b592b2a327094754031c346c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="510e6-102">Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="510e6-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="510e6-103">`My.Resources` Объект предоставляет доступ к ресурсам приложения и позволяет динамически извлекать ресурсы для приложения.</span><span class="sxs-lookup"><span data-stu-id="510e6-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="510e6-104">Извлечение ресурсов</span><span class="sxs-lookup"><span data-stu-id="510e6-104">Retrieving Resources</span></span>  
 <span data-ttu-id="510e6-105">Ряд ресурсов, таких как звуковые файлы, значки, изображения и строки можно извлечь с помощью `My.Resources` объекта.</span><span class="sxs-lookup"><span data-stu-id="510e6-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="510e6-106">Например можно получить доступ к файлы ресурсов для определенных языка и региональных параметров приложения.</span><span class="sxs-lookup"><span data-stu-id="510e6-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="510e6-107">В следующем примере задается значок формы на значок с именем `Form1Icon` хранятся в файле ресурсов приложения.</span><span class="sxs-lookup"><span data-stu-id="510e6-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="510e6-108">`My.Resources` Объект предоставляет только глобальные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="510e6-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="510e6-109">Он не предоставляет доступ к файлам ресурсов, связанных с формами.</span><span class="sxs-lookup"><span data-stu-id="510e6-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="510e6-110">Для доступа к ресурсам формы из формы.</span><span class="sxs-lookup"><span data-stu-id="510e6-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="510e6-111">Аналогичным образом `My.Settings` объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения о приложении.</span><span class="sxs-lookup"><span data-stu-id="510e6-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="510e6-112">Дополнительные сведения см. в разделе [My.Resources-объект](../../../visual-basic/language-reference/objects/my-resources-object.md) и [My.Settings-объект](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="510e6-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="510e6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="510e6-113">See Also</span></span>  
 [<span data-ttu-id="510e6-114">Объект My.Resources</span><span class="sxs-lookup"><span data-stu-id="510e6-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [<span data-ttu-id="510e6-115">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="510e6-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="510e6-116">Доступ к параметрам приложения</span><span class="sxs-lookup"><span data-stu-id="510e6-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
