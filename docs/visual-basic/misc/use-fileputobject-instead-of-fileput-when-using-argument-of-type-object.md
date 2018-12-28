---
title: При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: df7d7c54992984bcb1684e41f60ae8361a3aed03
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2018
ms.locfileid: "53774229"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="c5f71-102">При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut</span><span class="sxs-lookup"><span data-stu-id="c5f71-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="c5f71-103">Метод `FilePut` включает аргумент типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="c5f71-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="c5f71-104">Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="c5f71-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c5f71-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c5f71-105">To correct this error</span></span>  
  
-   <span data-ttu-id="c5f71-106">Замените `FilePut` объектом `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="c5f71-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="c5f71-107">Приведите аргумент `Object` к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="c5f71-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="c5f71-108">Используйте функциональность объекта `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="c5f71-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5f71-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c5f71-109">See Also</span></span>  
   
 [<span data-ttu-id="c5f71-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="c5f71-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="c5f71-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="c5f71-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
