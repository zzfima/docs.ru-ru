---
title: Практическое руководство. Объявление объекта с помощью инициализатора объектов
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347127"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)
Инициализаторы объектов позволяют объявлять и создавать экземпляры класса в одной инструкции. Кроме того, можно одновременно инициализировать один или несколько членов экземпляра без вызова параметризованного конструктора.  
  
 При использовании инициализатора объекта для создания экземпляра именованного типа вызывается конструктор без параметров для класса, за которым следует инициализация назначенных членов в указанном порядке.  
  
 В следующей процедуре показано, как создать экземпляр класса `Student` тремя разными способами. У класса есть имя, фамилия и свойства года, кроме других. Каждое из трех объявлений создает новый экземпляр `Student`, где свойству `First` присвоено значение "Michael", свойству `Last` задано значение "Туккер", а всем остальным элементам задаются значения по умолчанию. Результат каждого объявления в процедуре эквивалентен следующему примеру, в котором не используется инициализатор объекта.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Сведения о реализации класса `Student` см. в разделе [как создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Вы можете скопировать код из этого раздела, чтобы настроить класс и создать список объектов `Student` для работы.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Создание объекта именованного класса с помощью инициализатора объекта  
  
1. Начните объявление, как если бы вы планировали использовать конструктор.  
  
     `Dim student1 As New Student`  
  
2. Введите ключевое слово `With`, за которым следует список инициализации в фигурных скобках.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. В списке инициализация Включите каждое свойство, которое необходимо инициализировать, и присвойте ему начальное значение. Имя свойства предшествует точке.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     Можно инициализировать один или несколько членов класса.  
  
4. Кроме того, можно объявить новый экземпляр класса и присвоить ему значение. Сначала объявите экземпляр `Student`:  
  
     `Dim student2 As Student`  
  
5. Начните создание экземпляра `Student` обычным способом.  
  
     `Dim student2 As Student = New Student`  
  
6. Введите `With` и инициализатор объекта для инициализации одного или нескольких членов нового экземпляра.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. Можно упростить определение на предыдущем шаге, опустив `As Student`. В этом случае компилятор определит, что `student3` является экземпляром `Student`, используя вывод локального типа.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Дополнительные сведения см. в разделе [определение локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>См. также

- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Практическое руководство. Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [Инициализаторы объектов. Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
