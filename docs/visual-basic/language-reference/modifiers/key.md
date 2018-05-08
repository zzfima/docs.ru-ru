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
ms.openlocfilehash: 92d54e3135142bc02a17f3ce5ac078a356c139be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
`Key` Ключевое слово позволяет указать поведение свойств анонимных типов. Только свойства, указанные как ключевые свойства, участвуют в проверке равенства между экземплярами анонимного типа, или вычисления значений хэш-кода. Невозможно изменить значения ключевых свойств.  
  
 Укажите свойство анонимного типа как ключевые свойства, поместив ключевое слово `Key` перед ее объявления в списке инициализации. В следующем примере `Airline` и `FlightNo` являются ключевыми, но `Gate` не является.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 При создании нового анонимного типа он наследуется непосредственно от <xref:System.Object>. Компилятор переопределяет три члена, унаследованного: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, и <xref:System.Object.ToString%2A>. Переопределение код, который создается для <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> основан на ключевые свойства. Если нет ключевых свойств в типе, <xref:System.Object.GetHashCode%2A> и <xref:System.Object.Equals%2A> не переопределяются.  
  
## <a name="equality"></a>Равенство  
 Два экземпляра анонимного типа равны, если они являются экземплярами одного типа, и если равны значения их ключевых свойств. В следующих примерах `flight2` равен `flight1` из предыдущего примера, поскольку они являются экземплярами одного анонимного типа и иметь совпадающие значения их ключевых свойств. Тем не менее `flight3` не равно `flight1` , так как он имеет другое значение для ключа свойства `FlightNo`. Экземпляр `flight4` не совпадает с типом `flight1` так, как они назначить различные свойства в качестве свойства ключа.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 Если два экземпляра должны быть объявлены с только неключевыми свойствами, идентичными по имени, типа, порядок и значения, два экземпляра не равны. Экземпляр без ключевого свойства равен только самому себе.  
  
 Дополнительные сведения об условиях, при которых два экземпляра анонимного типа являются экземплярами одного анонимного типа см. в разделе [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Вычисление хэш-кода  
 Как <xref:System.Object.Equals%2A>, хэш-функции, определенные в <xref:System.Object.GetHashCode%2A> для анонимного типа основана на ключевые свойства типа. В следующих примерах показано взаимодействие между ключевыми свойствами и хэш-код значения.  
  
 Экземпляры анонимного типа, имеющие одинаковые значения для всех ключевых свойств иметь значение же хэш-кода, даже если неключевые свойства не имеют совпадающих значений. Следующая инструкция возвращает `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 Экземпляры анонимного типа, имеющие различные значения для одного или нескольких ключевых свойств имеют разные хэш-код значения. Следующая инструкция возвращает `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 Экземпляры анонимных типов, определяющие различные свойства как ключевые свойства не являются экземплярами одного типа. Они имеют разные хэш-код значения даже в том случае, если имена и значения всех свойств совпадают. Следующая инструкция возвращает `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a>Значения, доступные только для чтения  
 Невозможно изменить значения ключевых свойств. Например, в `flight1` в предыдущих примерах, `Airline` и `FlightNo` поля доступны только для чтения, но `Gate` может быть изменено.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a>См. также  
 [Определение анонимного типа](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
