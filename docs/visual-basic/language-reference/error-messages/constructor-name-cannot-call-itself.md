---
title: Конструктор <name> не может вызывать сам себя
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 8459ee7fec6d761161a721c88ccdc88e513fc95f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324387"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="abe50-102">Конструктор "\<имя >" не может вызвать сам себя</span><span class="sxs-lookup"><span data-stu-id="abe50-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="abe50-103">Объект `Sub New` процедура в классе или структуре вызывает саму себя.</span><span class="sxs-lookup"><span data-stu-id="abe50-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="abe50-104">Конструктор предназначен для инициализации нового экземпляра класса или структуры при первом создании.</span><span class="sxs-lookup"><span data-stu-id="abe50-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="abe50-105">Класс или структура может иметь несколько конструкторов, если все они имеют разные списки параметров.</span><span class="sxs-lookup"><span data-stu-id="abe50-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="abe50-106">Конструктор может вызвать другой конструктор для выполнения его функциональных возможностей в дополнение к свой собственный.</span><span class="sxs-lookup"><span data-stu-id="abe50-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="abe50-107">Но не имеет смысла для конструктора вызвать сам себя, и на самом деле это приведет к бесконечной рекурсии Если это разрешено.</span><span class="sxs-lookup"><span data-stu-id="abe50-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="abe50-108">**Идентификатор ошибки:** BC30298</span><span class="sxs-lookup"><span data-stu-id="abe50-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="abe50-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="abe50-109">To correct this error</span></span>  
  
1. <span data-ttu-id="abe50-110">Проверьте список параметров конструктора.</span><span class="sxs-lookup"><span data-stu-id="abe50-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="abe50-111">Она должна отличаться от вызова конструктора.</span><span class="sxs-lookup"><span data-stu-id="abe50-111">It should be different from that of the constructor making the call.</span></span>  
  
2. <span data-ttu-id="abe50-112">Если вам не требуется вызывать другой конструктор, удалите `Sub New` вызов полностью.</span><span class="sxs-lookup"><span data-stu-id="abe50-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe50-113">См. также</span><span class="sxs-lookup"><span data-stu-id="abe50-113">See also</span></span>

- [<span data-ttu-id="abe50-114">Время существования: создание и уничтожение объектов</span><span class="sxs-lookup"><span data-stu-id="abe50-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
