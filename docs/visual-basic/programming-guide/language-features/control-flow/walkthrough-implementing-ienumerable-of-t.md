---
title: "Пошаговое руководство. Реализация IEnumerable(Of T) в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "поток управления"
  - "поток управления [Visual Basic]"
  - "IEnumerable - интерфейс"
  - "циклические структуры, оптимизация производительности"
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Пошаговое руководство. Реализация IEnumerable(Of T) в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Интерфейс <xref:System.Collections.Generic.IEnumerable%601> реализуется классами, которые могут возвращать последовательность значений по одному элементу за один раз.  Преимущество возвращения данных по одному элементу за один раз состоит в том, что при этом отсутствует необходимость загружать в память весь набор данных для работы с ними.  Можно ограничиться использованием объема памяти, достаточного для загрузки одного элемента данных.  Классы, реализующие интерфейс `IEnumerable(T)`, могут использоваться совместно с циклами `For Each` или запросами LINQ.  
  
 Для примера возьмем приложение, которое должно читать большой текстовый файл и возвращать каждую строку из этого файла, отвечающую конкретным условиям поиска.  Чтобы возвращать отвечающие заданным условиям строки из файла, приложение использует запрос LINQ.  Чтобы опросить содержимое файла с помощью запроса LINQ, приложение могло бы загрузить это содержимое в массив или коллекцию.  Однако загрузка целого файла в массив или коллекцию приведет к использованию значительно большего объема памяти, нежели необходимо.  Вместо этого запрос LINQ может опросить содержимое файла с помощью перечислимого класса, возвращая только значения, соответствующие условиям поиска.  Запросы, возвращающие только ограниченное число соответствующих значений, потребляют намного меньше памяти.  
  
 Для представления исходных данных как перечислимых можно создать класс, реализующий интерфейс <xref:System.Collections.Generic.IEnumerable%601>.  Классу, реализующему интерфейс `IEnumerable(T)`, потребуется другой класс, который реализует интерфейс <xref:System.Collections.Generic.IEnumerator%601> для итерации по исходным данным.  Эти два класса позволяют последовательно возвращать элементы данных в виде определенного типа.  
  
 В этом пошаговом руководстве создается класс, реализующий интерфейс `IEnumerable(Of String)`, и класс, который реализует интерфейс `IEnumerator(Of String)`, которые могут использоваться для считывания текстового файла по одной строке за один раз.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
## Создание перечислимого класса  
  
||  
|-|  
|Чтобы создать проект перечислимого класса, выполните следующие действия:|  
|1.  В [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] в меню **Файл** последовательно выберите пункты **Создать** и **Проект**.<br />2.  Убедитесь, что в диалоговом окне **Новый проект** в области **Типы проектов** выбран пункт **Windows**.  В области **Шаблоны** выберите пункт **Библиотека классов**.  В поле **Имя** введите `StreamReaderEnumerable` и нажмите кнопку **ОК**.  Появится новый проект.<br />3.  В **обозревателе решений** щелкните правой кнопкой мыши файл Class1.vb и выберите команду **Переименовать**.  Переименуйте файл в `StreamReaderEnumerable.vb` и нажмите клавишу ВВОД.  При переименовании файла класс также будет переименован в `StreamReaderEnumerable`.  Этот класс будет реализовывать интерфейс `IEnumerable(Of String)`.<br />4.  Щелкните правой кнопкой мыши проект StreamReaderEnumerable, выберите команду **Добавить** и пункт **Создать элемент**.  Выберите шаблон **Класс**.  В поле **Имя** введите `StreamReaderEnumerator.vb` и нажмите кнопку **ОК**.|  
  
 Первый класс в этом проекте — перечислимый класс, который реализует интерфейс `IEnumerable(Of String)`.  Этот универсальный интерфейс реализует интерфейс <xref:System.Collections.IEnumerable> и предоставляет потребителям этого класса гарантированный доступ к значениям, тип которых задан как `String`.  
  
||  
|-|  
|Добавление кода для реализации IEnumerable|  
|1.  Откройте файл StreamReaderEnumerable.vb.<br />2.  В строке после `Public Class StreamReaderEnumerable` введите следующее и нажмите клавишу ВВОД.<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] автоматически заполняет класс членами, необходимыми для интерфейса `IEnumerable(Of String)`.<br />3.  Этот перечислимый класс будет читать строки текстового файла одну за другой.  Добавьте в класс следующий код, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра.<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.  Реализация метода <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> интерфейса `IEnumerable(Of String)` будет возвращать новый экземпляр класса `StreamReaderEnumerator`.  Реализацию метода `GetEnumerator` интерфейса `IEnumerable` можно сделать закрытой \(`Private`\), поскольку требуется предоставить доступ только членам интерфейса `IEnumerable(Of String)`.  Замените код, созданный [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для методов `GetEnumerator`, следующим кодом.<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
||  
|-|  
|Добавление кода для реализации IEnumerator|  
|1.  Откройте файл StreamReaderEnumerator.vb.<br />2.  В строке после `Public Class StreamReaderEnumerator` введите следующее и нажмите клавишу ВВОД.<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] автоматически заполняет класс членами, необходимыми для интерфейса `IEnumerator(Of String)`.<br />3.  Класс перечислителя открывает текстовый файл и выполняет файловые операции ввода\-вывода, считывая строки из файла.  Добавьте в класс следующий код, чтобы предоставить открытый конструктор, который принимает путь к файлу как входной параметр и открывает текстовый файл для чтения.<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.  Свойства `Current` для интерфейсов `IEnumerator(Of String)` и `IEnumerator` возвращают текущий элемент из текстового файла в качестве объекта типа `String`.  Реализацию свойства `Current` интерфейса `IEnumerator` можно сделать закрытой \(`Private`\), поскольку требуется предоставить доступ только членам интерфейса `IEnumerator(Of String)`.  Замените код, созданный [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для свойств `Current`, следующим кодом.<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.  Метод `MoveNext` интерфейса `IEnumerator` переходит к следующему элементу в текстовом файле и обновляет значение, возвращаемое свойством `Current`.  Если элементов для чтения не осталось, метод `MoveNext` возвращает значение `False`; в противном случае метод `MoveNext` возвращает значение `True`.  Добавьте следующий код в метод `MoveNext`.<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.  Метод `Reset` интерфейса `IEnumerator` дает итератору команду перейти в начало текстового файла и очищает значение текущего элемента.  Добавьте следующий код в метод `Reset`.<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.  Метод `Dispose` интерфейса `IEnumerator` гарантирует, что все неуправляемые ресурсы будут освобождены до уничтожения итератора.  Дескриптор файла, используемый объектом `StreamReader`, является неуправляемым ресурсом, который должен быть закрыт до уничтожения экземпляра итератора.  Замените код, созданный [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] для метода `Dispose`, следующим кодом.<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## Использование образца итератора  
 Перечислимый класс может использоваться в коде совместно с управляющими структурами, для которых требуется объект, реализующий интерфейс `IEnumerable`, например с циклом `For Next` или запросом LINQ.  В следующем примере показан пример использования `StreamReaderEnumerable` в запросе LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## См. также  
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Управление ходом выполнения](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)