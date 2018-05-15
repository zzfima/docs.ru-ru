---
title: Указано недопустимое имя для журнала событий
ms.date: 07/20/2015
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
ms.openlocfilehash: 8b6df077f15744cd2c34fb9e7e148b02ea27d5bf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a><span data-ttu-id="344fa-102">Указано недопустимое имя для журнала событий</span><span class="sxs-lookup"><span data-stu-id="344fa-102">An invalid name was specified for the event log</span></span>
<span data-ttu-id="344fa-103">Для журнала событий было указано недопустимое имя.</span><span class="sxs-lookup"><span data-stu-id="344fa-103">An invalid name was specified for the event log.</span></span> <span data-ttu-id="344fa-104">Обычно это является результатом недопустимых символов в имени, пустого имени файла или слишком длинного имени файла.</span><span class="sxs-lookup"><span data-stu-id="344fa-104">Usually this is a result of invalid characters in the name, a blank file name, or a file name that is too long.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="344fa-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="344fa-105">To correct this error</span></span>  
  
-   <span data-ttu-id="344fa-106">Если указанное имя содержит более восьми символов, убедитесь, что отсутствует конфликт с именами других журналов событий.</span><span class="sxs-lookup"><span data-stu-id="344fa-106">If the specified name is more than eight characters, make sure there is no conflict with the names of other event logs.</span></span> <span data-ttu-id="344fa-107">При определении уникальности имени оцениваются только первые восемь символов.</span><span class="sxs-lookup"><span data-stu-id="344fa-107">Only the first eight characters are evaluated when determining if the name is unique.</span></span>  
  
-   <span data-ttu-id="344fa-108">Если указывается путь, убедитесь, что он анализируется правильно.</span><span class="sxs-lookup"><span data-stu-id="344fa-108">If supplying a path, make sure it is parsed correctly.</span></span>  
  
-   <span data-ttu-id="344fa-109">Проверьте имя на наличие недопустимых символов.</span><span class="sxs-lookup"><span data-stu-id="344fa-109">Check that there are no invalid characters in the name.</span></span> <span data-ttu-id="344fa-110">Символы, которые нельзя использовать в имени файла: `<`, `>`, `:`, `"`, `/`, `\`и `|`.</span><span class="sxs-lookup"><span data-stu-id="344fa-110">Characters that cannot be used in a file name include `<`, `>`, `:`, `"`, `/`, `\`, and `|`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="344fa-111">См. также</span><span class="sxs-lookup"><span data-stu-id="344fa-111">See Also</span></span>  
 [<span data-ttu-id="344fa-112">Практическое руководство. Анализ путей к файлам</span><span class="sxs-lookup"><span data-stu-id="344fa-112">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [<span data-ttu-id="344fa-113">Практическое руководство. Переименование файла</span><span class="sxs-lookup"><span data-stu-id="344fa-113">How to: Rename a File</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 
