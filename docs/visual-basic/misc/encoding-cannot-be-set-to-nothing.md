---
title: Параметру Encoding нельзя присвоить значение Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 30b0b4a29fbdf931aa62263b75d1fa946e87b145
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58028442"
---
# <a name="encoding-cannot-be-set-to-nothing"></a><span data-ttu-id="d544f-102">Параметру Encoding нельзя присвоить значение Nothing</span><span class="sxs-lookup"><span data-stu-id="d544f-102">Encoding cannot be set to Nothing</span></span>
<span data-ttu-id="d544f-103">Не удалось выполнить чтение или запись в файл, так как параметр `encoding` установлен в значение `Nothing` , но требует допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="d544f-103">An attempt to read from or write to a file has failed because the parameter `encoding` has been set to `Nothing` but requires a valid value.</span></span>  
  
 <span data-ttu-id="d544f-104"><xref:System.Text.Encoding> используется для определения, какая кодировка должна использоваться при записи в файл.</span><span class="sxs-lookup"><span data-stu-id="d544f-104"><xref:System.Text.Encoding> is used to determine what encoding to use when writing to a file.</span></span> <span data-ttu-id="d544f-105">Кодировка по умолчанию — UTF-8.</span><span class="sxs-lookup"><span data-stu-id="d544f-105">The default is UTF-8.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d544f-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d544f-106">To correct this error</span></span>  
  
-   <span data-ttu-id="d544f-107">Предоставьте допустимое значение для параметра `encoding` .</span><span class="sxs-lookup"><span data-stu-id="d544f-107">Supply a valid value for the `encoding` parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d544f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d544f-108">See also</span></span>

- [<span data-ttu-id="d544f-109">Кодировки файлов</span><span class="sxs-lookup"><span data-stu-id="d544f-109">File Encodings</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md)
- [<span data-ttu-id="d544f-110">Чтение из файлов</span><span class="sxs-lookup"><span data-stu-id="d544f-110">Reading from Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)
- [<span data-ttu-id="d544f-111">Запись в файлы</span><span class="sxs-lookup"><span data-stu-id="d544f-111">Writing to Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)
- [<span data-ttu-id="d544f-112">My.Computer.FileSystem.ReadAllText</span><span class="sxs-lookup"><span data-stu-id="d544f-112">My.Computer.FileSystem.ReadAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [<span data-ttu-id="d544f-113">My.Computer.FileSystem.WriteAllText</span><span class="sxs-lookup"><span data-stu-id="d544f-113">My.Computer.FileSystem.WriteAllText</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
