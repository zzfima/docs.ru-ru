---
title: Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 775c40cbb62272f913297d5a58914a0c82c5a7d7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305316"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)
Инициализаторы объектов позволяют объявлять и создавать экземпляр класса в одной инструкции. Кроме того в то же время можно инициализировать один или несколько членов экземпляра без вызова конструктора с параметрами.  
  
 При использовании инициализатора объекта для создания экземпляра именованного типа, вызывается конструктор по умолчанию для класса, следуют инициализации назначенных членов в указанном порядке.  
  
 Ниже показано, как создать экземпляр `Student` класс тремя разными способами. Класс имеет имя, фамилию и свойства класса год, среди прочего. Каждый из трех объявлений создает новый экземпляр класса `Student`, со свойством `First` задается значение «Michael», свойство `Last` значение «Такер», а все остальные элементы значение к значениям по умолчанию. Результат каждого объявления в процедуре соответствует приведенному ниже, который не используют инициализатора объекта.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Для реализации `Student` , представлена в разделе [как: Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Вы можете скопировать код из этого раздела, чтобы настроить класс и создать список `Student` объектов для работы с.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Для создания объекта именованного класса с помощью инициализатора объектов  
  
1. Объявление начинается, как если бы планировалось использовать конструктор.  
  
     `Dim student1 As New Student`  
  
2. Введите ключевое слово `With`, а затем список инициализации в фигурных скобках.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. В списке инициализации включают каждое свойство, которое необходимо инициализировать и присвойте ему начальное значение. Имя свойства является стоять точка.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     Можно инициализировать один или несколько членов класса.  
  
4. Кроме того можно объявить новый экземпляр класса и присвоить его значение. Сначала объявите экземпляр `Student`:  
  
     `Dim student2 As Student`  
  
5. Начните создание экземпляра `Student` обычным способом.  
  
     `Dim student2 As Student = New Student`  
  
6. Тип `With` и затем инициализатора объекта для инициализации одного или нескольких членов нового экземпляра.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. Можно упростить определение на предыдущем шаге, опустив `As Student`. После этого компилятор определяет, что `student3` является экземпляром класса `Student` , используя вывод локального типа.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Дополнительные сведения см. в разделе [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>См. также

- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Практическое руководство. Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [Инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
