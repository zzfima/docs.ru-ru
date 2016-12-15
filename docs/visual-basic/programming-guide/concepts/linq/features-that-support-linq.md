---
title: "Visual Basic Features That Support LINQ | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic, LINQ features"
  - "LINQ [Visual Basic], features supporting LINQ"
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
caps.latest.revision: 51
caps.handback.revision: 49
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Visual Basic Features That Support LINQ
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] называют технологию в Visual Basic для поддержки синтаксиса запроса и других новых языковых конструкций непосредственно в языке.  С [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] исчезает необходимость изучать новый язык для запросов к внешним источникам данных.  С помощью Visual Basic можно выполнять запросы к данным в реляционных базах данных, XML\-хранилищах или объектах.  Такая интеграция возможностей запроса в язык позволяет выполнять проверку синтаксических ошибок во время компиляции и строгую типизацию.  Такая интеграция также гарантирует наличие у разработчика большей части знаний, необходимых ему для написания насыщенных и разнообразных запросов в Visual Basic.  
  
 В следующем разделе достаточно подробно описаны конструкции языка? поддерживающие LINQ, что позволяет начать с чтения вводной документации, изучения примеров кода и примеров приложений.  Для получения более подробных пояснений по объединению средств языка для поддержки интегрированных в язык запросов воспользуйтесь ссылками.  Хорошей отправной точкой служит раздел [Пошаговое руководство. Написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## Выражения запросов  
 Выражения запросов в Visual Basic могут быть выражены в декларативном синтаксисе, похожем на SQL или XQuery.  При компиляции синтаксис запроса преобразуется в вызовы методов стандартных операторов запроса, реализованные поставщиком LINQ.  Приложения управляют стандартными операторами запросов, находящимися в области действия, путем указания подходящего пространства имен с помощью директивы `Imports`.  Синтаксис выражения запроса для Visual Basic выглядит следующим образом:  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Дополнительные сведения см. в разделе [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## Неявно типизированные переменные  
 Вместо явного указания типа при объявлении и инициализации переменной можно разрешить компилятору определить и назначить тип.  Это называется *локальным определением типа*.  
  
 Переменные, типы которых определены, строго типизированы, так же, как и переменные с явным указанием типа.  Вывод локального типа работает только при определении локальной переменной внутри тела метода.  Дополнительные сведения см. в разделах [Option Infer \- оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 В следующем примере показан вывод локального типа.  Для использования этого примера необходимо задать для `Option Infer` значение `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 Вывод локального типа также делает возможным создать анонимные типы, описанных далее в этом разделе и не требуются для запроса LINQ.  
  
 В следующем примере LINQ определение типа происходит, если `Option Infer` имеет значение `On` либо `Off`.  Ошибка времени компиляции происходит, если `Option Infer` имеет значение `Off`, а `Option Strict` — значение `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## Инициализаторы объектов  
 Инициализаторы объектов используются в выражениях запроса при создании анонимного типа для хранения результатов запроса.  Они также могут использоваться для инициализации объектов с именованными типами за пределами запросов.  С помощью инициализатора объекта можно инициализировать объект в одной строке без явного вызова конструктора.  Пусть существует класс с именем `Customer`, имеющий открытые свойства `Name`, `Phone` и несколько других свойств. Инициализатор объекта может использоваться следующим образом.  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Дополнительные сведения см. в разделе [Инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## Анонимные типы  
 Анонимные типы предоставляют удобный способ для временной группировки набора свойств в элементе для включения в результат запроса.  Это позволяет выбрать любое сочетание доступных полей в запросе, в любом порядке, без определения именованных типов данных для элемента.  
  
 *Анонимный тип* динамически создается компилятором.  Имя типа назначается компилятором и оно может изменяться при каждой новой компиляции.  Поэтому имя не может использоваться непосредственно.  Анонимные типы инициализируются следующим образом.  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## К методам расширения  
 Методы расширения позволяют добавить методы к типу данных или интерфейсу вне определения.  Эта возможность позволяет, по сути, добавить новые методы в существующие типы без их фактического изменения.  Стандартные операторы запросов являются набором методов расширения, предоставляющих функциональные возможности запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] для любого типа, который реализует <xref:System.Collections.Generic.IEnumerable%601>. Другие расширения <xref:System.Collections.Generic.IEnumerable%601> включают <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A> и <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 Следующий метод расширения добавляет метод печати в класс <xref:System.String>.  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Метод вызывается как обычный метод экземпляра <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Дополнительные сведения см. в разделе [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## Лямбда\-выражения  
 Лямбда\-выражение представляет собой функцию без имени для вычисления и возврата одиночного значения.  В отличие от именованных функций лямбда\-выражение может быть определено и выполнено одновременно.  Следующий пример выводит 4.  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 Можно присвоить определение лямбда\-выражения имени переменной, а затем использовать имя для вызова функции.  Следующий пример выводит 4.  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] лямбда\-выражения лежат в основе многих стандартных операторов запроса.  Компилятор создает лямбда\-выражения для записи вычислений, определенных в основных методах запроса, таких как `Where`, `Select`, `Order By`, `Take While` и других.  
  
 Например, следующий код определяет запрос для возврата всех выпускников из списка студентов.  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 Определение запроса компилируется в код, похожий на приведенный в следующем примере, в котором используются два лямбда\-выражения для определения аргументов для `Where` и `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 Оба варианта могут быть выполнены с помощью цикла `For Each`:  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Дополнительные сведения см. в разделе [Лямбда\-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## См. также  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ и строки](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [C\# Features That Support LINQ](../../../../csharp/programming-guide/concepts/linq/features-that-support-linq.md)   
 [Option Infer \- оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)