---
title: 'Первым оператором в этой процедуре Sub New должен быть явный вызов MyBase.New или MyClass.New, так как <constructorname> в базовом классе <baseclassname> класса <derivedclassname> отмечен как устаревший: <errormessage>'
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 89b6c241bb637f2efc6014c4640b3b463c4facfa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59313481"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a><span data-ttu-id="a0942-102">Первый оператор в «Sub New» должен иметь явный вызов в «MyBase.New» или «MyClass.New», так как "\<имя_конструктора >" в базовом классе\<имя_базового_класса > "из"\<имя_производного_класса > "помечен как устаревший:"\< сообщение об ошибке > "</span><span class="sxs-lookup"><span data-stu-id="a0942-102">First statement of this 'Sub New' must be an explicit call to 'MyBase.New' or 'MyClass.New' because the '\<constructorname>' in the base class '\<baseclassname>' of '\<derivedclassname>' is marked obsolete: '\<errormessage>'</span></span>
<span data-ttu-id="a0942-103">Конструктор класса не вызывает явно конструктор базового класса, а вызванный неявно конструктор базового класса помечается атрибутом <xref:System.ObsoleteAttribute> , что является причиной возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="a0942-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="a0942-104">Если конструктор производного класса не вызывает конструктор базового класса, Visual Basic пытается создать неявный вызов конструктора базового класса без параметров.</span><span class="sxs-lookup"><span data-stu-id="a0942-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="a0942-105">Если в базовом классе, которые могут вызываться без аргументов нет доступного конструктора, Visual Basic не удается создать неявный вызов.</span><span class="sxs-lookup"><span data-stu-id="a0942-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="a0942-106">В этом случае необходимый конструктор помечается <xref:System.ObsoleteAttribute> атрибут, поэтому его нельзя вызвать Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a0942-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="a0942-107">Вы можете пометить любой программный элемент как неиспользуемый, применив к нему атрибут <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="a0942-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="a0942-108">Если вы это сделаете, вы можете задать для свойства <xref:System.ObsoleteAttribute.IsError%2A> атрибута значение `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="a0942-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="a0942-109">Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку.</span><span class="sxs-lookup"><span data-stu-id="a0942-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="a0942-110">Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.</span><span class="sxs-lookup"><span data-stu-id="a0942-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="a0942-111">**Идентификатор ошибки:** BC30920</span><span class="sxs-lookup"><span data-stu-id="a0942-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a0942-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a0942-112">To correct this error</span></span>  
  
1. <span data-ttu-id="a0942-113">Проверьте указанное сообщение об ошибке и выполните соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="a0942-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2. <span data-ttu-id="a0942-114">Включите вызов `MyBase.New()` или `MyClass.New()` в качестве первого оператора `Sub New` в производном классе.</span><span class="sxs-lookup"><span data-stu-id="a0942-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0942-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a0942-115">See also</span></span>

- [<span data-ttu-id="a0942-116">Общие сведения об атрибутах</span><span class="sxs-lookup"><span data-stu-id="a0942-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
