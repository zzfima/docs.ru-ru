---
title: Инструкции. Объединение данных с помощью LINQ с использованием соединений
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
ms.openlocfilehash: 7279908c5d262b65f4c4da9cd9b6c1b4117bc402
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345004"
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a>Практическое руководство. Объединение данных с помощью LINQ с использованием соединений (Visual Basic)
Visual Basic предоставляет предложения запросов `Join` и `Group Join`, позволяющие объединять содержимое нескольких коллекций на основе общих значений между коллекциями. Эти значения называются значениями *ключа* . Разработчики, знакомые с концепциями реляционных баз данных, распознают предложение `Join` как внутреннее соединение и предложение `Group Join` как, фактически, левое ВНЕШНее соединение.  
  
 Примеры в этом разделе демонстрируют несколько способов объединения данных с помощью предложений запроса `Join` и `Group Join`.  
  
## <a name="create-a-project-and-add-sample-data"></a>Создание проекта и добавление демонстрационных данных  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a>Создание проекта, содержащего образцы данных и типы  
  
1. Чтобы выполнить примеры в этом разделе, откройте Visual Studio и добавьте новый проект Visual Basic консольное приложение. Дважды щелкните файл Module1. vb, созданный Visual Basic.  
  
2. В примерах в этом разделе используются типы `Person` и `Pet`, а также данные из следующего примера кода. Скопируйте этот код в модуль `Module1` по умолчанию, созданный Visual Basic.  
  
     [!code-vb[VbLINQHowTos#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#1)]  
    [!code-vb[VbLINQHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#2)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a>Выполнение внутреннего объединения с помощью предложения Join  
 ВНУТРЕННЕЕ соединение объединяет данные из двух коллекций. Включаются элементы, для которых совпадают указанные значения ключа. Все элементы из любой коллекции, не имеющие соответствующего элемента в другой коллекции, исключаются.  
  
 В Visual Basic LINQ предоставляет два варианта выполнения внутреннего объединения: неявное соединение и явное соединение.  
  
 Неявное соединение задает коллекции для объединения в предложении `From` и определяет соответствующие ключевые поля в предложении `Where`. Visual Basic неявно соединяет две коллекции на основе указанных ключевых полей.  
  
 Вы можете указать явное соединение с помощью предложения `Join`, если хотите узнать, какие ключевые поля использовать в соединении. В этом случае можно по-прежнему использовать предложение `Where` для фильтрации результатов запроса.  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a>Выполнение внутреннего объединения с помощью предложения Join  
  
1. Добавьте следующий код в модуль `Module1` в проекте, чтобы увидеть примеры как неявного, так и неявного внутреннего объединения.  
  
     [!code-vb[VbLINQHowTos#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#4)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a>Выполнение левого внешнего объединения с помощью предложения Group Join  
 ЛЕВОЕ ВНЕШНее соединение включает все элементы из левой коллекции объединения и только совпадающие значения из правой коллекции объединения. Все элементы из правой коллекции объединения, не имеющие соответствующего элемента в коллекции слева, исключаются из результата запроса.  
  
 Предложение `Group Join` выполняет, по сути, левое ВНЕШНее соединение. Различие между тем, что обычно известно как левое ВНЕШНее соединение и что возвращается предложением `Group Join`, заключается в том, что предложение `Group Join` группирует результаты из правой коллекции объединения для каждого элемента в коллекции слева. В реляционной базе данных левое ВНЕШНее соединение возвращает несгруппированный результат, в котором каждый элемент в результатах запроса содержит совпадающие элементы из обеих коллекций в соединении. В этом случае элементы из левой коллекции объединения повторяются для каждого совпадающего элемента из правой коллекции. Вы увидите, как это выглядит при выполнении следующей процедуры.  
  
 Результаты запроса `Group Join` можно получить в виде несгруппированного результата, расширив запрос, чтобы вернуть элемент для каждого сгруппированного результата запроса. Для этого необходимо убедиться, что выполняется запрос к методу `DefaultIfEmpty` сгруппированной коллекции. Это гарантирует, что элементы из левой коллекции объединения по-прежнему будут включены в результат запроса, даже если они не имеют соответствующих результатов из коллекции справа. Можно добавить код в запрос, чтобы предоставить значение результата по умолчанию при отсутствии совпадающего значения из правой коллекции объединения.  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a>Выполнение левого внешнего объединения с помощью предложения Group Join  
  
1. Добавьте следующий код в модуль `Module1` в проекте, чтобы увидеть примеры сгруппированного левого внешнего объединения и несгруппированного левого внешнего объединения.  
  
     [!code-vb[VbLINQHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#3)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a>Выполнение объединения с помощью составного ключа  
 Можно использовать ключевое слово `And` в предложении `Join` или `Group Join`, чтобы указать несколько ключевых полей для использования при сопоставлении значений из объединяемых коллекций. Ключевое слово `And` указывает, что все указанные ключевые поля должны совпадать для соединяемых элементов.  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a>Выполнение объединения с помощью составного ключа  
  
1. Добавьте следующий код в модуль `Module1` в проекте, чтобы увидеть примеры соединений, использующих составной ключ.  
  
     [!code-vb[VbLINQHowTos#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#5)]  
  
## <a name="run-the-code"></a>Выполнение кода  
  
#### <a name="to-add-code-to-run-the-examples"></a>Добавление кода для выполнения примеров  
  
1. Замените `Sub Main` в модуле `Module1` в проекте на следующий код для выполнения примеров в этом разделе.  
  
     [!code-vb[VbLINQHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQHowTos/VB/Module1.vb#6)]  
  
2. Нажмите клавишу F5, чтобы выполнить примеры.  
  
## <a name="see-also"></a>См. также

- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md)
- [Предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Предложение From](../../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложения Where](../../../../visual-basic/language-reference/queries/where-clause.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [Преобразования данных с помощью LINQ (C#)](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)
