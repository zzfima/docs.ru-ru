---
title: Практическое руководство. Объединение данных с помощью LINQ с использованием соединений (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: f0279cc13e938b6f7853ef11fee1ef046f192316
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653459"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Практическое руководство. Объединение данных с помощью LINQ с использованием соединений (Visual Basic)
Visual Basic предоставляет `Join` и `Group Join` для объединения содержимого нескольких коллекций на основе общих значений между коллекциями предложения запроса. Эти значения называются *ключ* значения. Разработчики, знакомые с понятиями реляционной базы данных будет распознавать `Join` предложение INNER JOIN и `Group Join` предложение as, по сути, ЛЕВОЕ ВНЕШНЕЕ соединение.  
  
 Примеры в этом разделе демонстрируют несколько способов объединения данных с помощью `Join` и `Group Join` предложения запроса.  
  
## <a name="create-a-project-and-add-sample-data"></a>Создание проекта и добавление демонстрационных данных  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Создание проекта, который содержит образец данных и типы  
  
1.  Для выполнения примеров в этом разделе, откройте Visual Studio и добавьте новый проект консольного приложения Visual Basic. Дважды щелкните файл Module1.vb, созданными Visual Basic.  
  
2.  Образцы в этом разделе используют `Person` и `Pet` типы и данные из следующего примера кода. Скопируйте этот код в значение по умолчанию `Module1` модуля, созданного в Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Выполнение внутреннего соединения с помощью предложения Join  
 ВНУТРЕННЕЕ соединение объединяет данные из двух коллекций. Будут включены элементы, для которых указанные ключевые значения совпадают. Все элементы из любой коллекции, у которых нет соответствующего элемента в другой коллекции, исключаются.  
  
 В Visual Basic LINQ предоставляет два параметра для выполнения внутреннего СОЕДИНЕНИЯ: неявное соединение и явное соединение.  
  
 Неявное соединение задает коллекции для объединения в `From` предложения и определяет соответствующие ключевые поля в `Where` предложения. Visual Basic неявно объединяет две коллекции, основанные на указанных ключевых полях.  
  
 Явное соединение можно указать с помощью `Join` предложения, если требуется явно указать, какие ключевые поля использовать для объединения. В этом случае `Where` предложение по-прежнему может использоваться для фильтрации результатов запроса.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Для выполнения Inner Join с помощью предложения Join  
  
1.  Добавьте следующий код в `Module1` модуль проекта, чтобы просмотреть примеры явных и неявных внутреннее соединение.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Выполните левое внешнее соединение, используя предложение Group Join  
 ЛЕВОЕ ВНЕШНЕЕ соединение включает все элементы из коллекции слева, соединения и только совпадающие значения из коллекции правой стороны соединения. Все элементы из коллекции правой стороны соединения, у которых нет соответствующего элемента коллекции слева, исключаются из результата запроса.  
  
 `Group Join` Предложение выполняет, в сущности, ЛЕВОЕ ВНЕШНЕЕ соединение. Разница между обычно называемое ЛЕВОЕ ВНЕШНЕЕ соединение и что `Group Join` предложение возвращает значение, которое `Group Join` результаты предложения группы из коллекции правой стороны соединения для каждого элемента коллекции слева. В реляционной базе данных ЛЕВОЕ ВНЕШНЕЕ соединение возвращает несгруппированные результат, в котором каждый элемент в запросе привести содержит совпадающие элементы из обеих коллекций в соединении. В этом случае элементы из коллекции слева соединения повторяются для каждого соответствующего элемента из коллекции правой стороны. Вы увидите, как это выглядит после выполнения следующей процедуры.  
  
 Можно получить результаты `Group Join` запроса в виде несгруппированные результата, расширяя запрос, чтобы возвращался для каждого сгруппированного результата запроса. Чтобы сделать это, необходимо убедиться, что запрос на `DefaultIfEmpty` метод сгруппированной коллекции. Это гарантирует, что элементы из коллекции слева соединения по-прежнему включаются в результат запроса, даже если они не имеют совпадающих из коллекции правой. Можно добавить код в запрос для предоставления результирующее значение по умолчанию при отсутствии совпадающих значений из коллекции правой стороны соединения.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Для выполнения левого внешнего соединения с помощью предложения Group Join  
  
1.  Добавьте следующий код для `Module1` модуля проекта, чтобы просмотреть примеры сгруппированного левого внешнего соединения и без группировки левого внешнего соединения.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Выполнение соединения с помощью составного ключа  
 Можно использовать `And` ключевое слово в `Join` или `Group Join` предложение, определяющее несколько ключевых полей для использования при сравнении значений из соединяемых коллекций. `And` Ключевое слово указывает, что все указанные ключевые поля должны соответствовать элементам для объединения.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Для выполнения соединения с помощью составного ключа  
  
1.  Добавьте следующий код в `Module1` модуль проекта, чтобы просмотреть примеры соединения, в которых используется составной ключ.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a>Выполнение кода  
  
#### <a name="to-add-code-to-run-the-examples"></a>Добавление кода для выполнения примеров  
  
1.  Замените `Sub Main` в `Module1` модуля в проекте следующим кодом для выполнения примеров этого раздела.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  Нажмите клавишу F5 для запуска примеров.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [Предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Предложение From](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложения Where](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)  
 [Преобразования данных с помощью LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
