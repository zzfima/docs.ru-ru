---
title: "Невозможно завершить операцию: конечный каталог находится внутри исходного"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0a17877b2335ee010a97f0b522bd4c399867cd7d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a><span data-ttu-id="786d2-102">Невозможно завершить операцию: конечный каталог находится внутри исходного</span><span class="sxs-lookup"><span data-stu-id="786d2-102">Could not complete operation since target directory is under source directory</span></span>
<span data-ttu-id="786d2-103">Циклическая операция не удалась.</span><span class="sxs-lookup"><span data-stu-id="786d2-103">A cyclic operation has failed.</span></span> <span data-ttu-id="786d2-104">Циклические операции являются бесконечными циклами и поэтому не могут завершиться.</span><span class="sxs-lookup"><span data-stu-id="786d2-104">Cyclic operations cycle and therefore cannot complete.</span></span> <span data-ttu-id="786d2-105">Например, объект A может попытаться наследоваться от объекта B, который в свою очередь наследуется от объекта A.</span><span class="sxs-lookup"><span data-stu-id="786d2-105">For example, Object A may attempt to inherit from Object B, which in turn inherits from Object A.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="786d2-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="786d2-106">To correct this error</span></span>  
  
-   <span data-ttu-id="786d2-107">При наследовании убедитесь в отсутствии циклических ссылок.</span><span class="sxs-lookup"><span data-stu-id="786d2-107">When inheriting, make sure that there are no cyclic references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786d2-108">См. также</span><span class="sxs-lookup"><span data-stu-id="786d2-108">See Also</span></span>  
 [<span data-ttu-id="786d2-109">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="786d2-109">Error Types</span></span>](../../visual-basic/programming-guide/language-features/error-types.md)  
 [<span data-ttu-id="786d2-110">Общие сведения об отладке: точки останова</span><span class="sxs-lookup"><span data-stu-id="786d2-110">Debugging Basics: Breakpoints</span></span>](http://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)
