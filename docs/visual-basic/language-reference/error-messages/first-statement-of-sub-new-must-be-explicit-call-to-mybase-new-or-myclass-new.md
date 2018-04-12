---
title: 'Первый оператор в это &#39; Конструктор Sub New &#39; должен быть явным вызовом &#39; MyBase.New &#39; или &#39; MyClass.New &#39; так как &#39; &lt;имя_конструктора&gt;&#39; в базовом классе &#39;&lt; имя_базового_класса&gt;&#39; &#39;&lt; имя_производного_класса&gt;&#39; помечен как устаревший: &#39;&lt; сообщение об ошибке&gt;&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8882acd947251d85804fbefd54267ce078e31b95
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="cc45a-102">Первый оператор в это &#39; Конструктор Sub New &#39; должен быть явным вызовом &#39; MyBase.New &#39; или &#39; MyClass.New &#39; так как &#39; &lt;имя_конструктора&gt;&#39; в базовом классе &#39;&lt; имя_базового_класса&gt;&#39; &#39;&lt; имя_производного_класса&gt;&#39; помечен как устаревший: &#39;&lt; сообщение об ошибке&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="cc45a-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="cc45a-103">Конструктор класса не вызывает явно конструктор базового класса, а вызванный неявно конструктор базового класса помечается атрибутом <xref:System.ObsoleteAttribute> , что является причиной возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="cc45a-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="cc45a-104">Если конструктор производного класса не вызывает конструктор базового класса, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] пытается создать неявный вызов конструктора базового класса без параметров.</span><span class="sxs-lookup"><span data-stu-id="cc45a-104">When a derived class constructor does not call a base class constructor, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="cc45a-105">Если в базовом классе нет доступного конструктора, который можно вызывать без аргументов, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не удается создать неявный вызов.</span><span class="sxs-lookup"><span data-stu-id="cc45a-105">If there is no accessible constructor in the base class that can be called without arguments, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot generate an implicit call.</span></span> <span data-ttu-id="cc45a-106">В этом случае необходимый конструктор помечается атрибутом <xref:System.ObsoleteAttribute> , и поэтому [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не может вызвать его.</span><span class="sxs-lookup"><span data-stu-id="cc45a-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot call it.</span></span>  
  
 <span data-ttu-id="cc45a-107">Вы можете пометить любой программный элемент как неиспользуемый, применив к нему атрибут <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="cc45a-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="cc45a-108">Если вы это сделаете, вы можете задать для свойства <xref:System.ObsoleteAttribute.IsError%2A> атрибута значение `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="cc45a-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="cc45a-109">Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку.</span><span class="sxs-lookup"><span data-stu-id="cc45a-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="cc45a-110">Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.</span><span class="sxs-lookup"><span data-stu-id="cc45a-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="cc45a-111">**Идентификатор ошибки:** BC30920</span><span class="sxs-lookup"><span data-stu-id="cc45a-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cc45a-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cc45a-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="cc45a-113">Проверьте указанное сообщение об ошибке и выполните соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="cc45a-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="cc45a-114">Включите вызов `MyBase.New()` или `MyClass.New()` в качестве первого оператора `Sub New` в производном классе.</span><span class="sxs-lookup"><span data-stu-id="cc45a-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc45a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="cc45a-115">See Also</span></span>  
 [<span data-ttu-id="cc45a-116">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="cc45a-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
