---
title: Возможности Visual Basic, поддерживающие LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: db2eff2f7c19a3c510e7b212f5bb406d7a885439
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199151"
---
# <a name="visual-basic-features-that-support-linq"></a>Возможности Visual Basic, поддерживающие LINQ
Имя [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] относится к технологии в Visual Basic, что для поддержки синтаксиса запроса, так и для других языковых конструкций на языке. С помощью [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], нет необходимости изучать новый язык для запросов к внешнему источнику данных. Выполнять запросы к данным в реляционных базах данных, хранилища XML или объектов с помощью Visual Basic. Такая интеграция возможностей запроса в язык позволяет проверки во время компиляции для синтаксических ошибок и безопасность типов. Такая интеграция также гарантирует, что вы уже известна большая часть нужно знать для написания насыщенных и разнообразных запросов в Visual Basic.  
  
 В следующих разделах языковых конструкций, которые поддерживают LINQ достаточно подробно, чтобы можно было приступить к работе в режиме чтения вступительная документация, примеры кода и образцов приложений. Можно также щелкнуть ссылки на содержатся более подробные пояснения как возможности языка, объединяются в целях включить запросы LINQ. Лучше всего запустить [Пошаговое руководство: написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Выражения запросов  
 Выражения запросов в Visual Basic может выражаться в декларативный синтаксис, похожий на SQL или XQuery. Во время компиляции синтаксис запроса преобразуется в вызовы методов к реализации поставщика LINQ методы стандартных операторов запросов расширения. Приложения управляют стандартных операторов запроса находятся в области действия, указав соответствующее пространство имен с `Imports` инструкции. Синтаксис выражения запроса Visual Basic выглядит следующим образом:  
  
 [!code-vb[VbLINQVbFeatures#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_1.vb)]  
  
 Дополнительные сведения см. в разделе [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Неявно типизированные переменные  
 Вместо явного задания типа при объявлении и инициализации переменной, вы можете включить компилятору определить и назначить тип. Это называется *вывод локального типа*.  
  
 Переменные, которые выводятся, типы которых являются строго типизированными, так же, как переменные, тип которого указывается явным образом. Вывод локального типа работает только в том случае, при определении локальной переменной внутри тела метода. Дополнительные сведения см. в разделе [оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) и [вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
 В следующем примере вывод локального типа. Чтобы использовать этот пример, необходимо задать `Option Infer` для `On`.  
  
 [!code-vb[VbLINQVbFeatures#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_2.vb)]  
  
 Вывод локального типа также делает возможным создание анонимных типов, которые описаны далее в этом разделе и необходимы для запросов LINQ.  
  
 В следующем примере LINQ, вывод типа происходит, если `Option Infer` либо `On` или `Off`. Ошибка времени компиляции возникает, если `Option Infer` — `Off` и `Option Strict` является `On`.  
  
 [!code-vb[VbLINQVbFeatures#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_3.vb)]  
  
## <a name="object-initializers"></a>Инициализаторы объектов  
 Инициализаторы объектов используются в выражениях запросов при необходимости создать анонимный тип для хранения результатов запроса. Они также могут использоваться для инициализации объектов с именованными типами за пределами запросов. С помощью инициализатора объектов, можно инициализировать объект в одной строке без явного вызова конструктора. Предположим, что у вас есть класс с именем `Customer` , имеющий открытые `Name` и `Phone` свойства, вместе с другими свойствами, можно использовать инициализатор объекта таким образом:  
  
 [!code-vb[VbLINQVbFeatures#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_4.vb)]  
  
 Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Анонимные типы  
 Анонимные типы обеспечивают удобный способ временной группировки набора свойств в элемент, который требуется включить в результат запроса. Это позволяет выбрать любое сочетание доступных полей в запросе, в любом порядке, без определения именованного типа данных для элемента.  
  
 *Анонимного типа* динамически создается компилятором. Имя типа назначается компилятором, и он может измениться при каждой новой компиляции. Таким образом имя не может использоваться непосредственно. Анонимные типы инициализируются следующим образом:  
  
 [!code-vb[VbLINQVbFeatures#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_5.vb)]  
  
 Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Методы расширения  
 Методы расширения позволяют добавлять методы к типу данных или интерфейсу вне определения. Эта функция позволяет, по сути, добавить новые методы в существующий тип фактически не изменяя тип. Стандартные операторы запросов сами представляют собой набор методов расширения, предоставляющих [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] функциональность запросов для любого типа, реализующего <xref:System.Collections.Generic.IEnumerable%601>. Другие расширения для <xref:System.Collections.Generic.IEnumerable%601> включают <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, и <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 Следующий метод расширения добавляет метод печати для <xref:System.String> класса.  
  
 [!code-vb[VbLINQVbFeatures#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_6.vb)]  
  
 Как и обычный метод экземпляра вызывается метод <xref:System.String>:  
  
 [!code-vb[VbLINQVbFeatures#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_7.vb)]  
  
 Дополнительные сведения см. в статье [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Лямбда-выражения  
 Лямбда-выражения является функцией без имени, которая вычисляет и возвращает одиночное значение. В отличие от именованных функций лямбда-выражение может быть определен и выполнена в то же время. В следующем примере отображается 4.  
  
 [!code-vb[VbLINQVbFeatures#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_8.vb)]  
  
 Можно назначить определения лямбда-выражения в имени переменной и затем использовать имя для вызова функции. Следующий пример выводит 4.  
  
 [!code-vb[VbLINQVbFeatures#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_9.vb)]  
  
 В [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], лямбда-выражения лежат в основе многих стандартных операторов запроса. Компилятор создает лямбда-выражения для записи вычислений, которые определены в основных методах запроса, таких как `Where`, `Select`, `Order By`, `Take While`и другие.  
  
 Например следующий код определяет запрос, возвращающий все выпускников из списка студентов.  
  
 [!code-vb[VbLINQVbFeatures#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_10.vb)]  
  
 Определение запроса компилируется в код, аналогичный приведенному ниже, который использует два лямбда-выражения для определения аргументов для `Where` и `Select`.  
  
 [!code-vb[VbLINQVbFeatures#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_11.vb)]  
  
 Любой из версий, которые могут выполняться с помощью `For Each` цикла:  
  
 [!code-vb[VbLINQVbFeatures#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/features-that-support-linq_12.vb)]  
  
 Дополнительные сведения см. в разделе [Лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>См. также  
 [Синтаксис LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [LINQ и строки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
