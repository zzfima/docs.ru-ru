---
title: Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
ms.openlocfilehash: 7dbb15c43d044e21c9823c4a1652b0408006e5c3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032771"
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a><span data-ttu-id="91c2d-102">Быстрая разработка приложений с использованием My.Resources и My.Settings (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91c2d-102">Rapid Application Development with My.Resources and My.Settings (Visual Basic)</span></span>
<span data-ttu-id="91c2d-103">`My.Resources` Объект предоставляет доступ к ресурсам приложения и позволяет динамически получать ресурсы для приложения.</span><span class="sxs-lookup"><span data-stu-id="91c2d-103">The `My.Resources` object provides access to the application's resources and allows you to dynamically retrieve resources for your application.</span></span>  
  
## <a name="retrieving-resources"></a><span data-ttu-id="91c2d-104">Извлечение ресурсов</span><span class="sxs-lookup"><span data-stu-id="91c2d-104">Retrieving Resources</span></span>  
 <span data-ttu-id="91c2d-105">Множество ресурсов, таких как звуковые файлы, значки, изображения и строки можно извлечь с помощью `My.Resources` объекта.</span><span class="sxs-lookup"><span data-stu-id="91c2d-105">A number of resources such as audio files, icons, images, and strings can be retrieved through the `My.Resources` object.</span></span> <span data-ttu-id="91c2d-106">Например можно получить доступ к файлы ресурсов, связанные с языком и региональными параметрами приложения.</span><span class="sxs-lookup"><span data-stu-id="91c2d-106">For example, you can access the application's culture-specific resource files.</span></span> <span data-ttu-id="91c2d-107">В следующем примере задается значок формы на значок с именем `Form1Icon` хранятся в файле ресурсов приложения.</span><span class="sxs-lookup"><span data-stu-id="91c2d-107">The following example sets the icon of the form to the icon named `Form1Icon` stored in the application's resource file.</span></span>  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 <span data-ttu-id="91c2d-108">`My.Resources` Объект предоставляет только глобальные ресурсы.</span><span class="sxs-lookup"><span data-stu-id="91c2d-108">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="91c2d-109">Она предоставляет доступ к файлам ресурсов, связанных с формами.</span><span class="sxs-lookup"><span data-stu-id="91c2d-109">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="91c2d-110">Доступ к ресурсам формы необходимо из формы.</span><span class="sxs-lookup"><span data-stu-id="91c2d-110">You must access the form resources from the form.</span></span>  
  
 <span data-ttu-id="91c2d-111">Аналогичным образом `My.Settings` объект предоставляет доступ к параметрам приложения и позволяет динамически сохранять и извлекать значения свойств и другие сведения для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="91c2d-111">Similarly, the `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="91c2d-112">Дополнительные сведения см. в разделе [объект My.Resources](../../../visual-basic/language-reference/objects/my-resources-object.md) и [объект My.Settings](../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="91c2d-112">For more information, see [My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md) and [My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c2d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="91c2d-113">See Also</span></span>  
 [<span data-ttu-id="91c2d-114">Объект My.Resources</span><span class="sxs-lookup"><span data-stu-id="91c2d-114">My.Resources Object</span></span>](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [<span data-ttu-id="91c2d-115">Объект My.Settings</span><span class="sxs-lookup"><span data-stu-id="91c2d-115">My.Settings Object</span></span>](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="91c2d-116">Доступ к параметрам приложения</span><span class="sxs-lookup"><span data-stu-id="91c2d-116">Accessing Application Settings</span></span>](../../../visual-basic/developing-apps/programming/app-settings/index.md)
