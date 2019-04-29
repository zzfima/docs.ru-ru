---
title: 'Не удается выполнить запись в файл результатов <filename>: <error>'
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: f29eb628c079f65a520cf5e1ccd8afed549f7cad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787417"
---
# <a name="unable-to-write-to-output-file-filename-error"></a><span data-ttu-id="80152-102">Не удалось выполнить запись в выходной файл "\<имя_файла >": \<ошибка ></span><span class="sxs-lookup"><span data-stu-id="80152-102">Unable to write to output file '\<filename>': \<error></span></span>
<span data-ttu-id="80152-103">Возникла проблема при создании файла.</span><span class="sxs-lookup"><span data-stu-id="80152-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="80152-104">Не удается открыть выходной файл для записи.</span><span class="sxs-lookup"><span data-stu-id="80152-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="80152-105">Файл (или содержащая его папка) может быть открыт другим процессом для монопольного использования либо может иметь установленный атрибут "только для чтения".</span><span class="sxs-lookup"><span data-stu-id="80152-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="80152-106">Распространенные ситуации, в которых файл открыт для монопольного доступа.</span><span class="sxs-lookup"><span data-stu-id="80152-106">Common situations where a file is opened exclusively are:</span></span>  
  
- <span data-ttu-id="80152-107">Приложение уже запущено и использует свои файлы.</span><span class="sxs-lookup"><span data-stu-id="80152-107">The application is already running and using its files.</span></span> <span data-ttu-id="80152-108">Чтобы решить эту проблему, убедитесь, что приложение не запущено.</span><span class="sxs-lookup"><span data-stu-id="80152-108">To solve this problem, make sure that the application is not running.</span></span>  
  
- <span data-ttu-id="80152-109">Этот файл открыло другое приложение.</span><span class="sxs-lookup"><span data-stu-id="80152-109">Another application has opened the file.</span></span> <span data-ttu-id="80152-110">Чтобы решить эту проблему, убедитесь, что другое приложение не осуществляет доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="80152-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="80152-111">Не всегда очевидно, какое именно приложение осуществляет доступ к файлам, в этом случае самым простым способом завершения приложения может оказаться перезапуск компьютера.</span><span class="sxs-lookup"><span data-stu-id="80152-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="80152-112">Если хотя бы один из выходных файлов проекта доступен только для чтения, возникает это исключение.</span><span class="sxs-lookup"><span data-stu-id="80152-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="80152-113">**Идентификатор ошибки:** BC31019</span><span class="sxs-lookup"><span data-stu-id="80152-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80152-114">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="80152-114">To correct this error</span></span>  
  
1. <span data-ttu-id="80152-115">Скомпилируйте программу еще раз, чтобы узнать, повторится ли ошибка.</span><span class="sxs-lookup"><span data-stu-id="80152-115">Compile the program again to see if the error recurs.</span></span>  
  
2. <span data-ttu-id="80152-116">Если ошибка продолжает появляться, сохраните работу и перезапустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="80152-116">If the error continues, save your work and restart Visual Studio.</span></span>  
  
3. <span data-ttu-id="80152-117">Если ошибка возникает снова, перезапустите компьютер.</span><span class="sxs-lookup"><span data-stu-id="80152-117">If the error continues, restart the computer.</span></span>  
  
4. <span data-ttu-id="80152-118">Если ошибка повторяется, переустановите Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="80152-118">If the error recurs, reinstall Visual Basic.</span></span>  
  
5. <span data-ttu-id="80152-119">Если после переустановки ошибка не устранена, уведомите службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="80152-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="80152-120">Проверка атрибутов файла в проводнике</span><span class="sxs-lookup"><span data-stu-id="80152-120">To check file attributes in File Explorer</span></span>  
  
1. <span data-ttu-id="80152-121">Откройте нужную папку.</span><span class="sxs-lookup"><span data-stu-id="80152-121">Open the folder you are interested in.</span></span>  
  
2. <span data-ttu-id="80152-122">Нажмите кнопку **представления** значок и выберите **сведения**.</span><span class="sxs-lookup"><span data-stu-id="80152-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3. <span data-ttu-id="80152-123">Щелкните правой кнопкой мыши заголовок столбца и выберите **атрибуты** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="80152-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="80152-124">Изменение атрибутов файла или папки</span><span class="sxs-lookup"><span data-stu-id="80152-124">To change the attributes of a file or folder</span></span>  
  
1. <span data-ttu-id="80152-125">В **проводнике**, щелкните правой кнопкой мыши файл или папку и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="80152-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2. <span data-ttu-id="80152-126">В **атрибуты** раздел **Общие** вкладке Очистить **только для чтения** поле.</span><span class="sxs-lookup"><span data-stu-id="80152-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3. <span data-ttu-id="80152-127">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="80152-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80152-128">См. также</span><span class="sxs-lookup"><span data-stu-id="80152-128">See also</span></span>

- [<span data-ttu-id="80152-129">Обращайтесь к нам</span><span class="sxs-lookup"><span data-stu-id="80152-129">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
