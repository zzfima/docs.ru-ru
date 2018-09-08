---
title: Реализация IEnumerable в Visual Basic
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: be2eefdc52d38df3071d457b7a71dbac6eaa2657
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44141169"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Пошаговое руководство. Реализация IEnumerable(Of T) в Visual Basic
<xref:System.Collections.Generic.IEnumerable%601> Интерфейс реализуется классами, которые могут возвращать последовательность значений по одному элементу за раз. Преимущество возвращения данных одного элемента за раз в том, что не нужно загрузить полный набор данных в памяти для работы с ним. Необходимо использовать достаточно памяти для загрузки одного элемента из данных. Классы, реализующие `IEnumerable(T)` интерфейс можно использовать с `For Each` циклы или запросов LINQ.  
  
 Например рассмотрим приложение, которое необходимо прочитать большого текстового файла и возвращения каждой строки из файла, который соответствует конкретным условиям поиска. Приложение использует запрос LINQ для возврата строки из файла, соответствующие указанным критериям. Чтобы запросить содержимое файла с помощью запроса LINQ, приложение может получать содержимое файла в массив или коллекция. Тем не менее для загрузки всего файла в массив или коллекция потребует гораздо больше памяти, чем требуется. Запрос LINQ вместо удалось запросить содержимое файла с помощью перечислимого класса, возвращая только значения, соответствующие критериям поиска. Запросы, возвращающие только несколько соответствующих значений, потребляют намного меньше памяти.  
  
 Можно создать класс, реализующий <xref:System.Collections.Generic.IEnumerable%601> интерфейс для предоставления источника данных в виде перечислимых данных. Класс, реализующий `IEnumerable(T)` требуют другой класс, реализующий интерфейс <xref:System.Collections.Generic.IEnumerator%601> интерфейс для выполнения итерации по исходных данных. Эти классы позволяют возвращать элементы данных последовательно, как конкретный тип.  
  
 В этом пошаговом руководстве вы создадите класс, реализующий `IEnumerable(Of String)` интерфейс и класс, реализующий `IEnumerator(Of String)` интерфейс для считывания текстового файла по одной строке за раз.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Создание класса Enumerable  
  
**Создайте проект класса enumerable**

1.  В Visual Basic на **файл** последовательно выберите пункты **New** и нажмите кнопку **проекта**.

1.  Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**. Выберите **Библиотеки классов** в области **Шаблоны**. В поле **Имя** введите `StreamReaderEnumerable` и нажмите кнопку **ОК**. Откроется новый проект.

1.  В **обозревателе решений**, щелкните правой кнопкой мыши файл Class1.vb и нажмите кнопку **Переименовать**. Измените имя файла на `StreamReaderEnumerable.vb` и нажмите клавишу ВВОД. При переименовании файла класс также будет переименован в `StreamReaderEnumerable`. Этот класс реализует интерфейс `IEnumerable(Of String)`.

1.  Щелкните правой кнопкой мыши проект StreamReaderEnumerable, выберите пункт **добавить**, а затем нажмите кнопку **новый элемент**. Выберите **класс** шаблона. В **имя** введите `StreamReaderEnumerator.vb` и нажмите кнопку **ОК**.

 Первый класс в этом проекте представляет класс enumerable и будет реализовывать `IEnumerable(Of String)` интерфейс. Этот универсальный интерфейс реализует <xref:System.Collections.IEnumerable> интерфейс и гарантии, что потребители этого класса можно обращаться к значениям, типизированный как `String`.  
  
**Добавление кода для реализации IEnumerable**

1. Откройте файл StreamReaderEnumerable.vb.

2. В строке после `Public Class StreamReaderEnumerable`, введите следующую команду и нажмите клавишу ВВОД.

   [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]

   Visual Basic автоматически заполняет класс с элементами, которые требуются `IEnumerable(Of String)` интерфейс.
  
3. Этот класс enumerable будет читать строки текстового файла по одной строке за раз. Добавьте следующий код к классу, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра.

   [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]

4. Реализация <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> метод `IEnumerable(Of String)` интерфейс будет возвращать новый экземпляр класса `StreamReaderEnumerator` класса. Реализация `GetEnumerator` метод `IEnumerable` можно сделать интерфейс `Private`, так как требуется предоставить доступ только члены `IEnumerable(Of String)` интерфейс. Замените код, созданный Visual Basic для `GetEnumerator` методы следующим кодом.

   [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]  
  
**Добавление кода для реализации IEnumerator**

1. Откройте файл StreamReaderEnumerator.vb.

2. В строке после `Public Class StreamReaderEnumerator`, введите следующую команду и нажмите клавишу ВВОД.

   [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]

   Visual Basic автоматически заполняет класс с элементами, которые требуются `IEnumerator(Of String)` интерфейс.

3. Класс перечислителя открывает текстовый файл и выполняет файлового ввода-вывода для чтения строк из файла. Добавьте следующий код к классу предоставлять открытый конструктор, который принимает путь к файлу в качестве входного параметра и откройте текстовый файл для чтения.

   [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]

4. `Current` Свойства для обоих `IEnumerator(Of String)` и `IEnumerator` интерфейсы возвращают текущий элемент из текстового файла в качестве `String`. Реализация `Current` свойство `IEnumerator` можно сделать интерфейс `Private`, так как требуется предоставить доступ только члены `IEnumerator(Of String)` интерфейс. Замените код, созданный Visual Basic для `Current` свойства со следующим кодом.

   [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]

5. `MoveNext` Метод `IEnumerator` интерфейс переходит к следующему элементу в текстовом файле и обновляет значение, которое возвращается методом `Current` свойство. Если больше нет элементов для чтения, `MoveNext` возвращает `False`; в противном случае `MoveNext` возвращает метод `True`. Добавьте следующий код в метод `MoveNext` .

   [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]

6. `Reset` Метод `IEnumerator` интерфейс дает итератор на начало текстового файла и очищает значение текущего элемента. Добавьте следующий код в метод `Reset` .

   [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]

7. `Dispose` Метод `IEnumerator` интерфейс гарантирует, что все неуправляемые ресурсы будут освобождены до уничтожения итератора. Дескриптор файла, который используется `StreamReader` объект является неуправляемым ресурсом и должен быть закрыт до уничтожения экземпляра итератора. Замените код, созданный Visual Basic для `Dispose` метод следующим кодом.

   [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)] 
  
## <a name="using-the-sample-iterator"></a>Использование образца итератора

 Перечислимый класс можно использовать в коде, а также структур управления, для которых требуется объект, реализующий `IEnumerable`, такие как `For Next` цикла или запроса LINQ. В следующем примере показан `StreamReaderEnumerable` в запросе LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
