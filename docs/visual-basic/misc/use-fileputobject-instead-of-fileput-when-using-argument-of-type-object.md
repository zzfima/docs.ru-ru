---
title: "Использовать &#39; FilePutObject &#39; Вместо &#39; FilePut &#39; При использовании аргумента типа &#39; объект &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cba4af206e2dbf767fdb883ec81229a67842c57
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="01c88-102">Использовать &#39; FilePutObject &#39; Вместо &#39; FilePut &#39; При использовании аргумента типа &#39; объект &#39;</span><span class="sxs-lookup"><span data-stu-id="01c88-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="01c88-103">`FilePut` Метод включает аргумент типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="01c88-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="01c88-104">Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="01c88-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01c88-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="01c88-105">To correct this error</span></span>  
  
-   <span data-ttu-id="01c88-106">Замените `FilePut` объектом `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="01c88-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="01c88-107">Приведите аргумент `Object` к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="01c88-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="01c88-108">Используйте функциональность объекта `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="01c88-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c88-109">См. также</span><span class="sxs-lookup"><span data-stu-id="01c88-109">See Also</span></span>  
 [<span data-ttu-id="01c88-110">НЕ в СБОРКЕ: Функция FilePutObject</span><span class="sxs-lookup"><span data-stu-id="01c88-110">NOT IN BUILD: FilePutObject Function</span></span>](http://msdn.microsoft.com/en-us/a0f52a1c-5ecc-4945-b18c-03147af61d6b)  
 [<span data-ttu-id="01c88-111">Объект My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="01c88-111">My.Computer.FileSystem Object</span></span>](../../visual-basic/language-reference/objects/my-computer-filesystem-object.md)  
 [<span data-ttu-id="01c88-112">Метод My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="01c88-112">My.Computer.FileSystem.WriteAllBytes Method</span></span>](http://msdn.microsoft.com/en-us/b1a24dc1-eac8-4e22-8ffa-cc3bacbaf826)
