---
title: "Ошибка доступа к файлу путь | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID75
dev_langs:
- VB
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6307c0d0115e3791d5ad6bf4243057e6ed90d9cd
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="pathfile-access-error"></a><span data-ttu-id="7396b-102">Ошибка доступа к пути/файлу</span><span class="sxs-lookup"><span data-stu-id="7396b-102">Path/File access error</span></span>
<span data-ttu-id="7396b-103">Во время операции доступа к файлам или доступа к диску операционной системы не удается установить связь между путь и имя файла.</span><span class="sxs-lookup"><span data-stu-id="7396b-103">During a file-access or disk-access operation, the operating system could not make a connection between the path and the file name.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7396b-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="7396b-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="7396b-105">Убедитесь, что спецификация файла правильно отформатирован.</span><span class="sxs-lookup"><span data-stu-id="7396b-105">Make sure the file specification is correctly formatted.</span></span> <span data-ttu-id="7396b-106">Имя файла может содержать полный (абсолютный) или относительный путь.</span><span class="sxs-lookup"><span data-stu-id="7396b-106">A file name can contain a fully qualified (absolute) or relative path.</span></span> <span data-ttu-id="7396b-107">Полный путь начинается с имени диска (если путь находится на другом диске) и содержит явный путь от корня к файлу.</span><span class="sxs-lookup"><span data-stu-id="7396b-107">A fully qualified path starts with the drive name (if the path is on another drive) and lists the explicit path from the root to the file.</span></span> <span data-ttu-id="7396b-108">Любой путь, который не является полным задается относительно текущего диска и каталога.</span><span class="sxs-lookup"><span data-stu-id="7396b-108">Any path that is not fully qualified is relative to the current drive and directory.</span></span>  
  
2.  <span data-ttu-id="7396b-109">Убедитесь, что вы не была предпринята попытка сохранить файл, который заменит существующий файл только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7396b-109">Make sure that you did not attempt to save a file that would replace an existing read-only file.</span></span> <span data-ttu-id="7396b-110">Если это так, измените атрибут только для чтения целевого файла или сохраните файл с другим именем файла.</span><span class="sxs-lookup"><span data-stu-id="7396b-110">If this is the case, change the read-only attribute of the target file, or save the file with a different file name.</span></span>  
  
3.  <span data-ttu-id="7396b-111">Убедитесь, что не была предпринята попытка открыть файл только для чтения в режиме`Output`или `Append` режиме.</span><span class="sxs-lookup"><span data-stu-id="7396b-111">Make sure you did not attempt to open a read-only file in sequential`Output`or `Append` mode.</span></span> <span data-ttu-id="7396b-112">Если это так, откройте файл в `Input` режиме или измените атрибут "только для чтения" файла.</span><span class="sxs-lookup"><span data-stu-id="7396b-112">If this is the case, open the file in `Input` mode or change the read-only attribute of the file.</span></span>  
  
4.  <span data-ttu-id="7396b-113">Убедитесь, что не была предпринята попытка изменить [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проекта в пределах базы данных или документа.</span><span class="sxs-lookup"><span data-stu-id="7396b-113">Make sure you did not attempt to change a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project within a database or document.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7396b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7396b-114">See Also</span></span>  
 [<span data-ttu-id="7396b-115">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="7396b-115">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
