---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 1fa4c1fa0a2def02dd56fa3728a8df4b5ff16b7f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666851"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Указывает, что аргумент передается [по значению](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), поэтому вызываемая процедура или свойство не может изменить значение переменной, которая является базовым аргументом в вызывающем коде. Если модификатор не указан, по умолчанию используется значение ByVal.

> [!NOTE]
> Поскольку это значение по умолчанию, нет необходимости явно указывать `ByVal` ключевое слово в сигнатурах метода. Он, как правило, создает шум и часто ведет к нестандартному `ByRef` ключевому слову.

## <a name="remarks"></a>Примечания
 Модификатор `ByVal` можно использовать в следующих контекстах:

 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a>Пример
 В следующем примере демонстрируется использование `ByVal` механизма передачи параметров с аргументом ссылочного типа. В примере аргумент — это `c1`экземпляр класса. `Class1` `ByVal`запрещает коду в процедурах изменять базовое значение ссылочного аргумента, `c1`, но не защищает доступные поля и `c1`свойства.

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>См. также

- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
