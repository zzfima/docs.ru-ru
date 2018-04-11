---
title: Недопустимый режим файла
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a><span data-ttu-id="6b15e-102">Недопустимый режим файла</span><span class="sxs-lookup"><span data-stu-id="6b15e-102">Bad file mode</span></span>
<span data-ttu-id="6b15e-103">Операторы, используемые для управления содержимым файла должны соответствовать режим, в котором открыт файл.</span><span class="sxs-lookup"><span data-stu-id="6b15e-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="6b15e-104">Возможные причины:</span><span class="sxs-lookup"><span data-stu-id="6b15e-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="6b15e-105">Объект `FilePutObject` или `FileGetObject` инструкция указывает последовательный файл.</span><span class="sxs-lookup"><span data-stu-id="6b15e-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="6b15e-106">Объект `Print` инструкция указывает файл, открытый в режиме доступа, отличный от `Output` или `Append`.</span><span class="sxs-lookup"><span data-stu-id="6b15e-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="6b15e-107">`Input` Инструкция указывает файл, открытый в режиме доступа, отличный от`Input`</span><span class="sxs-lookup"><span data-stu-id="6b15e-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="6b15e-108">Попытка записи в файл только для чтения.</span><span class="sxs-lookup"><span data-stu-id="6b15e-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6b15e-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6b15e-109">To correct this error</span></span>  
  
-   <span data-ttu-id="6b15e-110">Убедитесь, что `FilePutObject` и `FileGetObject` ссылаются только на файлы, открытые для `Random` или `Binary` доступа.</span><span class="sxs-lookup"><span data-stu-id="6b15e-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="6b15e-111">Убедитесь, что `Print` указывает файл, открытый в `Output` или `Append` режим доступа.</span><span class="sxs-lookup"><span data-stu-id="6b15e-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="6b15e-112">В противном случае используйте другой инструкции для размещения данных в файл или открыть файл в нужный режим.</span><span class="sxs-lookup"><span data-stu-id="6b15e-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="6b15e-113">Убедитесь, что `Input` задает файл, открытый для `Input`.</span><span class="sxs-lookup"><span data-stu-id="6b15e-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="6b15e-114">В противном случае используйте другой инструкции для размещения данных в файл или открыть файл в нужный режим.</span><span class="sxs-lookup"><span data-stu-id="6b15e-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="6b15e-115">При записи в файл только для чтения, изменения состояния чтения и записи файла или не пытайтесь выполнить запись в него.</span><span class="sxs-lookup"><span data-stu-id="6b15e-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="6b15e-116">Используйте функциональность объекта `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="6b15e-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b15e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="6b15e-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [<span data-ttu-id="6b15e-118">Исправление неполадок, связанных с чтением из текстовых файлов и записью в такие файлы</span><span class="sxs-lookup"><span data-stu-id="6b15e-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
