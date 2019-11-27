---
title: Реализация IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: f40fcf7e0724addc478b261dcd36d09e1d8a751a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333690"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Пошаговое руководство. Реализация IEnumerable(Of T) в Visual Basic
Интерфейс <xref:System.Collections.Generic.IEnumerable%601> реализуется классами, которые могут возвращать последовательность значений по одному элементу за раз. Преимущество возврата данных по одному элементу за раз заключается в том, что для работы с ним не нужно загружать полный набор данных в память. Для загрузки одного элемента из данных необходимо использовать достаточно памяти. Классы, реализующие интерфейс `IEnumerable(T)`, можно использовать с циклами `For Each` или запросами LINQ.  
  
 Например, рассмотрим приложение, которое должно считывать большой текстовый файл и возвращать каждую строку из файла, удовлетворяющего определенным условиям поиска. Приложение использует запрос LINQ для возврата строк из файла, соответствующих указанным критериям. Чтобы запросить содержимое файла с помощью запроса LINQ, приложение может загрузить содержимое файла в массив или коллекцию. Однако загрузка всего файла в массив или коллекцию занимают гораздо больше памяти, чем требуется. Запрос LINQ может вместо этого запросить содержимое файла с помощью перечислимого класса, возвращая только те значения, которые соответствуют критериям поиска. Запросы, возвращающие только несколько соответствующих значений, занимают гораздо меньше памяти.  
  
 Можно создать класс, реализующий интерфейс <xref:System.Collections.Generic.IEnumerable%601>, чтобы предоставить исходные данные в виде перечислимых данных. Класс, реализующий интерфейс `IEnumerable(T)`, потребует другого класса, реализующего интерфейс <xref:System.Collections.Generic.IEnumerator%601> для прохода по исходным данным. Эти два класса позволяют последовательно возвращаться элементы данных в виде определенного типа.  
  
 В этом пошаговом руководстве вы создадите класс, реализующий интерфейс `IEnumerable(Of String)`, и класс, реализующий интерфейс `IEnumerator(Of String)` для чтения текстового файла по одной строке за раз.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Создание класса Enumerable  
  
**Создание проекта класса Enumerable**

1. В Visual Basic в меню **файл** наведите указатель мыши на пункт **создать** и выберите пункт **проект**.

1. Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**. Выберите **Библиотеки классов** в области **Шаблоны**. В поле **Имя** введите `StreamReaderEnumerable` и нажмите кнопку **ОК**. Отобразится новый проект.

1. В **Обозреватель решений**щелкните правой кнопкой мыши файл Class1. vb и выберите команду **Переименовать**. Измените имя файла на `StreamReaderEnumerable.vb` и нажмите клавишу ВВОД. При переименовании файла класс также будет переименован в `StreamReaderEnumerable`. Этот класс реализует интерфейс `IEnumerable(Of String)`.

1. Щелкните правой кнопкой мыши проект Стреамреадеренумерабле, наведите указатель на пункт **Добавить**и выберите пункт **новый элемент**. Выберите шаблон **класса** . В поле **имя** введите `StreamReaderEnumerator.vb` и нажмите кнопку **ОК**.

 Первый класс в этом проекте является классом Enumerable и реализует интерфейс `IEnumerable(Of String)`. Этот универсальный интерфейс реализует интерфейс <xref:System.Collections.IEnumerable> и гарантирует, что потребители этого класса могут обращаться к значениям, введенным как `String`.  
  
**Добавление кода для реализации IEnumerable**

1. Откройте файл Стреамреадеренумерабле. vb.

2. В строке после `Public Class StreamReaderEnumerable`введите следующую команду и нажмите клавишу ВВОД.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic автоматически заполняет класс членами, необходимыми для интерфейса `IEnumerable(Of String)`.
  
3. Этот перечислимый класс будет считывать строки из текстового файла по одной строке за раз. Добавьте следующий код в класс, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. Реализация метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> интерфейса `IEnumerable(Of String)` вернет новый экземпляр класса `StreamReaderEnumerator`. Реализацию метода `GetEnumerator` интерфейса `IEnumerable` можно сделать `Private`, поскольку необходимо предоставлять доступ только членам интерфейса `IEnumerable(Of String)`. Замените код, который Visual Basic создан для методов `GetEnumerator`, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Добавьте код для реализации IEnumerator**

1. Откройте файл Стреамреадеренумератор. vb.

2. В строке после `Public Class StreamReaderEnumerator`введите следующую команду и нажмите клавишу ВВОД.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic автоматически заполняет класс членами, необходимыми для интерфейса `IEnumerator(Of String)`.

3. Класс перечислителя открывает текстовый файл и выполняет файловый ввод-вывод для считывания строк из файла. Добавьте следующий код в класс, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра и открывает текстовый файл для чтения.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. Свойства `Current` для интерфейсов `IEnumerator(Of String)` и `IEnumerator` возвращают текущий элемент из текстового файла как `String`. Реализация свойства `Current` интерфейса `IEnumerator` может быть сделана `Private`, поскольку необходимо предоставлять только члены интерфейса `IEnumerator(Of String)`. Замените код, который Visual Basic создан для свойств `Current`, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. Метод `MoveNext` интерфейса `IEnumerator` переходит к следующему элементу в текстовом файле и обновляет значение, возвращаемое свойством `Current`. Если больше нет элементов для чтения, метод `MoveNext` возвращает `False`; в противном случае метод `MoveNext` возвращает `True`. Добавьте следующий код в метод `MoveNext` .

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. Метод `Reset` интерфейса `IEnumerator` направляет итератор, указывающий на начало текстового файла, и очищает значение текущего элемента. Добавьте следующий код в метод `Reset` .

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. Метод `Dispose` интерфейса `IEnumerator` гарантирует, что все неуправляемые ресурсы освобождаются до уничтожения итератора. Файл, используемый объектом `StreamReader`, является неуправляемым ресурсом и должен быть закрыт перед уничтожением экземпляра итератора. Замените код, который Visual Basic создан для метода `Dispose`, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)] 
  
## <a name="using-the-sample-iterator"></a>Использование примера итератора

 Класс Enumerable можно использовать в коде вместе с структурами элементов управления, для которых требуется объект, реализующий `IEnumerable`, например цикл `For Next` или запрос LINQ. В следующем примере показано `StreamReaderEnumerable` в запросе LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
