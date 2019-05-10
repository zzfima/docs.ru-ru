---
title: Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.
ms.date: 07/20/2015
f1_keywords:
- vbrID97
ms.assetid: b9d821f0-8565-4f15-bb35-184789c69662
ms.openlocfilehash: a227e5761bacc36c0682844a833e70c34582a5d3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622597"
---
# <a name="cannot-call-friend-function-on-object-which-is-not-an-instance-of-defining-class"></a><span data-ttu-id="6227f-102">Невозможно вызвать дружественную функцию для объекта, не являющегося экземпляром определяющего класса.</span><span class="sxs-lookup"><span data-stu-id="6227f-102">Cannot call friend function on object which is not an instance of defining class</span></span>
<span data-ttu-id="6227f-103">Предпринята попытка либо вызова процедуры `Friend` класса, либо получения доступа к дружественному ( `Friend` ) свойству или методу между процессами или между потоками.</span><span class="sxs-lookup"><span data-stu-id="6227f-103">Either you tried to call the `Friend` procedure of a class, or you tried to access a `Friend` property or method either cross-process or cross-thread.</span></span> <span data-ttu-id="6227f-104">Процедура `Friend` может вызываться из модуля вне класса, однако она является частью проекта, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="6227f-104">A `Friend` procedure is callable from a module outside the class, but is part of the project in which the class is defined.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6227f-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6227f-105">To correct this error</span></span>  
  
- <span data-ttu-id="6227f-106">Убедитесь, что вызов процедуры или доступ к процедуре выполняется из модуля, являющегося частью проекта, в котором определен класс.</span><span class="sxs-lookup"><span data-stu-id="6227f-106">Ensure that you are calling or accessing the procedure from a module that is part of the project in which the class is defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6227f-107">См. также</span><span class="sxs-lookup"><span data-stu-id="6227f-107">See also</span></span>

- [<span data-ttu-id="6227f-108">Friend</span><span class="sxs-lookup"><span data-stu-id="6227f-108">Friend</span></span>](../../visual-basic/language-reference/modifiers/friend.md)
