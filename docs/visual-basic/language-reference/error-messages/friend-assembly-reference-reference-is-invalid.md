---
title: "Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords: BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab1c7c5cc7a7f4ad899df7722769238e05d96e6b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="c6a26-102">Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым</span><span class="sxs-lookup"><span data-stu-id="c6a26-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="c6a26-103">Ссылка на дружественную сборку \<ссылка > является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="c6a26-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="c6a26-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="c6a26-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="c6a26-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку строгим именем, но не включает `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="c6a26-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="c6a26-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="c6a26-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c6a26-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c6a26-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="c6a26-108">Определите открытый ключ для сборки со строгими именами friend.</span><span class="sxs-lookup"><span data-stu-id="c6a26-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="c6a26-109">Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="c6a26-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a26-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c6a26-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="c6a26-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="c6a26-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 

