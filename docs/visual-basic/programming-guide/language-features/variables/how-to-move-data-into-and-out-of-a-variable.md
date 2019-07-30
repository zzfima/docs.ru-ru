---
title: Практическое руководство. Перемещение данных в переменную или из нее (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: df55f122c4ea029a383196f8d9684295ac8926aa
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631125"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Практическое руководство. Перемещение данных в переменную или из нее (Visual Basic)

Значение сохраняется в переменной путем размещения имени переменной в левой части оператора присваивания.

## <a name="putting-data-in-a-variable"></a>Помещение данных в переменную

#### <a name="to-store-a-value-in-a-variable"></a>Сохранение значения в переменной

- Используйте имя переменной в левой части оператора присваивания.

    В следующем примере задается значение переменной `alpha`.

    ```vb
    alpha = (beta * 6.27) / (gamma + 2.1)
    ```

    Значение, созданное в правой части оператора присваивания, хранится в переменной.

## <a name="getting-data-from-a-variable"></a>Получение данных из переменной

Значение переменной извлекается путем включения имени переменной в выражение.

#### <a name="to-retrieve-a-value-from-a-variable"></a>Получение значения из переменной

- Используйте имя переменной в выражении. Можно использовать переменную в любом месте, где можно использовать константу или литерал, за исключением выражения, определяющего значение константы.

  \-или-

- Используйте имя переменной после знака равенства (`=`) в операторе присваивания.

  В следующем примере считывается значение переменной `startValue` , а затем используется значение переменной `counter` в выражении.

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  Значение переменной участвует в выражении точно так же, как константа, а затем хранится в переменной или свойстве в левой части оператора присваивания.

## <a name="see-also"></a>См. также

- [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
