---
title: Переменные в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: 9a39c53ea2d57bca379297897d6d4d1b9f7a1a9f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840385"
---
# <a name="variables-in-visual-basic"></a>Переменные в Visual Basic
Часто приходится хранить значения при выполнении вычислений с помощью Visual Basic. Например, может потребоваться вычислить несколько значений, сравнить их и (в зависимости от результата сравнения) выполнить с ними различные операции. Чтобы сравнить значения, их необходимо сохранить.  
  
## <a name="usage"></a>Использование  
 Visual Basic, так же, как и большинство языков программирования, использует переменные для хранения значений. *Переменная* имеет имя (слово, которое используется для ссылки на содержащееся в переменной значение). Переменная также имеет тип данных (который определяет, какие данные можно хранить в переменной). Переменная может представлять массив, если она должна хранить индексированный набор близко связанных элементов данных.  
  
 Вывод локального типа позволяет объявлять переменные без явного указания типа данных. Вместо этого компилятор выводит тип переменной из типа инициализирующего выражения. Дополнительные сведения см. в разделах [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="assigning-values"></a>Назначение значений  
 Для выполнения вычислений и присвоения результата переменной используются операторы присваивания, как показано в следующем примере.  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
>  В этом примере знак равенства (`=`) является оператором присваивания, а не оператором равенства. Значение присваивается переменной `applesSold`.  
  
 Дополнительные сведения см. в разделе [Как Перемещение данных в действие и из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
## <a name="variables-and-properties"></a>Переменные и свойства  
 Как и переменная, *свойство* соответствует значению, к которому можно получить доступ. Но оно является более сложным, чем переменная. Свойство использует блоки кода, определяющие способ задания и получения его значения. Подробнее см. в разделе [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## <a name="see-also"></a>См. также

- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Устранение неполадок, связанных с переменными](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
- [Практическое руководство. Перемещение данных в действие и из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
