---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 0966cea26c5dde8f116081c7a6411b4275e50f40
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817049"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="cde16-102">Ссылка на дружественную сборку \<ссылку > является недопустимым</span><span class="sxs-lookup"><span data-stu-id="cde16-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="cde16-103">Ссылка на дружественную сборку \<ссылку > является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="cde16-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="cde16-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="cde16-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="cde16-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку со строгим именем, но он не включает `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="cde16-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="cde16-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="cde16-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cde16-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cde16-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="cde16-108">Определите открытый ключ для строгое имя дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="cde16-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="cde16-109">Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="cde16-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cde16-110">См. также</span><span class="sxs-lookup"><span data-stu-id="cde16-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="cde16-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="cde16-111">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
