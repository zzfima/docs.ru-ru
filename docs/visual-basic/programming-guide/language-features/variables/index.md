---
title: Переменные
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic]
- values [Visual Basic], storing
ms.assetid: 4cfaa06d-4ae3-4307-897b-cf599dc24caa
ms.openlocfilehash: 26433acea2b98ad0e67b9c35bec4eb8e88f7b7b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352413"
---
# <a name="variables-in-visual-basic"></a>Переменные в Visual Basic
You often have to store values when you perform calculations with Visual Basic. Например, может потребоваться вычислить несколько значений, сравнить их и (в зависимости от результата сравнения) выполнить с ними различные операции. Чтобы сравнить значения, их необходимо сохранить.  
  
## <a name="usage"></a>Использование  
 Visual Basic, just like most programming languages, uses variables for storing values. *Переменная* имеет имя (слово, которое используется для ссылки на содержащееся в переменной значение). Переменная также имеет тип данных (который определяет, какие данные можно хранить в переменной). Переменная может представлять массив, если она должна хранить индексированный набор близко связанных элементов данных.  
  
 Вывод локального типа позволяет объявлять переменные без явного указания типа данных. Вместо этого компилятор выводит тип переменной из типа инициализирующего выражения. Дополнительные сведения см. в разделах [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) и [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
## <a name="assigning-values"></a>Назначение значений  
 Для выполнения вычислений и присвоения результата переменной используются операторы присваивания, как показано в следующем примере.  
  
 [!code-vb[VbVbalrVariables#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#1)]  
  
> [!NOTE]
> В этом примере знак равенства (`=`) является оператором присваивания, а не оператором равенства. Значение присваивается переменной `applesSold`.  
  
 Подробнее см. в разделе [Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md).  
  
## <a name="variables-and-properties"></a>Переменные и свойства  
 Как и переменная, *свойство* соответствует значению, к которому можно получить доступ. Но оно является более сложным, чем переменная. Свойство использует блоки кода, определяющие способ задания и получения его значения. Подробнее см. в разделе [Различия между свойствами и переменными в Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## <a name="see-also"></a>См. также

- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Устранение неполадок, связанных с переменными](../../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
- [Практическое руководство. Запись данных в переменную и их извлечение из переменной](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)
- [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
