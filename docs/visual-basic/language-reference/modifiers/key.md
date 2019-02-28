---
title: Key (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 0f4778b69963c7b0df14308b3cb6312555647b92
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967780"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
`Key` Ключевое слово позволяет задать поведение для свойств анонимных типов. Только свойства, указанные как ключевые свойства, участвуют в проверке равенства между экземплярами анонимного типа, или вычисления значений хэш-кода. Невозможно изменить значения свойств ключа.  
  
 Укажите свойство анонимного типа как ключевое свойство, поместив ключевое слово `Key` перед ее объявления в списке инициализации. В следующем примере `Airline` и `FlightNo` являются ключевыми, но `Gate` не является.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 При создании нового анонимного типа, он наследует непосредственно от <xref:System.Object>. Компилятор переопределяет три унаследованных членов: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, и <xref:System.Object.ToString%2A>. Код переопределения, который создается за <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> на основе ключевых свойств. Если нет ключевых свойств в типе, <xref:System.Object.GetHashCode%2A> и <xref:System.Object.Equals%2A> не переопределяются.  
  
## <a name="equality"></a>Равенство  
 Два экземпляра анонимного типа равны, если они являются экземплярами одного типа и значения их свойств ключа равны. В следующих примерах `flight2` равен `flight1` из предыдущего примера, так как они являются экземплярами того же анонимного типа и они имеют соответствующих значений их ключевых свойств. Тем не менее `flight3` не равно `flight1` так как он имеет другое значение для свойства ключа, `FlightNo`. Экземпляр `flight4` не совпадает с типом `flight1` так, как они назначить разные свойства в качестве свойства ключа.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Если два экземпляра объявлены с только неключевыми свойствами, идентичными по имени, типа, порядок и значения, два экземпляра не равны. Экземпляр без ключевого свойства равен только самому себе.  
  
 Дополнительные сведения об условиях, при которых два экземпляра анонимного типа являются экземплярами того же анонимного типа, см. в разделе [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Вычисление хэш-кода  
 Как и <xref:System.Object.Equals%2A>, хэш-функцию, которая определена в <xref:System.Object.GetHashCode%2A> для анонимного типа основана на ключевые свойства типа. Ниже приведены примеры взаимодействие между свойств ключа и хэш-код значения.  
  
 Экземпляры анонимного типа, которые имеют одинаковые значения для всех ключевых свойств имеют же значение хэш-кода, даже если неключевые свойства не имеют совпадающих значений. Следующая инструкция возвращает `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Экземпляры анонимного типа, которые имеют разные значения для одного или нескольких ключевых свойств имеют разные хэш-код значения. Следующая инструкция возвращает `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Экземпляры анонимных типов, определяющие различные свойства, как ключевые свойства не являются экземплярами одного типа. Они имеют разные хэш-код значения, даже в том случае, если имена и значения всех свойств совпадают. Следующая инструкция возвращает `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Значения только для чтения  
 Невозможно изменить значения свойств ключа. Например, в `flight1` в предыдущих примерах, `Airline` и `FlightNo` поля доступны только для чтения, но `Gate` можно изменить.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>См. также
- [Определение анонимного типа](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
