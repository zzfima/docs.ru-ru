---
title: Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: ca31e1c40c77bf7f42d246019d81f4ffaed646e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839370"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="5ab74-102">Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ab74-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>
<span data-ttu-id="5ab74-103">[My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) и [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) объекты предоставляют доступ к формам, источникам данных и веб-служб XML, используемой приложением.</span><span class="sxs-lookup"><span data-stu-id="5ab74-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="5ab74-104">Это делается путем предоставления коллекций *по умолчанию экземпляры* каждого из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="5ab74-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="5ab74-105">Экземпляры по умолчанию</span><span class="sxs-lookup"><span data-stu-id="5ab74-105">Default Instances</span></span>  
 <span data-ttu-id="5ab74-106">Экземпляр по умолчанию является экземпляром класса, который предоставляется средой выполнения и не нужно быть объявляется и создается с помощью `Dim` и `New` инструкций.</span><span class="sxs-lookup"><span data-stu-id="5ab74-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="5ab74-107">В следующем примере показано, как вы может объявляется и создается экземпляр <xref:System.Windows.Forms.Form> класс с именем `Form1`, и как вы, теперь могут получить экземпляр по умолчанию это <xref:System.Windows.Forms.Form> класса через `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="5ab74-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="5ab74-108">`My.Forms` Объект возвращает коллекцию экземпляров по умолчанию для каждого `Form` класс, который существует в проекте.</span><span class="sxs-lookup"><span data-stu-id="5ab74-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="5ab74-109">Аналогичным образом `My.WebServices` предоставляет экземпляр по умолчанию прокси-класса для каждой веб-службы, что вы создали ссылку в приложении.</span><span class="sxs-lookup"><span data-stu-id="5ab74-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab74-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5ab74-110">See also</span></span>

- [<span data-ttu-id="5ab74-111">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="5ab74-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="5ab74-112">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="5ab74-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="5ab74-113">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="5ab74-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
