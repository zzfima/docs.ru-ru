---
title: Ссылка <reference> на дружественную сборку является недопустимой
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 6eb46c6479adc69eaf65b34c69aa69977b4d62ef
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972396"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="8108e-102">Недопустимый \<Справочник по ссылке на дружественную сборку ></span><span class="sxs-lookup"><span data-stu-id="8108e-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="8108e-103">Недопустимый \<ссылочный > дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="8108e-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="8108e-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="8108e-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="8108e-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута, определяет сборку со строгим именем, но не `PublicKey` включает атрибут.</span><span class="sxs-lookup"><span data-stu-id="8108e-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="8108e-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="8108e-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8108e-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8108e-107">To correct this error</span></span>  
  
1. <span data-ttu-id="8108e-108">Определите открытый ключ для дружественной сборки со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="8108e-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="8108e-109">Включите открытый ключ как часть имени сборки, передаваемой <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктору атрибута с `PublicKey` помощью атрибута.</span><span class="sxs-lookup"><span data-stu-id="8108e-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8108e-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8108e-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="8108e-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="8108e-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
