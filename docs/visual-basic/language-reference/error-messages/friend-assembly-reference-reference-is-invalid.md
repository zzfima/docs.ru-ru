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
ms.openlocfilehash: 39ae94e309ee8d18e6b5317445b7e4b7f6a42af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="30135-102">Ссылка на дружественную сборку &lt;ссылка&gt; является недопустимым</span><span class="sxs-lookup"><span data-stu-id="30135-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="30135-103">Ссылка на дружественную сборку \<ссылка > является недопустимым.</span><span class="sxs-lookup"><span data-stu-id="30135-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="30135-104">Для сборок, подписанных строгим именем, в объявлении InternalsVisibleTo должен быть указан открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="30135-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="30135-105">Имя сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута идентифицирует сборку строгим именем, но не включает `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="30135-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="30135-106">**Идентификатор ошибки:** BC31535</span><span class="sxs-lookup"><span data-stu-id="30135-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="30135-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="30135-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="30135-108">Определите открытый ключ для сборки со строгими именами friend.</span><span class="sxs-lookup"><span data-stu-id="30135-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="30135-109">Поместить открытый ключ как часть имени сборки, передаваемый в <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> конструктор атрибута с помощью `PublicKey` атрибута.</span><span class="sxs-lookup"><span data-stu-id="30135-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30135-110">См. также</span><span class="sxs-lookup"><span data-stu-id="30135-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="30135-111">Дружественные сборки</span><span class="sxs-lookup"><span data-stu-id="30135-111">Friend Assemblies</span></span>](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)  
 [<span data-ttu-id="30135-112">Практическое руководство. Создание подписанных дружественных сборок</span><span class="sxs-lookup"><span data-stu-id="30135-112">How to: Create Signed Friend Assemblies</span></span>](http://msdn.microsoft.com/library/f5542300-58b4-4e1c-b809-8df11e95e69b)
