---
title: Раздел
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 92c8809779d6cab524f67ee47f355b72ab152403
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351507"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)
Ключевое слово `Key` позволяет указать поведение свойств анонимных типов. Только свойства, указанные в качестве ключевых свойств, участвуют в тестах равенства между экземплярами анонимного типа или вычислении значений хэш-кода. Значения ключевых свойств нельзя изменить.  
  
 Вы назначаете свойство анонимного типа в качестве ключевого свойства, помещая ключевое слово `Key` перед его объявлением в списке инициализации. В следующем примере `Airline` и `FlightNo` являются ключевыми свойствами, а `Gate` — нет.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 При создании нового анонимного типа он наследуется непосредственно от <xref:System.Object>. Компилятор переопределяет три наследуемых члена: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>и <xref:System.Object.ToString%2A>. Код переопределения, созданный для <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A>, основан на ключевых свойствах. Если в типе отсутствуют ключевые свойства, <xref:System.Object.GetHashCode%2A> и <xref:System.Object.Equals%2A> не переопределяются.  
  
## <a name="equality"></a>Равенство  
 Два экземпляра анонимных типов равны, если они являются экземплярами одного типа и если значения их ключевых свойств равны. В следующих примерах `flight2` равно `flight1` из предыдущего примера, так как они являются экземплярами одного и того же анонимного типа и имеют совпадающие значения для их ключевых свойств. Однако `flight3` не равно `flight1`, так как имеет другое значение для свойства ключа, `FlightNo`. Тип `flight4` экземпляра отличается от `flight1`, так как они обозначают различные свойства в качестве ключевых свойств.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Если два экземпляра объявляются только с неключевыми свойствами, идентичными в имени, типе, порядке и значении, два экземпляра не равны. Экземпляр без ключевых свойств равен только самому себе.  
  
 Дополнительные сведения об условиях, при которых два экземпляра анонимных типов являются экземплярами одного и того же анонимного типа, см. в разделе [анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Вычисление хэш-кода  
 Как и <xref:System.Object.Equals%2A>, хэш-функция, определенная в <xref:System.Object.GetHashCode%2A> для анонимного типа, основана на ключевых свойствах типа. В следующих примерах показано взаимодействие между ключевыми свойствами и значениями хэш-кода.  
  
 Экземпляры анонимного типа, имеющие одинаковые значения для всех ключевых свойств, имеют одинаковое значение хэш-кода, даже если неключевые свойства не имеют совпадающих значений. Следующая инструкция возвращает `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Экземпляры анонимного типа, имеющие разные значения для одного или нескольких ключевых свойств, имеют разные значения хэш-кода. Следующая инструкция возвращает `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Экземпляры анонимных типов, которые обозначают различные свойства в качестве ключевых свойств, не являются экземплярами одного типа. Они имеют разные значения хэш-кода, даже если имена и значения всех свойств одинаковы. Следующая инструкция возвращает `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Значения только для чтения  
 Значения ключевых свойств нельзя изменить. Например, в `flight1` в предыдущих примерах поля `Airline` и `FlightNo` доступны только для чтения, но можно изменить `Gate`.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>См. также

- [Определение анонимного типа](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
