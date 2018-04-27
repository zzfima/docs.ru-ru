---
title: 'Не удалось записать в выходной файл &#39; &lt;filename&gt;&#39;: &lt;ошибки&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a183f81a73c3c8034d9ba7366be8b36d425263da
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a><span data-ttu-id="a1690-102">Не удалось записать в выходной файл &#39; &lt;filename&gt;&#39;: &lt;ошибки&gt;</span><span class="sxs-lookup"><span data-stu-id="a1690-102">Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt;</span></span>
<span data-ttu-id="a1690-103">Возникла проблема при создании файла.</span><span class="sxs-lookup"><span data-stu-id="a1690-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="a1690-104">Не удается открыть выходной файл для записи.</span><span class="sxs-lookup"><span data-stu-id="a1690-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="a1690-105">Файл (или содержащая его папка) может быть открыт другим процессом для монопольного использования либо может иметь установленный атрибут "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="a1690-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="a1690-106">Распространенные ситуации, в которых файл открыт для монопольного доступа.</span><span class="sxs-lookup"><span data-stu-id="a1690-106">Common situations where a file is opened exclusively are:</span></span>  
  
-   <span data-ttu-id="a1690-107">Приложение уже запущено и использует свои файлы.</span><span class="sxs-lookup"><span data-stu-id="a1690-107">The application is already running and using its files.</span></span> <span data-ttu-id="a1690-108">Чтобы решить эту проблему, убедитесь, что приложение не запущено.</span><span class="sxs-lookup"><span data-stu-id="a1690-108">To solve this problem, make sure that the application is not running.</span></span>  
  
-   <span data-ttu-id="a1690-109">Этот файл открыло другое приложение.</span><span class="sxs-lookup"><span data-stu-id="a1690-109">Another application has opened the file.</span></span> <span data-ttu-id="a1690-110">Чтобы решить эту проблему, убедитесь, что другое приложение не осуществляет доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="a1690-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="a1690-111">Не всегда очевидно, какое именно приложение осуществляет доступ к файлам, в этом случае самым простым способом завершения приложения может оказаться перезапуск компьютера.</span><span class="sxs-lookup"><span data-stu-id="a1690-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="a1690-112">Если хотя бы один из выходных файлов проекта доступен только для чтения, возникает это исключение.</span><span class="sxs-lookup"><span data-stu-id="a1690-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="a1690-113">**Идентификатор ошибки:** BC31019</span><span class="sxs-lookup"><span data-stu-id="a1690-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a1690-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a1690-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="a1690-115">Скомпилируйте программу еще раз, чтобы узнать, повторится ли ошибка.</span><span class="sxs-lookup"><span data-stu-id="a1690-115">Compile the program again to see if the error recurs.</span></span>  
  
2.  <span data-ttu-id="a1690-116">Если ошибка возникает снова, сохраните работу и перезапустите [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1690-116">If the error continues, save your work and restart [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
3.  <span data-ttu-id="a1690-117">Если ошибка возникает снова, перезапустите компьютер.</span><span class="sxs-lookup"><span data-stu-id="a1690-117">If the error continues, restart the computer.</span></span>  
  
4.  <span data-ttu-id="a1690-118">Если ошибка повторится, переустановите Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a1690-118">If the error recurs, reinstall Visual Basic.</span></span>  
  
5.  <span data-ttu-id="a1690-119">Если после переустановки ошибка не устранена, уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a1690-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="a1690-120">Проверка атрибутов файла в проводнике</span><span class="sxs-lookup"><span data-stu-id="a1690-120">To check file attributes in File Explorer</span></span>  
  
1.  <span data-ttu-id="a1690-121">Откройте нужную папку.</span><span class="sxs-lookup"><span data-stu-id="a1690-121">Open the folder you are interested in.</span></span>  
  
2.  <span data-ttu-id="a1690-122">Нажмите кнопку **представления** значок и кнопку **сведения**.</span><span class="sxs-lookup"><span data-stu-id="a1690-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3.  <span data-ttu-id="a1690-123">Щелкните правой кнопкой мыши заголовок столбца и выберите **атрибуты** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="a1690-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="a1690-124">Изменение атрибутов файла или папки</span><span class="sxs-lookup"><span data-stu-id="a1690-124">To change the attributes of a file or folder</span></span>  
  
1.  <span data-ttu-id="a1690-125">В **проводнике**, щелкните правой кнопкой мыши файл или папку и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="a1690-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="a1690-126">В **атрибуты** раздел **Общие** снимите **только для чтения** поле.</span><span class="sxs-lookup"><span data-stu-id="a1690-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3.  <span data-ttu-id="a1690-127">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="a1690-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1690-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a1690-128">See Also</span></span>  
 [<span data-ttu-id="a1690-129">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="a1690-129">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
