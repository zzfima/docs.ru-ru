---
title: Руководство по программированию на C#. Как копировать, удалять, перемещать файлы и папки
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 662f0ab3b9e69aa8bfb0085f42f577b850029e4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712277"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Руководство по программированию на C#. Копирование, удаление, перемещение файлов и папок
В следующих примерах показано, как синхронно копировать, перемещать и удалять файлы и папки с помощью классов <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, и <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> из пространства имен <xref:System.IO?displayProperty=nameWithType>. В этих примерах не используется индикатор хода выполнения или какой-либо иной пользовательский интерфейс. Если нужно использовать стандартное диалоговое окна хода выполнения, см. практическое руководство [Отображение диалогового окна хода выполнения для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Используйте <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> для предоставления событий, которые позволяют вычислять ход выполнения при работе с несколькими файлами. Другим подходом является использование вызова неуправляемого кода для вызова в Windows Shell методов, относящихся к обработке файлов. Сведения о способах асинхронного выполнения таких операций над файлами см. в разделе [Асинхронный файловый ввод-вывод](../../../standard/io/asynchronous-file-i-o.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как копировать файлы и каталоги.  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как перемещать файлы и каталоги.  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как удалять файлы и каталоги.  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO?displayProperty=nameWithType>
- [Руководство по программированию на C#](../index.md)
- [Файловая система и реестр (руководство по программированию на C#)](index.md)
- [Практическое руководство. Предоставление диалогового окна "Ход выполнения" для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [Файловый и потоковый ввод-вывод](../../../standard/io/index.md)
- [Распространенные задачи ввода-вывода](../../../standard/io/common-i-o-tasks.md)
