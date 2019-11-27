---
title: Практическое руководство. Вызов перегруженной процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d983f5f6183c33141079ed35171f7a73f254450f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340197"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Практическое руководство. Вызов перегруженной процедуры (Visual Basic)
Преимущество перегрузки процедуры заключается в гибкости вызова. Вызывающий код может получить сведения, необходимые для передачи в процедуру, а затем вызвать одно имя процедуры независимо от передаваемых аргументов.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Вызов процедуры, для которой определено более одной версии  
  
1. В вызывающем коде определите, какие данные должны быть переданы в процедуру.  
  
2. Напишите вызов процедуры обычным способом, предоставляя данные в списке аргументов. Убедитесь, что аргументы соответствуют списку параметров в одной из версий, определенных для процедуры.  
  
3. Не нужно определять, какую версию процедуры нужно вызвать. Visual Basic передает управление версии, соответствующей списку аргументов.  
  
     В следующем примере вызывается процедура `post`, объявленная в разделе [как определить несколько версий процедуры](./how-to-define-multiple-versions-of-a-procedure.md). Он получает идентификатор клиента, определяет, является ли он `String` или `Integer`, а затем в любом случае вызывает одну и ту же процедуру.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
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
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
