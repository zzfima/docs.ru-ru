---
title: Как выполнить Перемещение данных в действие и из переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 9b34173ebb3226fa00610c124c7b680e18d80de9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717952"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Как выполнить Перемещение данных в действие и из переменной (Visual Basic)
Сохраните значение в переменной, помещая имя переменной в левой части оператора присваивания.  
  
## <a name="putting-data-in-a-variable"></a>Размещение данных в переменной  
  
#### <a name="to-store-a-value-in-a-variable"></a>Для хранения значений в переменной  
  
-   Используйте имя переменной в левой части оператора присваивания.  
  
     В следующем примере значение переменной `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     Значение, созданное в правой части оператора присваивания хранится в переменной.  
  
## <a name="getting-data-from-a-variable"></a>Получение данных из переменной  
 Получить значение переменной, включая имя переменной в выражении.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>Для извлечения значения из переменной  
  
-   Используете имя переменной в выражении. Можно использовать переменную везде, где можно использовать константой или литералом, за исключением в выражение, определяющее значение константы.  
  
     - или -  
  
-   Использовать имя переменной после равенства (`=`) войдите в операторе присваивания.  
  
     В следующем примере считывается значение переменной `startValue` , а затем использует значение переменной `counter` в выражении.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     Значение переменной участвует в выражении, так же, как константа, а затем сохраняется в переменной или свойству в левой части оператора присваивания.  
  
## <a name="see-also"></a>См. также
- [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
