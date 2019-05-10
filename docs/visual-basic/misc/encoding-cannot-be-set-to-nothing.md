---
title: Параметру Encoding нельзя присвоить значение Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 492db7755e8b2b75ea8c60d7f4e1ccc1a5ded865
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598354"
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="0b19f-102">Параметру Encoding нельзя присвоить значение Nothing</span><span class="sxs-lookup"><span data-stu-id="0b19f-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="0b19f-103">Не удалось выполнить чтение или запись в файл, так как параметр `encoding` установлен в значение `Nothing` , но требует допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="0b19f-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="0b19f-104"><xref:System.Text.Encoding> используется для определения, какая кодировка должна использоваться при записи в файл.</span><span class="sxs-lookup"><span data-stu-id="0b19f-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="0b19f-105">Кодировка по умолчанию — UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0b19f-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0b19f-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0b19f-106">To correct this error</span></span>  
  
- <span data-ttu-id="0b19f-107">Предоставьте допустимое значение для параметра `encoding` .</span><span class="sxs-lookup"><span data-stu-id="0b19f-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b19f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0b19f-108">See also</span></span>

- [<span data-ttu-id="0b19f-109">Кодировки файлов</span><span class="sxs-lookup"><span data-stu-id="0b19f-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [<span data-ttu-id="0b19f-110">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="0b19f-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="0b19f-111">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="0b19f-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="0b19f-112">My.Computer.FileSystem.ReadAllText</span><span class="sxs-lookup"><span data-stu-id="0b19f-112">My.Computer.FileSystem.ReadAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [<span data-ttu-id="0b19f-113">My.Computer.FileSystem.WriteAllText</span><span class="sxs-lookup"><span data-stu-id="0b19f-113">My.Computer.FileSystem.WriteAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
