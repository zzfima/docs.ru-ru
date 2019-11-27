---
title: Практическое руководство. Запись данных в переменную и их извлечение из переменной
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: bc5a7377a5e2e4c7ebe7291fd5f0093c4d6e996d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346893"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Практическое руководство. Запись данных в переменную и их извлечение из переменной (Visual Basic)

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

  В следующем примере считывается значение переменной `startValue` а затем в выражении используется значение переменной `counter`.

  ```vb
  counter = startValue
  cellValue = (counter + 5) ^ 2
  ```

  Значение переменной участвует в выражении точно так же, как константа, а затем хранится в переменной или свойстве в левой части оператора присваивания.

## <a name="see-also"></a>См. также

- [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
