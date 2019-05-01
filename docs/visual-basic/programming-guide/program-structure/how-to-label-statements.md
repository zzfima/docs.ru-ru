---
title: Практическое руководство. Метки операторов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: 69ec8c7625410f140c59ba8dd492dca76857eb96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050444"
---
# <a name="how-to-label-statements-visual-basic"></a>Практическое руководство. Метки операторов (Visual Basic)
Блоки операторов состоят из строк кода, разделенных точкой с запятой. Строки кода, предшествует идентификатор или целое число, называются *с меткой*. Метки операторов используются пометить строку кода для обозначения при использовании операторами, такие как `On Error Goto`.  
  
 Метки могут быть либо допустимые идентификаторы Visual Basic, например те, которые идентифицируют элементы программы, или Целочисленные литералы. Метки должны находиться в начале строки исходного кода и должен быть двоеточие, независимо от того, ли за ним следуют инструкцию в той же строке.  
  
 Компилятор распознает метки, проверяя, совпадает ли начало строки любой идентификатор уже определен. Если этого не произошло, компилятор предполагает, что это метка.  
  
 Метки имеют собственную область объявления и не конфликтуют с другими идентификаторами. Областью метки является тело метода. Объявление метки приоритет двоеточиями.  
  
> [!NOTE]
>  Метки могут использоваться только для исполняемых инструкций внутри методов.  
  
### <a name="to-label-a-line-of-code"></a>Чтобы пометить строку кода  
  
- Поместите идентификатора, за которым следует двоеточие, в начале строки исходного кода.  
  
     Например, приведенный ниже код обозначены как `Jump` и `120`, соответственно:  
  
     [!code-vb[VbVbalrStatements#708](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#708)]  
  
## <a name="see-also"></a>См. также

- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
- [Имена объявленных элементов](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Соглашения о структуре программы и коде](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
