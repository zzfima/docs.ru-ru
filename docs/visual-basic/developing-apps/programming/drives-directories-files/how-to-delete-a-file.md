---
title: Практическое руководство. Удаление файла
ms.date: 07/20/2015
helpviewer_keywords:
- Delete method [Visual Basic]
- files [Visual Basic], deleting
- files [Visual Basic], manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
ms.openlocfilehash: 57182f1a1d92b7fe954fd26b32c5e4b1107823ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74348782"
---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="59ba3-102">Практическое руководство. Удаление файла в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="59ba3-102">How to: Delete a File in Visual Basic</span></span>

<span data-ttu-id="59ba3-103">Метод `DeleteFile` объекта `My.Computer.FileSystem` позволяет удалить файл.</span><span class="sxs-lookup"><span data-stu-id="59ba3-103">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="59ba3-104">Параметры метода позволяют указать, следует ли отправлять удаленный файл в **корзину**, следует ли запрашивать у пользователя подтверждение удаления файла и что делать при отмене пользователем операции.</span><span class="sxs-lookup"><span data-stu-id="59ba3-104">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="59ba3-105">Удаление текстового файла</span><span class="sxs-lookup"><span data-stu-id="59ba3-105">To delete a text file</span></span>  
  
- <span data-ttu-id="59ba3-106">Для удаления файла используйте метод `DeleteFile`.</span><span class="sxs-lookup"><span data-stu-id="59ba3-106">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="59ba3-107">В следующем коде показано, как удалить файл с именем `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="59ba3-107">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#22)]  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="59ba3-108">Удаление текстового файла с запросом подтверждения удаления файла</span><span class="sxs-lookup"><span data-stu-id="59ba3-108">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
- <span data-ttu-id="59ba3-109">Для удаления файла используйте метод `DeleteFile`, присвоив параметру`showUI` значение `AllDialogs`.</span><span class="sxs-lookup"><span data-stu-id="59ba3-109">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="59ba3-110">В следующем коде демонстрируется удаление файла `test.txt` с запросом у пользователя подтверждения удаления файла.</span><span class="sxs-lookup"><span data-stu-id="59ba3-110">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     [!code-vb[VbFileIOMisc#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#9)]  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="59ba3-111">Удаление текстового файла и отправка его в корзину</span><span class="sxs-lookup"><span data-stu-id="59ba3-111">To delete a text file and send it to the Recycle Bin</span></span>  
  
- <span data-ttu-id="59ba3-112">Для удаления файла используйте метод `DeleteFile`, присвоив параметру `SendToRecycleBin` значение `recycle`.</span><span class="sxs-lookup"><span data-stu-id="59ba3-112">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="59ba3-113">В следующем коде демонстрируется удаление файла `test.txt` и отправка его в **корзину**.</span><span class="sxs-lookup"><span data-stu-id="59ba3-113">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     [!code-vb[VbFileIOMisc#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#10)]  
  
## <a name="robust-programming"></a><span data-ttu-id="59ba3-114">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="59ba3-114">Robust Programming</span></span>  

 <span data-ttu-id="59ba3-115">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="59ba3-115">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="59ba3-116">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-116">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
- <span data-ttu-id="59ba3-117">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-117">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
- <span data-ttu-id="59ba3-118">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-118">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="59ba3-119">Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-119">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
- <span data-ttu-id="59ba3-120">Файл уже используется (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-120">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="59ba3-121">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-121">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="59ba3-122">Файл не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-122">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
- <span data-ttu-id="59ba3-123">Пользователь не имеет разрешения на удаление файла, или файл доступен только для чтения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-123">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
- <span data-ttu-id="59ba3-124">Существует ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-124">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
- <span data-ttu-id="59ba3-125">Пользователь отменил действие и `onUserCancel` задано `ThrowException` (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="59ba3-125">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ba3-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="59ba3-126">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.UICancelOption>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.UIOption>
- <xref:Microsoft.VisualBasic.FileIO.RecycleOption>
- [<span data-ttu-id="59ba3-127">Практическое руководство. Получение коллекции содержащихся в каталоге файлов</span><span class="sxs-lookup"><span data-stu-id="59ba3-127">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)
