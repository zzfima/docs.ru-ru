---
title: Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 3a372ba91377b53c87c05976e416ca8ed55ccbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)
Инициализаторы объектов позволяют объявлять и создавать экземпляр класса в одной инструкции. Кроме того можно инициализировать один или несколько членов экземпляра одновременно, без вызова конструктора с параметрами.  
  
 При использовании инициализатора объекта для создания экземпляра именованного типа, вызывается конструктор по умолчанию для класса, следуют инициализации назначенных членов в указанном порядке.  
  
 Ниже показано, как создать экземпляр `Student` класс тремя разными способами. Класс имеет имя, фамилию и год свойства класса, в частности. Каждый из трех объявлений создается новый экземпляр `Student`, со свойством `First` задается значение «Michael», свойство `Last` значение «Tucker», а других членов в значения по умолчанию. В следующем примере, в котором не используется инициализатор объекта соответствует результат каждого объявления в процедуре.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 Для реализации `Student` см. в описании [как: создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Можно скопировать код из этого раздела, чтобы настроить класс и создать список `Student` объектов для работы с.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Для создания объекта именованного класса с помощью инициализатора объектов  
  
1.  Начните объявление, как если бы планировалось использовать конструктор.  
  
     `Dim student1 As New Student`  
  
2.  Введите ключевое слово `With`, а затем список инициализации в фигурных скобках.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  В списке инициализации укажите каждое свойство, который будет инициализировать и присвойте ему начальное значение. Имя свойства предшествует периодом.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     Можно инициализировать один или несколько членов класса.  
  
4.  Кроме того можно объявить новый экземпляр класса и назначьте ему значение. Сначала объявите экземпляр `Student`:  
  
     `Dim student2 As Student`  
  
5.  Начать создание экземпляра `Student` обычным способом.  
  
     `Dim student2 As Student = New Student`  
  
6.  Тип `With` и затем инициализатора объекта для инициализации одного или нескольких членов нового экземпляра.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  Упростить определение на предыдущем шаге, не указывайте `As Student`. После этого компилятор определяет, что `student3` является экземпляром класса `Student` с помощью локального определения типов.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     Дополнительные сведения см. в разделе [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>См. также  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Практическое руководство. Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [Инициализаторы объектов. Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
