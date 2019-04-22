---
title: Недопустимый режим файла
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: d3d0ebd003f178567ec9e9b19d6baccb8bc15f60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819987"
---
# <a name="bad-file-mode"></a><span data-ttu-id="cf874-102">Недопустимый режим файла</span><span class="sxs-lookup"><span data-stu-id="cf874-102">Bad file mode</span></span>
<span data-ttu-id="cf874-103">Операторы, используемые для управления содержимое файла должны соответствовать в режим, в котором был открыт файл.</span><span class="sxs-lookup"><span data-stu-id="cf874-103">Statements used in manipulating file contents must be appropriate to the mode in which the file was opened.</span></span> <span data-ttu-id="cf874-104">Возможные причины:</span><span class="sxs-lookup"><span data-stu-id="cf874-104">Possible causes include:</span></span>  
  
-   <span data-ttu-id="cf874-105">Объект `FilePutObject` или `FileGetObject` инструкция указывает последовательный файл.</span><span class="sxs-lookup"><span data-stu-id="cf874-105">A `FilePutObject` or `FileGetObject` statement specifies a sequential file.</span></span>  
  
-   <span data-ttu-id="cf874-106">Объект `Print` инструкция указывает файл, открытый в режиме доступа, отличное от `Output` или `Append`.</span><span class="sxs-lookup"><span data-stu-id="cf874-106">A `Print` statement specifies a file opened for an access mode other than `Output` or `Append`.</span></span>  
  
-   <span data-ttu-id="cf874-107">`Input` Инструкция указывает файл, открытый в режиме доступа, отличное от `Input`</span><span class="sxs-lookup"><span data-stu-id="cf874-107">An `Input` statement specifies a file opened for an access mode other than `Input`</span></span>  
  
-   <span data-ttu-id="cf874-108">Предпринята попытка записи в файл только для чтения.</span><span class="sxs-lookup"><span data-stu-id="cf874-108">An attempt to write to a read-only file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf874-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cf874-109">To correct this error</span></span>  
  
-   <span data-ttu-id="cf874-110">Убедитесь, что `FilePutObject` и `FileGetObject` ссылаются только на файлы, открытые для `Random` или `Binary` доступа.</span><span class="sxs-lookup"><span data-stu-id="cf874-110">Make sure `FilePutObject` and `FileGetObject` are only referring to files open for `Random` or `Binary` access.</span></span>  
  
-   <span data-ttu-id="cf874-111">Убедитесь, что `Print` указывает файл, открытый в `Output` или `Append` режим доступа.</span><span class="sxs-lookup"><span data-stu-id="cf874-111">Make sure `Print` specifies a file opened for either `Output` or `Append` access mode.</span></span> <span data-ttu-id="cf874-112">В противном случае используйте другой инструкции для размещения данных в файл или открыть файл в нужный режим.</span><span class="sxs-lookup"><span data-stu-id="cf874-112">If not, use a different statement to place data in the file, or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="cf874-113">Убедитесь, что `Input` указывает файл, открытый в `Input`.</span><span class="sxs-lookup"><span data-stu-id="cf874-113">Make sure `Input` specifies a file opened for `Input`.</span></span> <span data-ttu-id="cf874-114">В противном случае используйте другой инструкции для размещения данных в файл или открыть файл в нужный режим.</span><span class="sxs-lookup"><span data-stu-id="cf874-114">If not, use a different statement to place data in the file or reopen the file in an appropriate mode.</span></span>  
  
-   <span data-ttu-id="cf874-115">Если вы создаете в файл только для чтения, изменить состояние чтения и записи файла или не пытайтесь для записи в него.</span><span class="sxs-lookup"><span data-stu-id="cf874-115">If you are writing to a read-only file, change the read/write status of the file or do not try to write to it.</span></span>  
  
-   <span data-ttu-id="cf874-116">Используйте функциональность объекта `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="cf874-116">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf874-117">См. также</span><span class="sxs-lookup"><span data-stu-id="cf874-117">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem>
- [<span data-ttu-id="cf874-118">Устранение неполадок. Чтение из текстовых файлов и запись в такие файлы</span><span class="sxs-lookup"><span data-stu-id="cf874-118">Troubleshooting: Reading from and Writing to Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
