---
title: "Возможности Visual Basic, поддерживающие LINQ | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3bca15a07a88195589b9c9de5f9842eea42912f1
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-features-that-support-linq"></a>Возможности Visual Basic, поддерживающие LINQ
Имя [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] называют технологию в Visual Basic, поддержки синтаксиса запроса и других новых языковых конструкций непосредственно в языке. С [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], нет необходимости изучать новый язык для запросов к внешнему источнику данных. Выполнять запросы к данным в реляционных базах данных, хранилища XML или объекты с помощью Visual Basic. Такая интеграция возможностей запроса в язык включает проверку ошибок синтаксиса и безопасность типов во время компиляции. Такая интеграция также гарантирует, что знаете, большая часть нужно знать для написания насыщенных и разнообразных запросов в Visual Basic.  
  
 В следующих разделах описаны языковые конструкции, которые поддерживают LINQ достаточно подробно, чтобы вы могли начать с чтения вводной документация, примеры и образцы приложений. Можно также щелкнуть ссылок, чтобы найти более подробные пояснения о возможности языка совокупности интегрированный язык запросов. Является неплохим началом [Пошаговое руководство: написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Выражения запросов  
 Выражения запросов в Visual Basic могут быть выражены в декларативном синтаксисе, похожем на SQL или XQuery. Во время компиляции синтаксис запроса преобразуется в вызовы методов для реализации методов стандартных операторов запросов расширения поставщика LINQ. Приложения управляют стандартных операторов запроса находятся в области действия, путем указания соответствующего пространства имен с `Imports` инструкции. Синтаксис выражения запроса Visual Basic выглядит следующим образом:  
  
 [!code-vb[VbLINQVbFeatures&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Дополнительные сведения см. в разделе [введения в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Неявно типизированные переменные  
 Вместо явного задания типа при объявлении и инициализации переменной, можно разрешить компилятору определить и назначить тип. Это называется *вывод локального типа*.  
  
 Переменные, типы которых выводятся строго типизированы, так же, как переменные, необходимо явно указать тип. Вывод локального типа работает только при определении локальной переменной внутри тела метода. Дополнительные сведения см. в разделе [Option Infer оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 В следующем примере показано определение локального типа. Чтобы использовать этот пример, необходимо установить `Option Infer` в `On`.  
  
 [!code-vb[VbLINQVbFeatures&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 Вывод локального типа также дает возможность создавать анонимные типы, которые описаны далее в этом разделе и необходимых для запросов LINQ.  
  
 В следующем примере LINQ определение типа происходит, если `Option Infer` либо `On` или `Off`. Ошибка времени компиляции возникает, если `Option Infer` — `Off` и `Option Strict` — `On`.  
  
 [!code-vb[VbLINQVbFeatures&#3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>Инициализаторы объектов  
 Инициализаторы объектов используются в выражениях запросов, когда необходимо создать анонимный тип для хранения результатов запроса. Они также могут использоваться для инициализации объектов с именованными типами за пределами запросов. С помощью инициализатора объектов, можно инициализировать объект в одной строке без явного вызова конструктора. Предположим, что имеется класс с именем `Customer` , имеющий открытые `Name` и `Phone` свойства, вместе с другими свойствами, таким образом можно использовать инициализатор объектов:  
  
 [!code-vb[VbLINQVbFeatures&#4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Анонимные типы  
 Анонимные типы предоставляют удобный способ временной группировки набора свойств в элемент, который требуется включить в результат запроса. Это позволяет выбрать любое сочетание доступных полей в запросе, в любом порядке, без определения именованных типов данных для элемента.  
  
 *Анонимного типа* динамически создается компилятором. Имя типа назначается компилятором и оно может изменяться при каждой новой компиляции. Поэтому имя не может использоваться непосредственно. Анонимные типы инициализируются следующим образом:  
  
 [!code-vb[VbLINQVbFeatures&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Методы расширения  
 Методы расширения позволяют добавлять методы к типу данных или интерфейсу вне определения. Эта возможность позволяет, по сути, добавить новые методы в существующий тип без фактического изменения. Стандартные операторы запросов являются набором методов расширения, обеспечивающие [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] функциональные возможности для любого типа, реализующего <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> запроса Другие расширения <xref:System.Collections.Generic.IEnumerable%601>включают <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>и <xref:System.Linq.Enumerable.Intersect%2A>.</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Union%2A> </xref:System.Linq.Enumerable.Count%2A> </xref:System.Collections.Generic.IEnumerable%601>  
  
 Следующий метод расширения добавляет метод печати в <xref:System.String>класс.</xref:System.String>  
  
 [!code-vb[VbLINQVbFeatures №&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Метод вызывается как обычный метод экземпляра <xref:System.String>:</xref:System.String>  
  
 [!code-vb[VbLINQVbFeatures&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Дополнительные сведения см. в разделе [методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Лямбда-выражения  
 Лямбда-выражения является функцией без имени, которая вычисляет и возвращает одиночное значение. В отличие от именованных функций лямбда-выражение может быть определен и выполняется в то же время. Следующий пример выводит 4.  
  
 [!code-vb[VbLINQVbFeatures №&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 Можно присвоить определение лямбда-выражения имени переменной и затем использовать имя для вызова функции. Следующий пример выводит 4.  
  
 [!code-vb[VbLINQVbFeatures&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], лямбда-выражения лежат в основе многих стандартных операторов запроса. Компилятор создает лямбда-выражения для записи вычислений, определенных в основных методах запроса, таких как `Where`, `Select`, `Order By`, `Take While`и др.  
  
 Например следующий код определяет запрос, который возвращает всех выпускников из списка студентов.  
  
 [!code-vb[VbLINQVbFeatures №&9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 Определение запроса компилируется в код, аналогичный приведенному ниже, который использует два лямбда-выражения для определения аргументов для `Where` и `Select`.  
  
 [!code-vb[VbLINQVbFeatures&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 Любой из версий, которые можно выполнять с помощью `For Each` цикла:  
  
 [!code-vb[VbLINQVbFeatures&11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Дополнительные сведения см. в разделе [лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>См. также  
 [Интегрированный в язык запрос (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)   
 [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
