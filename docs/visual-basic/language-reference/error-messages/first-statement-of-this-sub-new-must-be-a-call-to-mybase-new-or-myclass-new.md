---
title: Первый оператор этого Sub New должен быть вызовом MyBase.New или MyClass.New (Нет доступного конструктора без параметров)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 160e4d512a1533b3c89a1af50b47600ca6df51c2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592056"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="0c33d-102">Первый оператор этого Sub New должен быть вызовом MyBase.New или MyClass.New (Нет доступного конструктора без параметров)</span><span class="sxs-lookup"><span data-stu-id="0c33d-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="0c33d-103">Первый оператор в «Sub New» должен быть вызовом «MyBase.New» или «MyClass.New», так как базовый класс\<basename > "из"\<derivedname > "не имеет доступного «Sub New», который может быть вызван без аргументов.</span><span class="sxs-lookup"><span data-stu-id="0c33d-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="0c33d-104">В производном классе, каждый конструктор должен вызвать конструктор базового класса (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="0c33d-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="0c33d-105">Если базовый класс имеет конструктор без параметров, доступных производным классам `MyBase.New` может вызываться автоматически.</span><span class="sxs-lookup"><span data-stu-id="0c33d-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="0c33d-106">В противном случае необходимо вызвать конструктор базового класса с параметрами, и это не может быть сделано автоматически.</span><span class="sxs-lookup"><span data-stu-id="0c33d-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="0c33d-107">В этом случае первый оператор в конструктор каждого производного класса необходимо вызвать параметризованный конструктор базового класса, или вызвать другой конструктор в производном классе, который делает вызов конструктора базового класса.</span><span class="sxs-lookup"><span data-stu-id="0c33d-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="0c33d-108">**Идентификатор ошибки:** BC30148</span><span class="sxs-lookup"><span data-stu-id="0c33d-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0c33d-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0c33d-109">To correct this error</span></span>  
  
- <span data-ttu-id="0c33d-110">Вызовите `MyBase.New` предоставляющий необходимые параметры, или другой конструктор, выполняющий подобный вызов.</span><span class="sxs-lookup"><span data-stu-id="0c33d-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="0c33d-111">Например, если базовый класс имеет конструктор, который объявляется как `Public Sub New(ByVal index as Integer)`, первый оператор в производный конструктор класса может быть `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="0c33d-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c33d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0c33d-112">See also</span></span>

- [<span data-ttu-id="0c33d-113">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="0c33d-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
