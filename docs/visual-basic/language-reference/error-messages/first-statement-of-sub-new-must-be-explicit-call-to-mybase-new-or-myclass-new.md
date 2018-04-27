---
title: 'Первый оператор &#39;Sub New&#39; должен быть явным вызовом &#39;MyBase.New&#39; или &#39;MyClass.New&#39; из-за &#39; &lt;имя_конструктора&gt; &#39; в базовом классе &#39; &lt;имя_базового_класса&gt; &#39; из &#39; &lt;имя_производного_класса&gt; &#39; помечен как устаревший: &#39; &lt;errormessage&gt;&#39;'
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
ms.openlocfilehash: 7690c9dcdb97e63959d2f0e31791d55ee7b09ffc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="d3f6a-102">Первый оператор &#39;Sub New&#39; должен быть явным вызовом &#39;MyBase.New&#39; или &#39;MyClass.New&#39; из-за &#39; &lt;имя_конструктора&gt; &#39; в базовом классе &#39; &lt;имя_базового_класса&gt; &#39; из &#39; &lt;имя_производного_класса&gt; &#39; помечен как устаревший: &#39; &lt;errormessage&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="d3f6a-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="d3f6a-103">Конструктор класса не вызывает явно конструктор базового класса, а вызванный неявно конструктор базового класса помечается атрибутом <xref:System.ObsoleteAttribute> , что является причиной возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="d3f6a-104">Если конструктор производного класса не вызывает конструктор базового класса, Visual Basic пытается создать неявный вызов конструктора базового класса без параметров.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="d3f6a-105">Если в базовом классе, который может вызываться без аргументов нет доступного конструктора, Visual Basic не может создать неявный вызов.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="d3f6a-106">В этом случае необходимый конструктор помечается <xref:System.ObsoleteAttribute> атрибута, поэтому Visual Basic не может вызвать его.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="d3f6a-107">Вы можете пометить любой программный элемент как неиспользуемый, применив к нему атрибут <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="d3f6a-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="d3f6a-108">Если вы это сделаете, вы можете задать для свойства <xref:System.ObsoleteAttribute.IsError%2A> атрибута значение `True` или `False`.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="d3f6a-109">Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="d3f6a-110">Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="d3f6a-111">**Идентификатор ошибки:** BC30920</span><span class="sxs-lookup"><span data-stu-id="d3f6a-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d3f6a-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d3f6a-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="d3f6a-113">Проверьте указанное сообщение об ошибке и выполните соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="d3f6a-114">Включите вызов `MyBase.New()` или `MyClass.New()` в качестве первого оператора `Sub New` в производном классе.</span><span class="sxs-lookup"><span data-stu-id="d3f6a-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3f6a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d3f6a-115">See Also</span></span>  
 [<span data-ttu-id="d3f6a-116">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="d3f6a-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
