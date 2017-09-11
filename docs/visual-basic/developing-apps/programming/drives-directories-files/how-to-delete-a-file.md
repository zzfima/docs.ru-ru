---
title: "Практическое руководство. Удаление файла в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Delete method
- files, deleting
- files, manipulating
- File object
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: e4b0b87fd403556777e0ab5a1edd517687360374
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-delete-a-file-in-visual-basic"></a><span data-ttu-id="75ec0-102">Практическое руководство. Удаление файла в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75ec0-102">How to: Delete a File in Visual Basic</span></span>
<span data-ttu-id="75ec0-103">Метод `DeleteFile` объекта `My.Computer.FileSystem` позволяет удалить файл.</span><span class="sxs-lookup"><span data-stu-id="75ec0-103">The `DeleteFile` method of the `My.Computer.FileSystem` object allows you to delete a file.</span></span> <span data-ttu-id="75ec0-104">Параметры метода позволяют указать, следует ли отправлять удаленный файл в **корзину**, следует ли запрашивать у пользователя подтверждение удаления файла и что делать при отмене пользователем операции.</span><span class="sxs-lookup"><span data-stu-id="75ec0-104">Among the options it offers are: whether to send the deleted file to the **Recycle Bin**, whether to ask the user to confirm that the file should be deleted, and what to do when the user cancels the operation.</span></span>  
  
### <a name="to-delete-a-text-file"></a><span data-ttu-id="75ec0-105">Удаление текстового файла</span><span class="sxs-lookup"><span data-stu-id="75ec0-105">To delete a text file</span></span>  
  
-   <span data-ttu-id="75ec0-106">Для удаления файла используйте метод `DeleteFile`.</span><span class="sxs-lookup"><span data-stu-id="75ec0-106">Use the `DeleteFile` method to delete the file.</span></span> <span data-ttu-id="75ec0-107">В следующем коде показано, как удалить файл с именем `test.txt`.</span><span class="sxs-lookup"><span data-stu-id="75ec0-107">The following code demonstrates how to delete the file named `test.txt`.</span></span>  
  
     <span data-ttu-id="75ec0-108">[!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="75ec0-108">[!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]</span></span>  
  
### <a name="to-delete-a-text-file-and-ask-the-user-to-confirm-that-the-file-should-be-deleted"></a><span data-ttu-id="75ec0-109">Удаление текстового файла с запросом подтверждения удаления файла</span><span class="sxs-lookup"><span data-stu-id="75ec0-109">To delete a text file and ask the user to confirm that the file should be deleted</span></span>  
  
-   <span data-ttu-id="75ec0-110">Для удаления файла используйте метод `DeleteFile`, присвоив параметру`showUI` значение `AllDialogs`.</span><span class="sxs-lookup"><span data-stu-id="75ec0-110">Use the `DeleteFile` method to delete the file, setting `showUI` to `AllDialogs`.</span></span> <span data-ttu-id="75ec0-111">В следующем коде демонстрируется удаление файла `test.txt` с запросом у пользователя подтверждения удаления файла.</span><span class="sxs-lookup"><span data-stu-id="75ec0-111">The following code demonstrates how to delete the file named `test.txt` and allow the user to confirm that the file should be deleted.</span></span>  
  
     <span data-ttu-id="75ec0-112">[!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="75ec0-112">[!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]</span></span>  
  
### <a name="to-delete-a-text-file-and-send-it-to-the-recycle-bin"></a><span data-ttu-id="75ec0-113">Удаление текстового файла и отправка его в корзину</span><span class="sxs-lookup"><span data-stu-id="75ec0-113">To delete a text file and send it to the Recycle Bin</span></span>  
  
-   <span data-ttu-id="75ec0-114">Для удаления файла используйте метод `DeleteFile`, присвоив параметру `SendToRecycleBin` значение `recycle`.</span><span class="sxs-lookup"><span data-stu-id="75ec0-114">Use the `DeleteFile` method to delete the file, specifying `SendToRecycleBin` for the `recycle` parameter.</span></span> <span data-ttu-id="75ec0-115">В следующем коде демонстрируется удаление файла `test.txt` и отправка его в **корзину**.</span><span class="sxs-lookup"><span data-stu-id="75ec0-115">The following code demonstrates how to delete the file named `test.txt` and send it to the **Recycle Bin**.</span></span>  
  
     <span data-ttu-id="75ec0-116">[!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="75ec0-116">[!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="75ec0-117">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="75ec0-117">Robust Programming</span></span>  
 <span data-ttu-id="75ec0-118">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="75ec0-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="75ec0-119">Путь является недопустимым, так как он представляет собой строку нулевой длины (пустую строку), либо содержит только пробелы, либо содержит недопустимые знаки, либо представляет собой путь к устройству (начинается с символов \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-119">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="75ec0-120">Путь не является допустимым, поскольку он равен `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-120">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="75ec0-121">Длина пути превышает максимальную длину, определенную в системе (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-121">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="75ec0-122">Имя файла или папки в пути содержит двоеточие (:) или имеет недопустимый формат (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-122">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="75ec0-123">Файл уже используется (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-123">The file is in use (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="75ec0-124">У пользователя отсутствуют необходимые разрешения на просмотр пути (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-124">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="75ec0-125">Файл не существует (<xref:System.IO.FileNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-125">The file does not exist (<xref:System.IO.FileNotFoundException>).</span></span>  
  
-   <span data-ttu-id="75ec0-126">Пользователь не имеет разрешения на удаление файла, или файл доступен только для чтения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-126">The user does not have permission to delete the file, or the file is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
-   <span data-ttu-id="75ec0-127">Существует ситуация частичного доверия, в которой пользователь не имеет достаточных разрешений для доступа к файлу (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-127">A partial-trust situation exists in which the user does not have sufficient permissions (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="75ec0-128">Пользователь отменил действие и `onUserCancel` задано `ThrowException` (<xref:System.OperationCanceledException>).</span><span class="sxs-lookup"><span data-stu-id="75ec0-128">The user cancelled the operation and `onUserCancel` is set to `ThrowException` (<xref:System.OperationCanceledException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ec0-129">См. также</span><span class="sxs-lookup"><span data-stu-id="75ec0-129">See Also</span></span>  
 <span data-ttu-id="75ec0-130"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span><span class="sxs-lookup"><span data-stu-id="75ec0-130"><xref:Microsoft.VisualBasic.FileIO.UICancelOption></span></span>   
 <span data-ttu-id="75ec0-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="75ec0-131"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="75ec0-132"><xref:Microsoft.VisualBasic.FileIO.UIOption></span><span class="sxs-lookup"><span data-stu-id="75ec0-132"><xref:Microsoft.VisualBasic.FileIO.UIOption></span></span>   
 <span data-ttu-id="75ec0-133"><xref:Microsoft.VisualBasic.FileIO.RecycleOption></span><span class="sxs-lookup"><span data-stu-id="75ec0-133"><xref:Microsoft.VisualBasic.FileIO.RecycleOption></span></span>   
 [<span data-ttu-id="75ec0-134">Практическое руководство. Получение коллекции содержащихся в каталоге файлов</span><span class="sxs-lookup"><span data-stu-id="75ec0-134">How to: Get the Collection of Files in a Directory</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)

