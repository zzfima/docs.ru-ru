---
title: Практическое руководство. Вызов перегруженной процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 802a312d6ec6640594f3c6b662202d1ffcf2376d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649130"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Практическое руководство. Вызов перегруженной процедуры (Visual Basic)
Преимущество перегрузки процедуры заключается в гибкости вызова. Вызывающий код может получить сведения, необходимые для передачи в процедуру, а затем вызвать одну процедуры по имени, независимо от того, какие аргументы, она передает.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Вызывать процедуру, которая имеет несколько версий определенных  
  
1.  В вызывающем коде определяют, какие данные будут переданы в процедуре.  
  
2.  Создайте вызов процедуры обычным способом, представляя данные в списке аргументов. Убедитесь, что аргументы соответствуют списку параметров в одной из версий, определенное для этой процедуры.  
  
3.  Необходимо определить, какую версию процедуры необходимо вызвать. Visual Basic передает управление в версию, которая соответствует списку аргументов.  
  
     В следующем примере вызывается `post` объявление процедуры в [как: определить несколько версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md). Она получает идентификатор клиента, определяет, является ли он `String` или `Integer`, а затем в любом случае вызывает ту же процедуру.  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>См. также  
 [Процедуры](./index.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Перегрузка процедур](./procedure-overloading.md)  
 [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)  
 [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)  
 [Разрешение перегрузки](./overload-resolution.md)  
 [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)
