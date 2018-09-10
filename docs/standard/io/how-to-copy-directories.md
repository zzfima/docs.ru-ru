---
title: Практическое руководство. Копирование каталогов
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f2c2fbd58b10af80a2a233cbd4211befe2dbd33
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216058"
---
# <a name="how-to-copy-directories"></a>Практическое руководство. Копирование каталогов
В этом примере демонстрируется использование классов ввода-вывода для синхронного копирования содержимого каталога в другое место. В этом примере пользователь может указать, следует ли также копировать подкаталоги. Если подкаталоги копируются, метод в этом примере рекурсивно копирует их путем вызова самого себя для каждого последующего подкаталога, пока не будет скопировано все.  
  
 Пример асинхронного копирования файлов см. в разделе [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.IO.FileInfo>  
- <xref:System.IO.DirectoryInfo>  
- <xref:System.IO.FileStream>  
- [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)  
- [Распространенные задачи ввода-вывода](../../../docs/standard/io/common-i-o-tasks.md)  
- [Асинхронный файловый ввод-вывод](../../../docs/standard/io/asynchronous-file-i-o.md)
