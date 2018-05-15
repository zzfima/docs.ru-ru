---
title: Первый оператор &#39;Sub New&#39; должен являться вызов &#39;MyBase.New&#39; или &#39;MyClass.New&#39; (нет доступного конструктора без параметров)
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 3b24385932700a4843ae295bc82ef9529cc86b9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="first-statement-of-this-39sub-new39-must-be-a-call-to-39mybasenew39-or-39myclassnew39-no-accessible-constructor-without-parameters"></a><span data-ttu-id="ce3ff-102">Первый оператор &#39;Sub New&#39; должен являться вызов &#39;MyBase.New&#39; или &#39;MyClass.New&#39; (нет доступного конструктора без параметров)</span><span class="sxs-lookup"><span data-stu-id="ce3ff-102">First statement of this &#39;Sub New&#39; must be a call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="ce3ff-103">Первый оператор данного «Sub New» должен быть вызов «MyBase.New» или «MyClass.New», так как базовый класс\<базовое имя > "из"\<derivedname > "не имеет доступного «Sub New», который может вызываться без аргументов.</span><span class="sxs-lookup"><span data-stu-id="ce3ff-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="ce3ff-104">В производном классе все конструкторы должны вызывать конструктор базового класса (`MyBase.New`).</span><span class="sxs-lookup"><span data-stu-id="ce3ff-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="ce3ff-105">Если базовый класс имеет конструктор без параметров, доступных производным классам `MyBase.New` может вызываться автоматически.</span><span class="sxs-lookup"><span data-stu-id="ce3ff-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="ce3ff-106">В противном случае конструктор базового класса должен вызываться с параметрами, и это не может быть сделано автоматически.</span><span class="sxs-lookup"><span data-stu-id="ce3ff-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="ce3ff-107">В этом случае первый оператор всех конструкторов производного класса необходимо вызвать параметризованный конструктор базового класса, или вызов другого конструктора в производном классе, который делает вызов конструктора базового класса.</span><span class="sxs-lookup"><span data-stu-id="ce3ff-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="ce3ff-108">**Идентификатор ошибки:** BC30148</span><span class="sxs-lookup"><span data-stu-id="ce3ff-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce3ff-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ce3ff-109">To correct this error</span></span>  
  
-   <span data-ttu-id="ce3ff-110">Вызвать `MyBase.New` предоставляющий необходимые параметры, или другой конструктор, выполняющий подобный вызов.</span><span class="sxs-lookup"><span data-stu-id="ce3ff-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="ce3ff-111">Например, если базовый класс имеет конструктор, который объявлен как `Public Sub New(ByVal index as Integer)`, первый оператор в производном класса конструктор может быть `MyBase.New(100)`.</span><span class="sxs-lookup"><span data-stu-id="ce3ff-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce3ff-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ce3ff-112">See Also</span></span>  
 [<span data-ttu-id="ce3ff-113">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="ce3ff-113">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
