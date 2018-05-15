---
title: Файл слишком велик для чтения в массив байтов
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 1b04d47cab77269a0ce84ef77c162a4401d99d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="ca8b6-102">Файл слишком велик для чтения в массив байтов</span><span class="sxs-lookup"><span data-stu-id="ca8b6-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="ca8b6-103">Размер файла, который вы пытаетесь считать в массив байтов превышает 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="ca8b6-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="ca8b6-104">`My.Computer.FileSystem.ReadAllBytes` Метод не может считать файл большего размера.</span><span class="sxs-lookup"><span data-stu-id="ca8b6-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ca8b6-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ca8b6-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ca8b6-106">Используйте <xref:System.IO.StreamReader> для чтения файла.</span><span class="sxs-lookup"><span data-stu-id="ca8b6-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="ca8b6-107">Дополнительные сведения см. в разделе [основы из .NET Framework файлового ввода-вывода и файловой системы (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="ca8b6-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca8b6-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ca8b6-108">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [<span data-ttu-id="ca8b6-109">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ca8b6-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [<span data-ttu-id="ca8b6-110">Практическое руководство. Чтение текста из файлов с помощью StreamReader</span><span class="sxs-lookup"><span data-stu-id="ca8b6-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
