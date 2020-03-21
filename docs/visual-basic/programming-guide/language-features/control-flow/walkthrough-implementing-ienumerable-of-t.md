---
title: Реализация IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266915"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Пошаговое руководство. Реализация IEnumerable(Of T) в Visual Basic
Интерфейс <xref:System.Collections.Generic.IEnumerable%601> реализован классами, которые могут возвращать последовательность значений по одному элементу за раз. Преимущество возврата данных по одному элементу за один раз заключается в том, что вам не нужно загружать полный набор данных в память, чтобы работать с ним. Для загрузки одного элемента из данных необходимо использовать достаточную память. Классы, `IEnumerable(T)` реализующие `For Each` интерфейс, могут использоваться с помощью циклов или запросов LIN.  
  
 Например, рассмотрим приложение, которое должно прочитать большой текстовый файл и вернуть каждую строку из файла, которое соответствует определенным критериям поиска. Приложение использует запрос LIN'а для возврата строк из файла, которые соответствуют указанным критериям. Чтобы задать запрос на содержимое файла с помощью запроса LIN,, приложение может загрузить содержимое файла в массив или коллекцию. Однако загрузка всего файла в массив или коллекцию потребует гораздо больше памяти, чем требуется. Вместо этого запрос НАИВный запрос может задать запрос содержимого файла с помощью перечисленного класса, вернув только значения, которые соответствуют критериям поиска. Запросы, возвращающие лишь несколько соответствующих значений, потребляют гораздо меньше памяти.  
  
 Можно создать класс, который <xref:System.Collections.Generic.IEnumerable%601> реализует интерфейс для обнажая исходные данные в качестве перечисленных данных. Классу, реализующего `IEnumerable(T)` интерфейс, потребуется <xref:System.Collections.Generic.IEnumerator%601> другой класс, который реализует интерфейс для итерации через исходные данные. Эти два класса позволяют возвращать элементы данных последовательно в качестве определенного типа.  
  
 В этом пошаговом шаге вы `IEnumerable(Of String)` создадите класс, который `IEnumerator(Of String)` реализует интерфейс и класс, который реализует интерфейс для чтения одной строки текста за раз.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Создание подавиваемого класса  
  
**Создание проекта, поддававшегося пересчету класса**

1. В Visual Basic, в меню **файла,** укажите на **новый,** а затем нажмите **Project**.

1. Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**. Выберите **Библиотеки классов** в области **Шаблоны**. В поле **Имя** введите `StreamReaderEnumerable` и нажмите кнопку **ОК**. Отображается новый проект.

1. В **Solution Explorer**, правой кнопкой мыши на class1.vb файл и нажмите **Переименовать**. Измените имя файла на `StreamReaderEnumerable.vb` и нажмите клавишу ВВОД. При переименовании файла класс также будет переименован в `StreamReaderEnumerable`. Этот класс реализует интерфейс `IEnumerable(Of String)`.

1. Право нажмите на StreamReaderEnumable проекта, указать, чтобы **добавить,** а затем нажмите **Новый пункт**. Выберите шаблон **класса.** В поле **Имя** введите `StreamReaderEnumerator.vb`, а затем нажмите кнопку **ОК**.

 Первым классом в этом проекте является перечисленный `IEnumerable(Of String)` класс и будет реализован интерфейс. Этот общий интерфейс <xref:System.Collections.IEnumerable> реализует интерфейс и гарантирует, что потребители этого `String`класса могут получить доступ к значениям, набранным как.  
  
**Добавление кода для реализации IEnumerable**

1. Откройте файл StreamReaderEnumerable.vb.

2. На линии `Public Class StreamReaderEnumerable`после , введите следующее и нажмите ENTER.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic автоматически заполняет класс членами, `IEnumerable(Of String)` которые требуются интерфейсу.
  
3. Этот перечисленный класс будет читать строки из текстового файла по одной строке за раз. Добавьте следующий код в класс, чтобы разоблачить общедоступный конструктор, который использует путь файла в качестве параметра ввода.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. Реализация <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> метода `IEnumerable(Of String)` интерфейса вернет новый экземпляр `StreamReaderEnumerator` класса. Реализация `GetEnumerator` метода интерфейса `IEnumerable` может быть `Private`сделана, потому что `IEnumerable(Of String)` вы должны подвергать только члены интерфейса. Замените код, созданный `GetEnumerator` Visual Basic для методов, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Добавить код для реализации IEnumerator**

1. Откройте файл StreamReaderEnumerator.vb.

2. На линии `Public Class StreamReaderEnumerator`после , введите следующее и нажмите ENTER.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic автоматически заполняет класс членами, `IEnumerator(Of String)` которые требуются интерфейсу.

3. Класс enumerator открывает текстовый файл и выполняет ввоза файла/от, чтобы прочитать строки из файла. Добавьте следующий код в класс, чтобы разоблачить общедоступный конструктор, который использует путь файла в качестве параметра ввода, и откройте текстовый файл для чтения.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. Свойства `Current` как для `IEnumerator(Of String)` `IEnumerator` интерфейсов, так и для интерфейсов `String`возвращают текущий элемент из текстового файла в виде. Реализация `Current` свойства `IEnumerator` интерфейса может быть `Private`сделана, потому что вы `IEnumerator(Of String)` должны подвергать только члены интерфейса. Замените код, созданный `Current` Visual Basic для свойств, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. Метод `MoveNext` `IEnumerator` интерфейса переходит к следующему элементу в текстовом файле `Current` и обновляет значение, возвращаемое свойством. Если нет больше элементов для `MoveNext` чтения, метод возвращается; `False` в `MoveNext` противном `True`случае метод возвращается. Добавьте в метод `MoveNext` следующий код.

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. Метод `Reset` `IEnumerator` интерфейса направляет итератору указывать на начало текстового файла и очищает текущее значение элемента. Добавьте в метод `Reset` следующий код.

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. Метод `Dispose` `IEnumerator` интерфейса гарантирует, что все неуправляемые ресурсы будут выпущены до уничтожения итератора. Ручка файла, используемая `StreamReader` объектом, является неуправляемым ресурсом и должна быть закрыта до того, как экземпляр итератора будет уничтожен. Замените код, созданный `Dispose` Visual Basic для метода, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>Использование образца Итератора

 В коде можно использовать перечисленный класс вместе со структурами управления, `IEnumerable`требующими `For Next` реализации объекта, например цикла или запроса НАИС. В следующем примере `StreamReaderEnumerable` показан запрос LIN'а.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>См. также раздел

- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Поток управления](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [Циклические структуры](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Оператор For Each...Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
