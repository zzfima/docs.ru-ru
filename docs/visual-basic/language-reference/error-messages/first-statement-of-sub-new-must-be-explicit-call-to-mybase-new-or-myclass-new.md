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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: feb04d426b7e050b7ad05cdfd4d481172dda3a49
ms.lasthandoff: 03/13/2017

---
# <a name="first-statement-of-this-39sub-new39-must-be-an-explicit-call-to-39mybasenew39-or-39myclassnew39-because-the-39ltconstructornamegt39-in-the-base-class-39ltbaseclassnamegt39-of-39ltderivedclassnamegt39-is-marked-obsolete-39lterrormessagegt39"></a>Первый оператор этого Sub New должен быть явный вызов «MyBase.New» или «MyClass.New», поскольку "&lt;constructorname&gt;«в базовом классе»&lt;baseclassname&gt;«of»&lt;derivedclassname&gt;" помечен как устаревший: "&lt;errormessage&gt;"
Конструктор класса не вызывается явно конструктор базового класса и неявный конструктор базового класса помечается <xref:System.ObsoleteAttribute>атрибут и следует рассматривать его как ошибку.</xref:System.ObsoleteAttribute>  
  
 Если конструктор производного класса не вызывает конструктор базового класса, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] пытается создать неявный вызов конструктора базового класса без параметров. Если нет доступного конструктора в базовом классе, который может вызываться без аргументов, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не удается создать неявный вызов. В этом случае необходимый конструктор помечается <xref:System.ObsoleteAttribute>атрибут, поэтому [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] невозможно вызвать его</xref:System.ObsoleteAttribute>  
  
 Можно пометить любой элемент программирования как более не используется путем применения <xref:System.ObsoleteAttribute>к его.</xref:System.ObsoleteAttribute> После этого можно задать атрибут <xref:System.ObsoleteAttribute.IsError%2A>значение `True` или `False`.</xref:System.ObsoleteAttribute.IsError%2A> Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку. Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.  
  
 **Идентификатор ошибки:** BC30920  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте указанное сообщение об ошибке и выполните соответствующее действие.  
  
2.  Сделайте вызов `MyBase.New()` или `MyClass.New()` первым оператором `Sub New` в производном классе.  
  
## <a name="see-also"></a>См. также  
 [Обзор атрибутов](../../../visual-basic/programming-guide/concepts/attributes/index.md)
 
