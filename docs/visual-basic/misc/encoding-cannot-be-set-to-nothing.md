---
title: "Параметру Encoding нельзя присвоить значение Nothing"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa3567e47f170c64b45cbb9e49d7fa0026b8903
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="6f29c-102">Параметру Encoding нельзя присвоить значение Nothing</span><span class="sxs-lookup"><span data-stu-id="6f29c-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="6f29c-103">Не удалось выполнить чтение или запись в файл, так как параметр `encoding` установлен в значение `Nothing` , но требует допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="6f29c-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="6f29c-104"><xref:System.Text.Encoding> используется для определения, какая кодировка должна использоваться при записи в файл.</span><span class="sxs-lookup"><span data-stu-id="6f29c-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="6f29c-105">Кодировка по умолчанию — UTF-8.</span><span class="sxs-lookup"><span data-stu-id="6f29c-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6f29c-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6f29c-106">To correct this error</span></span>  
  
-   <span data-ttu-id="6f29c-107">Предоставьте допустимое значение для параметра `encoding` .</span><span class="sxs-lookup"><span data-stu-id="6f29c-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f29c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6f29c-108">See Also</span></span>  
 [<span data-ttu-id="6f29c-109">Кодировки файлов</span><span class="sxs-lookup"><span data-stu-id="6f29c-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)  
 [<span data-ttu-id="6f29c-110">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="6f29c-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)  
 [<span data-ttu-id="6f29c-111">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="6f29c-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)  
 [<span data-ttu-id="6f29c-112">Метод My.Computer.FileSystem.ReadAllText</span><span class="sxs-lookup"><span data-stu-id="6f29c-112">My.Computer.FileSystem.ReadAllText Method</span></span>](http://msdn.microsoft.com/en-us/3a7ac8be-fb1d-4087-bc65-167d6754d57f)  
 [<span data-ttu-id="6f29c-113">Метод My.Computer.FileSystem.WriteAllText</span><span class="sxs-lookup"><span data-stu-id="6f29c-113">My.Computer.FileSystem.WriteAllText Method</span></span>](http://msdn.microsoft.com/en-us/f507460c-87d9-4504-b74f-3ff825c7d5c4)
