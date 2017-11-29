---
title: "Слишком много приложений-клиентов DLL"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID47
ms.assetid: 4b87780b-67ad-4c96-9253-db954a751dad
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b9278134e937ac8bf4626237954432d727ac0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-dll-application-clients"></a><span data-ttu-id="4e49a-102">Слишком много приложений-клиентов DLL</span><span class="sxs-lookup"><span data-stu-id="4e49a-102">Too many DLL application clients</span></span>
<span data-ttu-id="4e49a-103">Библиотека динамической компоновки (DLL) для [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] может обеспечить доступ ограниченному числу ведущих приложений.</span><span class="sxs-lookup"><span data-stu-id="4e49a-103">The dynamic-link library (DLL) for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] can only accommodate access by a limited number of host applications.</span></span> <span data-ttu-id="4e49a-104">Ваше приложение и другие приложения, которые являются узлами [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] (к некоторым из которых может обращаться ваше приложение), пытаются получить доступ к библиотеке DLL [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] одновременно.</span><span class="sxs-lookup"><span data-stu-id="4e49a-104">Your application and other applications that are [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] hosts (some of which may be accessed by your application) are all attempting to access the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] DLL at the same time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e49a-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4e49a-105">To correct this error</span></span>  
  
-   <span data-ttu-id="4e49a-106">Уменьшите число открытых приложений, обращающихся к [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4e49a-106">Reduce the number of open applications accessing [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e49a-107">См. также</span><span class="sxs-lookup"><span data-stu-id="4e49a-107">See Also</span></span>  
 [<span data-ttu-id="4e49a-108">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="4e49a-108">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)
