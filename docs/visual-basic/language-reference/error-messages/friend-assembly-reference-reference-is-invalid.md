---
title: Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: c47fae9c60dc04ee02b1ff015d3dde87b8920c02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587375"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="d67f7-102">Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым</span><span class="sxs-lookup"><span data-stu-id="d67f7-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="d67f7-103">Ссылка на дружественную сборку \<ссылка > является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="d67f7-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="d67f7-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="d67f7-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="d67f7-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку строгим именем, но не включает `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="d67f7-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="d67f7-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="d67f7-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d67f7-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d67f7-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="d67f7-108">Определите открытый ключ для сборки со строгими именами friend.</span><span class="sxs-lookup"><span data-stu-id="d67f7-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="d67f7-109">Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="d67f7-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d67f7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d67f7-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="d67f7-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="d67f7-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

