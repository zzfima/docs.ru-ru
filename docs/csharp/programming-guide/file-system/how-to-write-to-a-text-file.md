---
title: Практическое руководство. Руководство по программированию на C#. Запись в текстовый файл
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: e3fa0eb12c9259629ff8151ff2d057f2744e9e36
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595626"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Практическое руководство. Руководство по программированию на C#. Запись в текстовый файл
В этих примерах показаны различные способы записи текста в файл. В первых двух примерах используются удобные статические методы класса <xref:System.IO.File?displayProperty=nameWithType> для записи каждого элемента любого объекта `IEnumerable<string>` и строки в текстовый файл. В примере 3 показано, как добавить текст в файл, если необходимо обрабатывать отдельно каждую строку по мере ее записи в файл. В примерах 1–3 перезаписывается все существующее содержимое файла, а в примере 4 показано, как добавить текст в существующий файл.  
  
 Все эти примеры записывают строковые литералы в файлы. Чтобы отформатировать записываемый в файл текст, воспользуйтесь методом <xref:System.String.Format%2A> или функцией [интерполяции строк](../../../csharp/language-reference/tokens/interpolated.md) C#.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
- Файл существует и является файлом только для чтения.  
  
- Имя пути имеет слишком большую длину.  
  
- Диск может быть переполнен.  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)
- [Пример. Сохранение коллекции настраиваемых объектов в локальном хранилище](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
