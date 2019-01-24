---
title: Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: cdedcc18aa82f6efd8c52cdca5d915d7d78e269f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611934"
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="6d695-102">Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым</span><span class="sxs-lookup"><span data-stu-id="6d695-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="6d695-103">Ссылка на дружественную сборку \<ссылку > является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="6d695-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="6d695-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="6d695-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="6d695-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку со строгим именем, но он не включает `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="6d695-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="6d695-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="6d695-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6d695-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6d695-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="6d695-108">Определите открытый ключ для строгое имя дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="6d695-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="6d695-109">Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="6d695-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d695-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6d695-110">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="6d695-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="6d695-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


