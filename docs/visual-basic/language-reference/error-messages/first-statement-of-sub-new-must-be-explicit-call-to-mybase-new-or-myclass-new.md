---
title: "Первый оператор этого Sub New должен быть явный вызов «MyBase.New» или «MyClass.New», поскольку &quot;&lt;constructorname&gt;«в базовом классе»&lt;baseclassname&gt;«of»&lt;derivedclassname&gt;&quot; помечен как устаревший: &quot;&lt;errormessage&gt;&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30920
- bc30920
dev_langs:
- VB
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d46192bc9a9f2807f56cbdd7bdd4fd21f6c9a7b0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a><span data-ttu-id="629f4-102">Первый оператор этого Sub New должен быть явный вызов «MyBase.New» или «MyClass.New», поскольку "&lt;constructorname&gt;«в базовом классе»&lt;baseclassname&gt;«of»&lt;derivedclassname&gt;" помечен как устаревший: "&lt;errormessage&gt;"</span><span class="sxs-lookup"><span data-stu-id="629f4-102">First statement of this &#39;Sub New&#39; must be an explicit call to &#39;MyBase.New&#39; or &#39;MyClass.New&#39; because the &#39;&lt;constructorname&gt;&#39; in the base class &#39;&lt;baseclassname&gt;&#39; of &#39;&lt;derivedclassname&gt;&#39; is marked obsolete: &#39;&lt;errormessage&gt;&#39;</span></span>
<span data-ttu-id="629f4-103">Конструктор класса не вызывается явно конструктор базового класса и неявный конструктор базового класса помечается <xref:System.ObsoleteAttribute>атрибут и следует рассматривать его как ошибку.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="629f4-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="629f4-104">Если конструктор производного класса не вызывает конструктор базового класса, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] пытается создать неявный вызов конструктора базового класса без параметров.</span><span class="sxs-lookup"><span data-stu-id="629f4-104">When a derived class constructor does not call a base class constructor, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="629f4-105">Если нет доступного конструктора в базовом классе, который может вызываться без аргументов, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не удается создать неявный вызов.</span><span class="sxs-lookup"><span data-stu-id="629f4-105">If there is no accessible constructor in the base class that can be called without arguments, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot generate an implicit call.</span></span> <span data-ttu-id="629f4-106">В этом случае необходимый конструктор помечается <xref:System.ObsoleteAttribute>атрибут, поэтому [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] невозможно вызвать его</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="629f4-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot call it.</span></span>  
  
 <span data-ttu-id="629f4-107">Можно пометить любой элемент программирования как более не используется путем применения <xref:System.ObsoleteAttribute>к его.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="629f4-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="629f4-108">После этого можно задать атрибут <xref:System.ObsoleteAttribute.IsError%2A>значение `True` или `False`.</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="629f4-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="629f4-109">Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку.</span><span class="sxs-lookup"><span data-stu-id="629f4-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="629f4-110">Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.</span><span class="sxs-lookup"><span data-stu-id="629f4-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="629f4-111">**Идентификатор ошибки:** BC30920</span><span class="sxs-lookup"><span data-stu-id="629f4-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="629f4-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="629f4-112">To correct this error</span></span>  
  
1.  <span data-ttu-id="629f4-113">Проверьте указанное сообщение об ошибке и выполните соответствующее действие.</span><span class="sxs-lookup"><span data-stu-id="629f4-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2.  <span data-ttu-id="629f4-114">Сделайте вызов `MyBase.New()` или `MyClass.New()` первым оператором `Sub New` в производном классе.</span><span class="sxs-lookup"><span data-stu-id="629f4-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="629f4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="629f4-115">See Also</span></span>  
 [<span data-ttu-id="629f4-116">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="629f4-116">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
