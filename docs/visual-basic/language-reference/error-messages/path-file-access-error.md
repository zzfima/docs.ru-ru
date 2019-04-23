---
title: Ошибка доступа к пути / файлу
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 4f18c9216aa24840bc205534a97124d12698cb98
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342158"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="58a58-102">Ошибка доступа к пути/файлу</span><span class="sxs-lookup"><span data-stu-id="58a58-102">Path/File access error</span></span>
<span data-ttu-id="58a58-103">В ходе операции доступа к файлам или доступа к диску операционной системы не может установить подключение между путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="58a58-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="58a58-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="58a58-104">To correct this error</span></span>  
  
1. <span data-ttu-id="58a58-105">Убедитесь, что спецификация файла имеет правильный формат.</span><span class="sxs-lookup"><span data-stu-id="58a58-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="58a58-106">Имя файла может содержать полный (абсолютный) или относительный путь.</span><span class="sxs-lookup"><span data-stu-id="58a58-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="58a58-107">Полный URL-адрес начинается с имени диска (если путь находится на другом диске) и содержит явный путь от корня к файлу.</span><span class="sxs-lookup"><span data-stu-id="58a58-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="58a58-108">Любой путь, который не является полным образом задается относительно текущего диска и каталога.</span><span class="sxs-lookup"><span data-stu-id="58a58-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2. <span data-ttu-id="58a58-109">Убедитесь, что вы не была предпринята попытка сохранить файл, который заменит существующий файл только для чтения.</span><span class="sxs-lookup"><span data-stu-id="58a58-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="58a58-110">Если это так, измените атрибут только для чтения целевого файла или сохраните файл с другим именем.</span><span class="sxs-lookup"><span data-stu-id="58a58-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3. <span data-ttu-id="58a58-111">Убедитесь, что не была предпринята попытка открыть файл только для чтения в последовательных `Output` или `Append` режиме.</span><span class="sxs-lookup"><span data-stu-id="58a58-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="58a58-112">Если это так, откройте файл в `Input` режиме или изменить атрибут только для чтения файла.</span><span class="sxs-lookup"><span data-stu-id="58a58-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4. <span data-ttu-id="58a58-113">Убедитесь, что не была предпринята попытка изменить проект Visual Basic в пределах базы данных или документа.</span><span class="sxs-lookup"><span data-stu-id="58a58-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a58-114">См. также</span><span class="sxs-lookup"><span data-stu-id="58a58-114">See also</span></span>

- [<span data-ttu-id="58a58-115">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="58a58-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
