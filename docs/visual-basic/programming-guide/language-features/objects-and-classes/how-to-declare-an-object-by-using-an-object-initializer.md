---
title: "Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объявление объектов с помощью инициализатора объекта"
  - "инициализаторы [Visual Basic]"
  - "инициализаторы объекта [Visual Basic]"
  - "практические видеоруководства, Visual Basic"
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Инициализаторы объектов позволяют объявлять и создавать экземпляр класса в одном операторе языка.  Кроме того, можно инициализировать один или несколько членов экземпляра одновременно, не вызывая параметризованный конструктор.  
  
 При использовании инициализатора объекта для создания экземпляра именованного типа для класса вызывается конструктор по умолчанию, за которым следует инициализации назначенных членов в указанном порядке.  
  
 В приведенной ниже процедуре показано, как создать экземпляр класса `Student` тремя различными способами.  Класс имеет среди прочих свойства "имя", "фамилия" и "номер курса".  В каждом из трех объявлений создается новый экземпляр класса `Student`, где для свойства `First` задается значение "Michael", для свойства `Last` — значение "Tucker", а для всех других членов — значения по умолчанию.  Результат каждого объявления в процедуре аналогичен следующему примеру, в котором не используется инициализатор объектов.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 Сведения о реализации класса `Student` см. в разделе [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  Можно скопировать код из этого раздела, чтобы настроить класс и создать список объектов `Student` для работы с ними.  
  
### Создание объекта именованного класса с помощью инициализатора объектов  
  
1.  Начните объявление, как если бы планировалось использовать конструктор.  
  
     `Dim student1 As New Student`  
  
2.  Введите ключевое слово `With`, за которым следует список инициализации в фигурных скобках.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  В списке инициализации укажите каждое свойство, которое требуется инициализировать, и присвойте ему начальное значение.  Имени свойства предшествует точка.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     Можно инициализировать один или несколько членов класса.  
  
4.  Кроме того, можно объявить новый экземпляр класса, а затем присвоить ему значение.  Сначала объявите экземпляр `Student`:  
  
     `Dim student2 As Student`  
  
5.  Начните создание экземпляра класса `Student` обычным способом.  
  
     `Dim student2 As Student = New Student`  
  
6.  Введите `With`, а затем инициализатор объектов для инициализации одного или нескольких членов нового экземпляра.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  Чтобы упростить определение в предыдущем действии, не указывайте `As Student`.  В этом случае компилятор определяет с помощью определения локального типа, что `student3` является экземпляром класса `Student`.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     Дополнительные сведения см. в разделе [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## См. также  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)   
 [Инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)