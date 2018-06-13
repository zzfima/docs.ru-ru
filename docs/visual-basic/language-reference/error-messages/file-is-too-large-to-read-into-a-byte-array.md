---
title: Файл слишком велик для чтения в массив байтов
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 1b04d47cab77269a0ce84ef77c162a4401d99d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585929"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>Файл слишком велик для чтения в массив байтов
Размер файла, который вы пытаетесь считать в массив байтов превышает 4 ГБ. `My.Computer.FileSystem.ReadAllBytes` Метод не может считать файл большего размера.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте <xref:System.IO.StreamReader> для чтения файла. Дополнительные сведения см. в разделе [основы из .NET Framework файлового ввода-вывода и файловой системы (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [Доступ к файлам с помощью Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [Практическое руководство. Чтение текста из файлов с помощью StreamReader](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
