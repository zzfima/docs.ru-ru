---
title: Файл слишком велик для чтения в массив байтов
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 0c7d35e08eeb42e35c4c40e47434a64393d829b1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831518"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="6b132-102">Файл слишком велик для чтения в массив байтов</span><span class="sxs-lookup"><span data-stu-id="6b132-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="6b132-103">Размер файла, который вы пытаетесь считать в массив байтов превышает 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="6b132-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="6b132-104">`My.Computer.FileSystem.ReadAllBytes` Метод не может прочитать файл большего размера.</span><span class="sxs-lookup"><span data-stu-id="6b132-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b132-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6b132-105">To correct this error</span></span>  
  
-   <span data-ttu-id="6b132-106">Используйте <xref:System.IO.StreamReader> для чтения файла.</span><span class="sxs-lookup"><span data-stu-id="6b132-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="6b132-107">Дополнительные сведения см. в разделе [основы из .NET Framework файлового ввода-вывода и файловой системе (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span><span class="sxs-lookup"><span data-stu-id="6b132-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b132-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6b132-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="6b132-109">Доступ к файлам с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b132-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="6b132-110">Практическое руководство. Чтение текста из файлов с помощью StreamReader</span><span class="sxs-lookup"><span data-stu-id="6b132-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
