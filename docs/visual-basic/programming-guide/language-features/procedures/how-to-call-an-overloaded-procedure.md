---
title: "Практическое руководство: вызов перегруженной процедуры (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, overloading
- procedures, calling
- procedures, multiple versions
- procedure calls, overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 0da83aa63bf013d841f2a01a535726f3b03497a1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Практическое руководство. Вызов перегруженной процедуры (Visual Basic)
Преимущество перегрузки процедуры заключается в гибкости вызова. Вызывающий код может получить сведения, необходимые для передачи в процедуру и затем вызвать одну процедуры по имени, независимо от того, какие аргументы она передает.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Для вызова процедуры, которая имеет определенные более одной версии  
  
1.  В вызывающем коде определите, какие данные необходимо передать в процедуру.  
  
2.  Создайте вызов процедуры обычным способом, представляя данные в списке аргументов. Убедитесь, что аргументы соответствуют списку параметров в одной из версий, определенные для процедуры.  
  
3.  Необходимо определить, какую версию процедуры необходимо вызвать. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]передает управление версию, которая соответствует списку аргументов.  
  
     В следующем примере вызывается `post` объявление процедуры в [как: определить несколько версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md). Она получает идентификатор клиента, определяет, является ли он `String` или `Integer`, а затем в любом случае вызывает ту же процедуру.  
  
     [!code-vb[VbVbcnProcedures&#56;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures&#57;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)   
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)   
 [Перегрузка процедур](./procedure-overloading.md)   
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)   
 [Практическое руководство: определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Практическое руководство: перегрузка процедуры, которая принимает необязательные параметры](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Практическое руководство: перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)   
 [Разрешение перегрузки](./overload-resolution.md)   
 [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)
