---
title: Ошибка доступа к пути файла
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 83ce8615b173a6f5835347ebc561a793655ec8f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598587"
---
# <a name="pathfile-access-error"></a><span data-ttu-id="edbb5-102">Ошибка доступа к пути/файлу</span><span class="sxs-lookup"><span data-stu-id="edbb5-102">Path/File access error</span></span>
<span data-ttu-id="edbb5-103">Во время операции доступа к файлам или доступа к диску операционной системы не может сделать соединение между путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="edbb5-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="edbb5-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="edbb5-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="edbb5-105">Убедитесь, что спецификация файла имеет правильный формат.</span><span class="sxs-lookup"><span data-stu-id="edbb5-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="edbb5-106">Имя файла может содержать полный (абсолютный) или относительный путь.</span><span class="sxs-lookup"><span data-stu-id="edbb5-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="edbb5-107">Полный путь начинается с имени диска (если путь находится на другом диске) и содержит явный путь от корня для файла.</span><span class="sxs-lookup"><span data-stu-id="edbb5-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="edbb5-108">Любой, не полный путь задается относительно текущего диска и каталога.</span><span class="sxs-lookup"><span data-stu-id="edbb5-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="edbb5-109">Убедитесь, что вы не была предпринята попытка сохранить файл, который заменит существующий файл только для чтения.</span><span class="sxs-lookup"><span data-stu-id="edbb5-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="edbb5-110">Если это так, измените атрибут только для чтения целевого файла или сохраните файл с другим именем.</span><span class="sxs-lookup"><span data-stu-id="edbb5-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="edbb5-111">Убедитесь, что не была предпринята попытка открыть файл только для чтения в режиме `Output` или `Append` режиме.</span><span class="sxs-lookup"><span data-stu-id="edbb5-111">Make sure you did not attempt to open a read-only file in sequential `Output` or `Append` mode.</span></span> <span data-ttu-id="edbb5-112">Если это так, откройте файл в `Input` режиме или измените атрибут только для чтения файла.</span><span class="sxs-lookup"><span data-stu-id="edbb5-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="edbb5-113">Убедитесь, что не была предпринята попытка изменить проект Visual Basic в пределах базы данных или документа.</span><span class="sxs-lookup"><span data-stu-id="edbb5-113">Make sure you did not attempt to change a Visual Basic project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edbb5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="edbb5-114">See Also</span></span>  
 [<span data-ttu-id="edbb5-115">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="edbb5-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
