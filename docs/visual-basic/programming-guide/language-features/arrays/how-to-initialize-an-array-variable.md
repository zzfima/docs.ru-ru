---
title: Практическое руководство. Инициализация переменной массива в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 4ce2e061c5f523fae3020b08034875422a0062a7
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50170176"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>Практическое руководство. Инициализация переменной массива в Visual Basic
Инициализация переменной массива путем включения литерала массива в `New` предложения и задание начальных значений массива. Можно указать тип или разрешить его наследование от значений в литерале массива. Дополнительные сведения о том, как определить тип, см. в разделе «Заполнение массива начальными значениями» в [массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>Инициализация переменной массива с помощью литерала массива  
  
-   В `New` предложения, или когда вы присваиваете значение массива, значения элементов внутри фигурных скобок (`{}`). В следующем примере показано несколько способов объявить, создать и инициализировать переменную, должна содержать массив, который содержит элементы типа `Char`.  
  
     [!code-vb[VbVbalrArrays#16](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_1.vb)]  
  
     После выполнения каждого из операторов, созданный массив имеет длину 3, и элементы с индексом 0 до 2 содержат начальные значения. Если указать верхнюю границу и значения, необходимо включить значение для каждого элемента от индекса 0 до верхней границы.  
  
     Обратите внимание, что не нужно указывать индекс верхней границы в том случае, если указываются значения элементов в литерале массива. Если верхняя граница не указан, размер массива выводится на основе числа значений в литерале массива.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>Инициализация переменной многомерного массива с помощью литералов массива  
  
-   Поместите значения в фигурные скобки (`{}`) в фигурных скобках. Убедитесь, что вложенные литералы массива все подразумевают массивы одного типа и длины. В следующем примере кода показано несколько примеров инициализации многомерного массива.  
  
     [!code-vb[VbVbalrArrays#17](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_2.vb)]  
  
-   Можно явно задать границы массива или не указывать их и компилятор выведет границы массива, на основе значений в литерале массива. Если указать и верхние границы и значения, необходимо включить значение для каждого элемента от индекса 0 до верхней границы каждого измерения. В следующем примере показано несколько способов объявить, создать и инициализировать переменную, должна содержать двухмерный массив, который содержит элементы типа `Short`  
  
     [!code-vb[VbVbalrArrays#18](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_3.vb)]  
  
     После выполнения каждого из операторов созданный массив содержит шесть инициализированных элементов с индексами `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)`, и `(1,2)`. Каждое место массива содержит значение `10`.  
  
-   Следующий пример выполняет перебор многомерного массива. В консольном приложении Windows, написанного на Visual Basic, вставьте в него код `Sub Main()` метод. Последние комментарии показывают результат.  
  
     [!code-vb[VbVbalrArrays#31](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_4.vb)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>Для инициализации переменной массива массивов с помощью литералов массива  
  
-   Поместите значения объектов в фигурные скобки (`{}`). Несмотря на то, что можно также вложить литералы массива, задающие массивы разной длины, в случае массива массивов следует убедиться, что вложенные литералы массива заключены в круглые скобки (`()`). Скобки задают принудительное вычисление вложенных литералов массива, а результирующие массивы используются как начальные значения массива массивов. В следующем примере кода показаны два примера инициализации массива массивов.  
  
     [!code-vb[VbVbalrArrays#19](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_5.vb)]  
  
-   Приведенный ниже пример проходит через массив массивов. В консольном приложении Windows, написанного на Visual Basic, вставьте в него код `Sub Main()` метод.  Последние комментарии в коде показывают результат.  
  
     [!code-vb[VbVbalrArrays#32](../../../../visual-basic/programming-guide/language-features/arrays/codesnippet/VisualBasic/how-to-initialize-an-array-variable_6.vb)]  
  
## <a name="see-also"></a>См. также  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Устранение неполадок, связанных с массивами](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
