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
ms.openlocfilehash: 4db5d288d79379b677bb19b2eba0d094e0d71bc8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44036409"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Практическое руководство. Объединение данных с помощью LINQ с использованием соединений (Visual Basic)
Visual Basic предоставляет `Join` и `Group Join` для объединения содержимого нескольких коллекций на основе общих значений между коллекциями предложения запроса. Эти значения называются *ключ* значения. Разработчикам, знакомым с понятиями реляционной базы данных будет распознавать `Join` предложение INNER JOIN и `Group Join` предложение as, фактически, ЛЕВОЕ ВНЕШНЕЕ соединение.  
  
 В примерах в этом разделе показано несколько способов объединения данных с помощью `Join` и `Group Join` предложения запроса.  
  
## <a name="create-a-project-and-add-sample-data"></a>Создание проекта и добавление демонстрационных данных  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Чтобы создать проект, содержащий образец данных и типы  
  
1.  Для выполнения примеров этого раздела, откройте Visual Studio и добавьте новый проект консольного приложения Visual Basic. Дважды щелкните файл Module1.vb, созданными Visual Basic.  
  
2.  Примеры в этом разделе используется `Person` и `Pet` типы и данные из следующего примера кода. Скопируйте этот код в значение по умолчанию `Module1` модуля, созданного с Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Выполнение внутреннего соединения с помощью предложения Join  
 ВНУТРЕННЕЕ соединение объединяет данные из двух коллекций. Включены элементы, для которых соответствует указанных значений ключа. Все элементы из любой коллекции, у которых нет соответствующего элемента в другой коллекции, исключаются.  
  
 В Visual Basic LINQ предоставляет два параметра для выполнения внутреннего СОЕДИНЕНИЯ: неявное соединение и явное соединение.  
  
 Неявное соединение задает коллекции для объединения в `From` предложение и определяет соответствующие ключевые поля в `Where` предложение. Visual Basic неявно объединяет две коллекции, на основе указанного ключа полей.  
  
 Явное соединение можно указать с помощью `Join` предложение, если вы хотите явно указать, какие ключевые поля для использования в соединении. В этом случае `Where` предложение по-прежнему может использоваться для фильтрации результатов запроса.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Для выполнения Inner Join с помощью предложения Join  
  
1.  Добавьте следующий код, чтобы `Module1` модуля в проект, чтобы ознакомиться с примерами явные и неявные внутреннее соединение.  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Выполнить левое внешнее соединение, используя предложение Group Join  
 ЛЕВОЕ ВНЕШНЕЕ соединение включает в себя все элементы из коллекции слева от оператора соединения и только совпадающие значения из коллекции правой стороны соединения. Все элементы из коллекции правой части соединения, у которых нет соответствующего элемента в коллекции слева от оператора, исключаются из результата запроса.  
  
 `Group Join` Предложение выполняет, по сути, LEFT OUTER JOIN. Разница между обычно называемое ЛЕВОЕ ВНЕШНЕЕ соединение и что `Group Join` предложение возвращает, является то, что `Group Join` результаты предложения группы из коллекции правой стороны соединения для каждого элемента коллекции слева от оператора. В реляционной базе данных ЛЕВОЕ ВНЕШНЕЕ соединение возвращает результат без группировки, в котором каждый элемент в запросе привести содержит совпадающие элементы из обеих коллекций в соединении. В этом случае элементы из коллекции слева от оператора соединения повторяются для каждого соответствующего элемента из коллекции справа. Вы увидите, как это выглядит после завершения следующей процедуры.  
  
 Результаты можно получить `Group Join` запроса в виде результата без группировки, расширяя запрос для возврата элемента для каждого сгруппированного результата запроса. Чтобы выполнить это, необходимо убедиться, что выполняется запрос для `DefaultIfEmpty` метод сгруппированных коллекции. Это гарантирует, что элементы из коллекции слева от оператора соединения по-прежнему включены в результат запроса, даже если они не имеют совпадающих из коллекции справа. Можно добавить код к запросу для предоставления результирующее значение по умолчанию при отсутствии совпадающих значений из коллекции правой стороны соединения.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Чтобы выполнить левое внешнее соединение, используя предложение Group Join  
  
1.  Добавьте следующий код, чтобы `Module1` модуля проекта, чтобы просмотреть примеры сгруппированного левого внешнего соединения и несгруппированные левого внешнего соединения.  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Выполнение соединения с помощью составного ключа  
 Можно использовать `And` ключевое слово в `Join` или `Group Join` предложение, чтобы определить несколько ключевых полей для использования при сопоставлении значения из соединяемых коллекций. `And` Ключевое слово указывает, что все указанные ключевые поля должны соответствовать элементам для объединения.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Для соединения с помощью составного ключа  
  
1.  Добавьте следующий код, чтобы `Module1` модуль проекта, чтобы просмотреть примеры соединения, в которых используется составной ключ.  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a>Выполните код  
  
#### <a name="to-add-code-to-run-the-examples"></a>Добавление кода для выполнения примеров  
  
1.  Замените `Sub Main` в `Module1` модуля в проекте следующим кодом, чтобы выполнить примеры в этом разделе.  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  Нажмите клавишу F5 для запуска примеров.  
  
## <a name="see-also"></a>См. также  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [Предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Предложение From](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [Предложения Where](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/index.md)  
 [Преобразования данных с помощью LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
