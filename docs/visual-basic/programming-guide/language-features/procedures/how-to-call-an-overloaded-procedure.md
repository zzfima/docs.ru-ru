---
title: Как выполнить Вызов перегруженной процедуры (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 8320bc550c818fd2bea53f75107709eab8456096
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706421"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Как выполнить Вызов перегруженной процедуры (Visual Basic)
Преимущество перегрузки процедуры заключается в гибкости вызова. Вызывающий код может получить информацию, которую необходимо передать в процедуру, а затем вызвать одну процедуры по имени, независимо от того, какие аргументы, она передает.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Для вызова процедуры, которая имеет более одной версии определенные  
  
1.  В вызывающем коде определите, какие данные, передаваемые в процедуру.  
  
2.  Создайте вызов процедуры обычным способом, представляя данные в списке аргументов. Убедитесь, что аргументы совпадает со списком параметров в одной из версий, определенные для процедуры.  
  
3.  У вас нет определить, какую версию для вызова процедуры. Visual Basic передает управление версию, которая соответствует списку аргументов.  
  
     В следующем примере вызывается `post` объявление процедуры в [как: Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md). Она получает идентификатор клиента, определяет, является ли `String` или `Integer`, а затем в любом случае вызывает ту же процедуру.  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>См. также
- [Процедуры](./index.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Перегрузка процедур](./procedure-overloading.md)
- [Рекомендации по устранению неполадок](./troubleshooting-procedures.md)
- [Практическое руководство. Определение различных версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md)
- [Практическое руководство. Перегрузка процедуры, которая принимает один необязательный параметр](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Практическое руководство. Перегрузка процедуры, принимающей неопределенное число параметров](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Вопросы, связанные с перегрузкой процедур](./considerations-in-overloading-procedures.md)
- [Разрешение перегрузки](./overload-resolution.md)
- [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)
