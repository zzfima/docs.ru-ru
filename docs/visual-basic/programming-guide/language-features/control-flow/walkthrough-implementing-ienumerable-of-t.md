---
title: "Реализация IEnumerable в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures, optimizing performance
- control flow
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 68c37c46cbceb1056d50972cdc58ddb7c7577447
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Пошаговое руководство. Реализация IEnumerable(Of T) в Visual Basic
<xref:System.Collections.Generic.IEnumerable%601>Интерфейс реализуется классами, которые могут возвращать последовательность значений по одному элементу за раз.</xref:System.Collections.Generic.IEnumerable%601> Преимущество возвращения данных одного элемента за раз является то, что вы не загрузить полный набор данных в памяти для работы с ним. Необходимо использовать достаточно памяти для загрузки одного элемента данных. Классы, реализующие `IEnumerable(T)` интерфейс может использоваться с `For Each` циклов или запросов LINQ.  
  
 Например рассмотрим приложение, которое должно читать большой текстовый файл и возвращать каждую строку из этого файла, отвечающую конкретным условиям поиска. Приложение использует запрос LINQ для возврата строки в файле, соответствующие указанным критериям. Запрос содержимого файла с помощью запроса LINQ, приложение может загрузить содержимое файла в массив или коллекцию. Однако загрузка целого файла в массив или коллекция потребует значительно большего объема памяти, чем требуется. Вместо запроса LINQ может опросить содержимое файла с помощью перечислимого класса, возвращая только значения, соответствующие критериям поиска. Запросы, возвращающие только несколько соответствующих значений, потребляют намного меньше памяти.  
  
 Можно создать класс, реализующий <xref:System.Collections.Generic.IEnumerable%601>интерфейс, предоставляемый перечислимых данных источнику данных.</xref:System.Collections.Generic.IEnumerable%601> Класс, реализующий `IEnumerable(T)` требуется еще один класс, реализующий интерфейс <xref:System.Collections.Generic.IEnumerator%601>интерфейс для итерации элементов в источнике данных.</xref:System.Collections.Generic.IEnumerator%601> Эти классы позволяют возвращать элементы данных последовательно, как конкретный тип.  
  
 В этом пошаговом руководстве вы создадите класс, реализующий `IEnumerable(Of String)` интерфейс и класс, реализующий `IEnumerator(Of String)` интерфейс для считывания текстового файла по одной строке за раз.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Создание перечислимого класса  
  
|Чтобы создать проект перечислимого класса|  
|---|  
|1.  В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]на **файл** наведите указатель мыши на **New** и нажмите кнопку **проекта**.<br />2.  В **новый проект** в диалоговом **типы проектов** область, убедитесь, что **Windows** выбран. Выберите **библиотеки классов** в **шаблоны** области. В **имя** введите `StreamReaderEnumerable`, а затем нажмите кнопку **ОК**. Откроется новый проект.<br />3.  В **обозревателе решений**, щелкните правой кнопкой мыши файл Class1.vb и выберите **переименование**. Переименуйте файл `StreamReaderEnumerable.vb` и нажмите клавишу ВВОД. Переименование файла также Переименуйте класс в `StreamReaderEnumerable`. Этот класс будет реализовывать `IEnumerable(Of String)` интерфейса.<br />4.  Щелкните правой кнопкой мыши проект StreamReaderEnumerable и выберите последовательно пункты **добавить**и нажмите кнопку **новый элемент**. Выберите **класса** шаблона. В **имя** введите `StreamReaderEnumerator.vb` и нажмите кнопку **ОК**.|  
  
 Первый класс в этом проекте — перечислимый класс и реализую `IEnumerable(Of String)` интерфейса. Этот универсальный интерфейс реализует <xref:System.Collections.IEnumerable>интерфейс и гарантии, потребители этого класса можно обращаться к значениям, типизированного как `String`.</xref:System.Collections.IEnumerable>  
  
|Чтобы добавить код, реализующий интерфейс IEnumerable|  
|---|  
|1.  Откройте файл StreamReaderEnumerable.vb.<br />2.  В строке после `Public Class StreamReaderEnumerable`, введите следующую команду и нажмите клавишу ВВОД.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#1;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]автоматически заполняет класс с членами, которые требуются `IEnumerable(Of String)` интерфейса.<br />3.  Этот перечислимый класс будет читать строки текстового файла по одной строке за раз. Добавьте следующий код в класс, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#2;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  Реализация <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>метода `IEnumerable(Of String)` интерфейс будет возвращать новый экземпляр `StreamReaderEnumerator` класса</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Реализация `GetEnumerator` метод `IEnumerable` можно сделать интерфейс `Private`, поскольку требуется предоставить доступ только члены `IEnumerable(Of String)` интерфейса. Замените код, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для `GetEnumerator` методов с помощью следующего кода.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#3;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|Чтобы добавить код для реализации IEnumerator|  
|---|  
|1.  Откройте файл StreamReaderEnumerator.vb.<br />2.  В строке после `Public Class StreamReaderEnumerator`, введите следующую команду и нажмите клавишу ВВОД.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#4;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]автоматически заполняет класс с членами, которые требуются `IEnumerator(Of String)` интерфейса.<br />3.  Класс перечислителя открывает текстовый файл и выполняет файлового ввода-вывода для чтения строки из файла. Добавьте следующий код в класс, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра и откройте текстовый файл для чтения.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#5;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  `Current` Свойств для обоих `IEnumerator(Of String)` и `IEnumerator` интерфейсы возвращают текущий элемент из текстового файла в качестве `String`. Реализация `Current` свойство `IEnumerator` можно сделать интерфейс `Private`, поскольку требуется предоставить доступ только члены `IEnumerator(Of String)` интерфейса. Замените код, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для `Current` свойства с помощью следующего кода.<br />     [!code-vb[VbVbalrIteratorWalkthrough №&6;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  `MoveNext` Метод `IEnumerator` интерфейс переходит к следующему элементу в текстовом файле и обновляет значение, возвращается `Current` свойство. Если больше нет элементов для чтения, `MoveNext` возвращает метод `False`; в противном случае `MoveNext` возвращает метод `True`. Добавьте следующий код в метод `MoveNext`.<br />     [!code-vb[VbVbalrIteratorWalkthrough&#7;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  `Reset` Метод `IEnumerator` интерфейс дает итератору начало текстового файла и очищает значение текущего элемента. Добавьте следующий код в метод `Reset`.<br />     [!code-vb[VbVbalrIteratorWalkthrough №&8;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  `Dispose` Метод `IEnumerator` интерфейс гарантирует, что все неуправляемые ресурсы будут освобождены до уничтожения итератора. Дескриптор файла, используемый `StreamReader` объект является неуправляемым ресурсом и должен быть закрыт до уничтожения экземпляра итератора. Замените код, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] для `Dispose` метод следующим кодом.<br />     [!code-vb[VbVbalrIteratorWalkthrough №&9;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>Использование образца итератора  
 Перечислимый класс может использоваться в коде совместно с управляющими структурами, для которых требуется объект, реализующий `IEnumerable`, такие как `For Next` цикла или запроса LINQ. В следующем примере показан `StreamReaderEnumerable` в запросе LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough&#10;](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>См. также  
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

