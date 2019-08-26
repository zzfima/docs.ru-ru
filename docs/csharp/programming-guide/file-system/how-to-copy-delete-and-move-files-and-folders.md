---
title: Практическое руководство. Копирование, удаление и перемещение файлов и папок (руководство по программированию на C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: dd32798062dbfc9a10acd27ce51d8d5dd3b164f6
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590086"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Практическое руководство. Копирование, удаление и перемещение файлов и папок (руководство по программированию на C#)
В следующих примерах показано, как синхронно копировать, перемещать и удалять файлы и папки с помощью классов <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, и <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> из пространства имен <xref:System.IO?displayProperty=nameWithType>. В этих примерах не используется индикатор хода выполнения или какой-либо иной пользовательский интерфейс. Сведения о том, как предоставить стандартное диалоговое окно "Ход выполнения операций", см. в [этом практическом руководстве](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.IO?displayProperty=nameWithType>
- [Руководство по программированию на C#](../index.md)
- [Файловая система и реестр (руководство по программированию на C#)](index.md)
- [Практическое руководство. Отображение диалогового окна "Ход выполнения" для операций с файлами](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [Файловый и потоковый ввод-вывод](../../../standard/io/index.md)
- [Распространенные задачи ввода-вывода](../../../standard/io/common-i-o-tasks.md)
