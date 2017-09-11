---
title: "Слишком много клиентов Библиотеки приложения | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 18781161d1208e7e8d01f99eb9d655803d249e6e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="3c41d-102">Слишком много приложений-клиентов DLL</span><span class="sxs-lookup"><span data-stu-id="3c41d-102">Too many DLL application clients</span></span>
<span data-ttu-id="3c41d-103">Библиотека динамической компоновки (DLL), для [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] может обеспечить доступ ограниченному числу ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="3c41d-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="3c41d-104">Приложение и другие приложения, которые являются [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] узлов (некоторые из которых может осуществляться приложением) пытаются получить доступ к [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] DLL в то же время.</span><span class="sxs-lookup"><span data-stu-id="3c41d-104">Your application and other applications that are [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3c41d-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3c41d-105">To correct this error</span></span>  
  
-   <span data-ttu-id="3c41d-106">Уменьшите число открытых приложений, использующих [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c41d-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c41d-107">См. также</span><span class="sxs-lookup"><span data-stu-id="3c41d-107">See Also</span></span>  
 [<span data-ttu-id="3c41d-108">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="3c41d-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
