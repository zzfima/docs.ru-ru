---
title: "Реализация IEnumerable в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45b4008f0bf3ae0f303aa029e7bff5b82ab6f259
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Пошаговое руководство. Реализация IEnumerable(Of T) в Visual Basic
<xref:System.Collections.Generic.IEnumerable%601> Интерфейс реализуется классами, которые могут возвращать последовательность значений одного элемента за раз. Преимущество возвращения данных одного элемента за раз является то, что вы не загружать полный набор данных в памяти для работы с ним. Необходимо использовать достаточно памяти для загрузки одного элемента из данных. Классы, реализующие `IEnumerable(T)` интерфейс может использоваться с `For Each` циклов или запросов LINQ.  
  
 Например рассмотрим приложение, которое необходимо прочитать большой текстовый файл и возвращения каждой строки из файла, который соответствует конкретным условиям поиска. Приложение использует запрос LINQ для возврата строки из файла, который соответствует указанным критериям. Запрос содержимого файла с помощью запроса LINQ, приложение может загружать содержимое файла в массив или коллекция. Однако загрузка целого файла в массив или коллекция будет потреблять гораздо больше памяти, чем требуется. Вместо этого запрос LINQ может запросить содержимое файла с помощью перечислимого класса, возвращая только значения, соответствующие критериям поиска. Запросы, возвращающие только несколько соответствующих значений, потребляют намного меньше памяти.  
  
 Можно создать класс, реализующий <xref:System.Collections.Generic.IEnumerable%601> интерфейс, предоставляемый перечислимых данных источнику данных. Класс, реализующий `IEnumerable(T)` требуется другой класс, реализующий интерфейс <xref:System.Collections.Generic.IEnumerator%601> интерфейс для перечисления элементов в источнике данных. Эти классы позволяют возвращать элементы данных последовательно, как конкретный тип.  
  
 В этом пошаговом руководстве будет создан класс, реализующий `IEnumerable(Of String)` интерфейс и класс, реализующий `IEnumerator(Of String)` интерфейс для чтения текстового файла по одной строке за раз.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Создание перечислимого класса  
  
|Чтобы создать проект перечислимого класса|  
|---|  
|1.  В [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] в меню **Файл** последовательно выберите пункты **Создать**, **Проект**.<br />2.  Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**. Выберите **Библиотеки классов** в области **Шаблоны**. В поле **Имя** введите `StreamReaderEnumerable` и нажмите кнопку **ОК**. Откроется новый проект.<br />3.  В **обозревателе решений**, щелкните правой кнопкой мыши файл Class1.vb и нажмите кнопку **переименование**. Измените имя файла на `StreamReaderEnumerable.vb` и нажмите клавишу ВВОД. При переименовании файла класс также будет переименован в `StreamReaderEnumerable`. Этот класс реализует интерфейс `IEnumerable(Of String)`.<br />4.  Щелкните правой кнопкой мыши проект StreamReaderEnumerable, выберите пункт **добавить**, а затем нажмите кнопку **новый элемент**. Выберите **класса** шаблона. В **имя** введите `StreamReaderEnumerator.vb` и нажмите кнопку **ОК**.|  
  
 Первый класс в этом проекте — перечислимый класс и реализует `IEnumerable(Of String)` интерфейса. Этот универсальный интерфейс реализует <xref:System.Collections.IEnumerable> интерфейс и гарантирует доступность потребителям этого класса к типу значения `String`.  
  
|Чтобы добавить код, реализующий интерфейс IEnumerable|  
|---|  
|1.  Откройте файл StreamReaderEnumerable.vb.<br />2.  В строке после `Public Class StreamReaderEnumerable`, введите следующую команду и нажмите клавишу ВВОД.<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]автоматически заполняет класс с элементами, которые требуются `IEnumerable(Of String)` интерфейса.<br />3.  Этот перечислимый класс будет читать строки текстового файла по одной строке за раз. Добавьте следующий код в класс, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра.<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  Реализация <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> метод `IEnumerable(Of String)` интерфейс будет возвращать новый экземпляр `StreamReaderEnumerator` класса. Реализация `GetEnumerator` метод `IEnumerable` можно сделать интерфейс `Private`, поскольку требуется предоставить доступ только члены `IEnumerable(Of String)` интерфейса. Замените код, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для `GetEnumerator` методы следующим кодом.<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|Чтобы добавить код для реализации IEnumerator|  
|---|  
|1.  Откройте файл StreamReaderEnumerator.vb.<br />2.  В строке после `Public Class StreamReaderEnumerator`, введите следующую команду и нажмите клавишу ВВОД.<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]автоматически заполняет класс с элементами, которые требуются `IEnumerator(Of String)` интерфейса.<br />3.  Класс перечислителя открывает текстовый файл и выполняет файлового ввода-вывода, считывая строки из файла. Добавьте следующий код в класс, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра и откройте текстовый файл для чтения.<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  `Current` Свойств для обоих `IEnumerator(Of String)` и `IEnumerator` интерфейсы возвращают текущий элемент из текстового файла в качестве `String`. Реализация `Current` свойство `IEnumerator` можно сделать интерфейс `Private`, поскольку требуется предоставить доступ только члены `IEnumerator(Of String)` интерфейса. Замените код, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для `Current` свойства с помощью следующего кода.<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  `MoveNext` Метод `IEnumerator` интерфейс переходит к следующему элементу в текстовом файле и обновляет значение, возвращается `Current` свойство. Если больше нет элементов для чтения, `MoveNext` возвращает `False`; в противном случае `MoveNext` возвращает `True`. Добавьте следующий код в метод `MoveNext` .<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  `Reset` Метод `IEnumerator` интерфейс дает итератору на начало текстового файла и очищает значение текущего элемента. Добавьте следующий код в метод `Reset` .<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  `Dispose` Метод `IEnumerator` интерфейс гарантирует, что все неуправляемые ресурсы будут освобождены до уничтожения итератора. Дескриптор файла, используемый `StreamReader` объект является неуправляемым ресурсом и должен быть закрыт до уничтожения экземпляра итератора. Замените код, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] для `Dispose` метод следующим кодом.<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>Использование образца итератора  
 Перечислимый класс может использоваться в коде, а также структур управления, для которых требуется объект, реализующий `IEnumerable`, такие как `For Next` цикла или запросом LINQ. В следующем примере показан `StreamReaderEnumerable` в запросе LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
