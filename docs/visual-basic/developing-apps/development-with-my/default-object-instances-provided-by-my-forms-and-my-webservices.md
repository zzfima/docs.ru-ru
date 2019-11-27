---
title: Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: d06df4bd023892429b2aaefdd624398a6546d06d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330204"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="e56fb-102">Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e56fb-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="e56fb-103">Объекты [My. Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) и [My. WebService](../../../visual-basic/language-reference/objects/my-webservices-object.md) предоставляют доступ к формам, источникам данных и веб-службам XML, используемым приложением.</span><span class="sxs-lookup"><span data-stu-id="e56fb-103">The [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) and [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="e56fb-104">Это делается путем предоставления коллекций *экземпляров по умолчанию* для каждого из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="e56fb-104">They do this by providing collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="e56fb-105">Экземпляры по умолчанию</span><span class="sxs-lookup"><span data-stu-id="e56fb-105">Default Instances</span></span>  

 <span data-ttu-id="e56fb-106">Экземпляр по умолчанию — это экземпляр класса, который предоставляется средой выполнения и не требует объявления и создания экземпляра с помощью инструкций `Dim` и `New`.</span><span class="sxs-lookup"><span data-stu-id="e56fb-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="e56fb-107">В следующем примере показано, как можно было объявить и создать экземпляр <xref:System.Windows.Forms.Form> класса с именем `Form1`, и как теперь можно получить экземпляр по умолчанию этого класса <xref:System.Windows.Forms.Form> через `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="e56fb-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="e56fb-108">Объект `My.Forms` Возвращает коллекцию экземпляров по умолчанию для каждого класса `Form`, существующего в проекте.</span><span class="sxs-lookup"><span data-stu-id="e56fb-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="e56fb-109">Аналогичным образом `My.WebServices` предоставляет экземпляр класса-посредника по умолчанию для каждой веб-службы, на которую вы создали ссылку в приложении.</span><span class="sxs-lookup"><span data-stu-id="e56fb-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e56fb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="e56fb-110">See also</span></span>

- [<span data-ttu-id="e56fb-111">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="e56fb-111">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="e56fb-112">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="e56fb-112">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="e56fb-113">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="e56fb-113">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
