---
title: Как выполнить Руководство по программированию на C#. Чтение из текстового файла
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 560453a81124a3ee52a2ffd794ddac026c7394a5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978024"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Чтение из текстового файла
В этом примере считывается содержимое текстового файла с помощью статических методов <xref:System.IO.File.ReadAllText%2A> и <xref:System.IO.File.ReadAllLines%2A> из класса <xref:System.IO.File?displayProperty=nameWithType>.  
  
 Пример использования <xref:System.IO.StreamReader> см. в практическом руководстве по [ построчному чтению текстового файла](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
>  Файлы, которые используются в этом примере, созданы при работе с практическим руководством по [ записи в текстовый файл](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код и вставьте его в консольное приложение C#.  
  
 Если вы не используете текстовые файлы, созданные при работе с практическим руководством по [ записи в текстовый файл](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), замените аргумент `ReadAllText` и `ReadAllLines` соответствующим путем и именем файла на компьютере.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Файл не существует или не существует в указанном месте. Проверьте правильность написания имени файла и путь к нему.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Не следует полагаться на имя файла, чтобы определить содержимое файла. Например, файл `myFile.cs` может вовсе не быть исходным файлом C#.  
  
## <a name="see-also"></a>См. также

- <xref:System.IO?displayProperty=nameWithType>
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)
