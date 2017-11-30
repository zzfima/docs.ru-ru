---
title: "Практическое руководство. Запись данных в переменную и их извлечение из переменной (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a>Практическое руководство. Запись данных в переменную и их извлечение из переменной (Visual Basic)
Сохраните значение в переменной, помещая имя переменной слева от оператора присваивания.  
  
## <a name="putting-data-in-a-variable"></a>Размещение данных в переменной  
  
#### <a name="to-store-a-value-in-a-variable"></a>Для хранения значений в переменной  
  
-   Используйте имя переменной в левой части оператора присваивания.  
  
     В следующем примере задается значение переменной `alpha`.  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     Значение, созданное в правой части оператора присваивания, хранится в переменной.  
  
## <a name="getting-data-from-a-variable"></a>Получение данных из переменной  
 Получить значение переменной, включая имя переменной в выражении.  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a>Для извлечения значения из переменной  
  
-   Используйте имя переменной в выражении. Можно использовать переменную везде, где можно использовать константу или литерал, за исключением в выражение, определяющее значение константы.  
  
     -или-  
  
-   Используйте имя переменной после равенства (`=`) войти в операторе присваивания.  
  
     В следующем примере считывается значение переменной `startValue` , а затем использует значение переменной `counter` в выражении.  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     Значение переменной участвует в выражении так же, как константа, и затем сохраняются в переменной или свойстве в левой части оператора присваивания.  
  
## <a name="see-also"></a>См. также  
 [Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
