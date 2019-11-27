---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: a96f871c6ce119f65ebbec54fdb1471ae105d504
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351586"
---
# <a name="byval-visual-basic"></a>ByVal (Visual Basic)
Указывает, что аргумент передается [по значению](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), поэтому вызываемая процедура или свойство не может изменить значение переменной, которая является базовым аргументом в вызывающем коде. Если модификатор не указан, по умолчанию используется значение ByVal.

> [!NOTE]
> Поскольку это значение по умолчанию, нет необходимости явно указывать ключевое слово `ByVal` в сигнатурах метода. Он, как правило, создает шум и часто приводит к нестандартному ключевому слову `ByRef`.

## <a name="remarks"></a>Примечания
 Модификатор `ByVal` можно использовать в следующих контекстах:

 [Оператор Declare](../../../visual-basic/language-reference/statements/declare-statement.md)

 [Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [Оператор Statement](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [Оператор Sub](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a>Пример
 В следующем примере демонстрируется использование механизма передачи параметров `ByVal` с аргументом ссылочного типа. В примере аргумент имеет `c1`, экземпляр класса `Class1`. `ByVal` не позволяет коду в процедурах изменять базовое значение ссылочного аргумента, `c1`, но не защищает доступные поля и свойства `c1`.

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>См. также

- [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md)
- [Передача аргументов по значению и по ссылке](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
