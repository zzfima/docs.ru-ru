---
title: Используйте &#39;FilePutObject&#39; вместо &#39;FilePut&#39; при использовании аргумента типа &#39;объекта&#39;
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 529352d98c175981c20861205ce04c8a2ebcdca9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="6f206-102">Используйте &#39;FilePutObject&#39; вместо &#39;FilePut&#39; при использовании аргумента типа &#39;объекта&#39;</span><span class="sxs-lookup"><span data-stu-id="6f206-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="6f206-103">`FilePut` Метод включает аргумент типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="6f206-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="6f206-104">Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="6f206-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f206-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6f206-105">To correct this error</span></span>  
  
-   <span data-ttu-id="6f206-106">Замените `FilePut` объектом `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="6f206-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="6f206-107">Приведите аргумент `Object` к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="6f206-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="6f206-108">Используйте функциональность объекта `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="6f206-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f206-109">См. также</span><span class="sxs-lookup"><span data-stu-id="6f206-109">See Also</span></span>  
   
 [<span data-ttu-id="6f206-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="6f206-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="6f206-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="6f206-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
