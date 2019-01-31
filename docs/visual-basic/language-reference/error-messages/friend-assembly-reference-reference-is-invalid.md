---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: ff2cdbebe13f6224209ef8da62600c99348c911b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286823"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="83a7f-102">Ссылка на дружественную сборку \<ссылку > является недопустимым</span><span class="sxs-lookup"><span data-stu-id="83a7f-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="83a7f-103">Ссылка на дружественную сборку \<ссылку > является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="83a7f-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="83a7f-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="83a7f-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="83a7f-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку со строгим именем, но он не включает `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="83a7f-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="83a7f-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="83a7f-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83a7f-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="83a7f-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="83a7f-108">Определите открытый ключ для строгое имя дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="83a7f-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="83a7f-109">Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="83a7f-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83a7f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="83a7f-110">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="83a7f-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="83a7f-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


