---
title: Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f1ac1ea14efb0cdf0d8ca03257e4da33d35e368
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="f30f5-102">Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.</span><span class="sxs-lookup"><span data-stu-id="f30f5-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="f30f5-103">Предпринята попытка либо вызова процедуры `Friend` класса, либо получения доступа к дружественному ( `Friend` ) свойству или методу между процессами или между потоками.</span><span class="sxs-lookup"><span data-stu-id="f30f5-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="f30f5-104">Процедура `Friend` может вызываться из модуля вне класса, однако она является частью проекта, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="f30f5-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f30f5-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f30f5-105">To correct this error</span></span>  
  
-   <span data-ttu-id="f30f5-106">Убедитесь, что вызов процедуры или доступ к процедуре выполняется из модуля, являющегося частью проекта, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="f30f5-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30f5-107">См. также</span><span class="sxs-lookup"><span data-stu-id="f30f5-107">See Also</span></span>  
 [<span data-ttu-id="f30f5-108">Friend</span><span class="sxs-lookup"><span data-stu-id="f30f5-108">Friend</span></span>](../../visual-basic/language-reference/modifiers/friend.md)
