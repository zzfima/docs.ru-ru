---
title: Переменные в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: 30baab24c54b5158da53f1ba88206d8f1564ebaf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953337"
---
# <a name="variables-in-visual-basic"></a>Переменные в Visual Basic
При выполнении вычислений с Visual Basic часто приходится сохранять значения. Например, может потребоваться вычислить несколько значений, сравнить их и (в зависимости от результата сравнения) выполнить с ними различные операции. Чтобы сравнить значения, их необходимо сохранить.  
  
## <a name="usage"></a>Использование  
 Visual Basic, как и большинство языков программирования, использует переменные для хранения значений. *Переменная* имеет имя (слово, которое используется для ссылки на содержащееся в переменной значение). Переменная также имеет тип данных (который определяет, какие данные можно хранить в переменной). Переменная может представлять массив, если она должна хранить индексированный набор близко связанных элементов данных.  
  
 Вывод локального типа позволяет объявлять переменные без явного указания типа данных. Вместо этого компилятор выводит тип переменной из типа инициализирующего выражения. Дополнительные сведения см. в разделах [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="assigning-values"></a>Назначение значений  
 Для выполнения вычислений и присвоения результата переменной используются операторы присваивания, как показано в следующем примере.  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> В этом примере знак равенства (`=`) является оператором присваивания, а не оператором равенства. Значение присваивается переменной `applesSold`.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Перемещение данных в переменную](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)и из нее.  
  
## <a name="variables-and-properties"></a>Переменные и свойства  
 Как и переменная, *свойство* соответствует значению, к которому можно получить доступ. Но оно является более сложным, чем переменная. Свойство использует блоки кода, определяющие способ задания и получения его значения. Подробнее см. в разделе [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## <a name="see-also"></a>См. также

- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Устранение неполадок, связанных с переменными](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
- [Практическое руководство. Перемещение данных в переменную и из нее](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
