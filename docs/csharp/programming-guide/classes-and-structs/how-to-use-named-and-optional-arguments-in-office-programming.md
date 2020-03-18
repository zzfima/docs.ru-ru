---
title: Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office (руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: 36b5c8b49404606c8240d24953c3677d5612d30e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714875"
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a>Практическое руководство. Использование именованных и необязательных аргументов в программировании приложений Office (руководство по программированию на C#)

Появившиеся в C# 4 именованные и необязательные аргументы повышают удобство, гибкость и удобочитаемость программирования на C#. Кроме того, эти функции значительно упрощают доступ к COM-интерфейсам, таким как интерфейсы API автоматизации Microsoft Office.

В следующем примере у метода [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) имеется шестнадцать параметров, представляющих характеристики таблицы, например число столбцов и строк, форматирование, границы и цвета. Все шестнадцать параметров являются необязательными, поскольку в большинстве случаев не требуется задавать конкретные значения для всех этих параметров. Однако без именованных и необязательных аргументов приходилось указывать значение или значение-заполнитель для каждого из параметров. Именованные и необязательные параметры позволяют задавать значения только для тех параметров, которые требуются в конкретном проекте.

Для выполнения этих процедур на компьютере должно быть установлено приложение Microsoft Office Word.

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-a-new-console-application"></a>Создание нового проекта консольного приложения

1. Запустите среду Visual Studio.

2. В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.

3. В области **Категории шаблонов** разверните узел **Visual C#** и выберите **Windows**.

4. В верхней части области **Шаблоны** в поле **Требуемая версия .NET Framework** должно отображаться значение **.NET Framework 4**.

5. В области **Шаблоны** щелкните **Консольное приложение**.

6. Введите имя проекта в поле **Имя**.

7. Нажмите кнопку **ОК**.

     В **обозревателе решений** появится новый проект.

## <a name="to-add-a-reference"></a>Добавление ссылки

1. В **обозревателе решений** щелкните имя проекта правой кнопкой мыши и выберите пункт **Добавить ссылку**. Откроется диалоговое окно **Добавление ссылки**.

2. На странице **.NET** выберите **Microsoft.Office.Interop.Word** в списке **Имя компонента**.

3. Нажмите кнопку **ОК**.

## <a name="to-add-necessary-using-directives"></a>Добавление необходимых директив using

1. В **обозревателе решений** щелкните правой кнопкой мыши файл *Program.cs* и выберите пункт **Просмотреть код**.

2. В начало файла кода добавьте следующие директивы `using`:

     [!code-csharp[csProgGuideNamedAndOptional#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#4)]

## <a name="to-display-text-in-a-word-document"></a>Отображение текста в документ Word

1. В класс `Program` в файле *Program.cs* добавьте следующий метод для создания приложения Word и документа Word. Метод [Add](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) имеет четыре необязательных параметра. В этом примере используются значения по умолчанию. Поэтому в операторе вызова указывать аргументы не требуется.

     [!code-csharp[csProgGuideNamedAndOptional#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#6)]

2. Добавьте в конец метода следующий код, чтобы определить место отображения текста в документе и текст для отображения:

     [!code-csharp[csProgGuideNamedAndOptional#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#7)]

## <a name="to-run-the-application"></a>Запуск приложения

1. Добавьте в метод Main следующую инструкцию:

     [!code-csharp[csProgGuideNamedAndOptional#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#8)]

2. Нажмите клавиши <kbd>CTRL</kbd>+<kbd>F5</kbd>, чтобы запустить проект. Появится документ Word, содержащий указанный текст.

## <a name="to-change-the-text-to-a-table"></a>Замена текста на таблицу
  
1. Метод `ConvertToTable` служит для преобразования текста в таблицу. У метода имеется шестнадцать необязательных параметров. IntelliSense заключает необязательные параметры в квадратные скобки, как показано на следующем рисунке.

     ![Список параметров для метода ConvertToTable](./media/how-to-use-named-and-optional-arguments-in-office-programming/convert-table-parameters.png)

     Именованные и необязательные аргументы позволяют задавать значения только для тех параметров, которые требуется изменить. Добавьте в конец метода `DisplayInWord` следующий код, чтобы создать простую таблицу. Аргумент указывает, что запятые в текстовой строке в `range` разделяют ячейки таблицы.

     [!code-csharp[csProgGuideNamedAndOptional#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#9)]

     В более ранних версиях C# для вызова `ConvertToTable` каждому параметру требовался ссылочный аргумент, как показано в следующем коде:
  
     [!code-csharp[csProgGuideNamedAndOptional#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#14)]

2. Нажмите клавиши <kbd>CTRL</kbd>+<kbd>F5</kbd>, чтобы запустить проект.

## <a name="to-experiment-with-other-parameters"></a>Экспериментирование с другими параметрами

1. Для изменения таблицы, чтобы она содержала один столбец и три строки, замените последнюю строку метода `DisplayInWord` следующей инструкцией и нажмите сочетание клавиш <kbd>CTRL</kbd>+<kbd>F5</kbd>.  

     [!code-csharp[csProgGuideNamedAndOptional#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#10)]

2. Чтобы использовать заранее определенный формат таблицы, замените последнюю строку метода `DisplayInWord` следующей инструкцией и нажмите сочетание клавиш <kbd>CTRL</kbd>+<kbd>F5</kbd>. В качестве формата можно использовать любую из констант [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>).

     [!code-csharp[csProgGuideNamedAndOptional#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#11)]

## <a name="example"></a>Пример

Следующий код включает полный пример:

 [!code-csharp[csProgGuideNamedAndOptional#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#12)]

## <a name="see-also"></a>См. также раздел

- [Именованные и необязательные аргументы](./named-and-optional-arguments.md)
