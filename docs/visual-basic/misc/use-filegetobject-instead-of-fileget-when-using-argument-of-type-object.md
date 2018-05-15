---
title: Используйте &#39;FileGetObject&#39; вместо &#39;FileGet&#39; при использовании аргумента типа &#39;объекта&#39;
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 2edb80f6df95774e0ea5a7b51e57925845d7ba75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="c2d5f-102">Используйте &#39;FileGetObject&#39; вместо &#39;FileGet&#39; при использовании аргумента типа &#39;объекта&#39;</span><span class="sxs-lookup"><span data-stu-id="c2d5f-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="c2d5f-103">Метод `FileGet` включает аргумент типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="c2d5f-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="c2d5f-104">Чтобы избежать неоднозначности, следует использовать`FileGetObject` вместо `FileGet` .</span><span class="sxs-lookup"><span data-stu-id="c2d5f-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="c2d5f-105">Обратите внимание, что функциональные возможности, предлагаемые `My.Computer.Filesystem` , проще в использовании и обеспечивают большую производительность, чем `FileGet` или `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="c2d5f-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2d5f-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c2d5f-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="c2d5f-107">Замените `FileGet` объектом `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="c2d5f-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="c2d5f-108">Приведите аргумент `Object` к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="c2d5f-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d5f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d5f-109">See Also</span></span>  
   
 [<span data-ttu-id="c2d5f-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="c2d5f-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
