---
title: "Практическое руководство. Чтение из текстового файла (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- StreamReader.ReadToEnd
dev_langs:
- CSharp
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bd0ad3e062c4d4b32fb6140cacba9a4a32674759
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Практическое руководство. Чтение из текстового файла (Руководство по программированию на C#)
В этом примере считывается содержимое текстового файла с помощью статических методов <xref:System.IO.File.ReadAllText%2A> и <xref:System.IO.File.ReadAllLines%2A> из класса <xref:System.IO.File?displayProperty=fullName>.  
  
 Пример, использующий <xref:System.IO.StreamReader>, см. в разделе [Практическое руководство. Построчное чтение текстового файла](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
>  Файлы, которые используются в этом примере, созданы в разделе [Практическое руководство. Запись в текстовый файл](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).  
  
## <a name="example"></a>Пример  
 [!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-read-from-a-text-file_1.cs)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код и вставьте его в консольное приложение C#.  
  
 Если вы не используете текстовые файлы из раздела [Практическое руководство. Запись в текстовый файл](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), замените аргумент `ReadAllText` и `ReadAllLines` на соответствующий путь и имя файла на компьютере.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Файл не существует или не существует в указанном месте. Проверьте правильность написания имени файла и путь к нему.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Не следует полагаться на имя файла, чтобы определить содержимое файла. Например, файл `myFile.cs` может вовсе не быть исходным файлом C#.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)

