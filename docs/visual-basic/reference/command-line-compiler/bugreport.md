---
title: /bugreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c36cdcaf8d2db0b08e262d6ba8ff2bb774fb233
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="bugreport"></a><span data-ttu-id="ff6ca-102">/bugreport</span><span class="sxs-lookup"><span data-stu-id="ff6ca-102">/bugreport</span></span>
<span data-ttu-id="ff6ca-103">Создает файл, который можно использовать, если файл отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff6ca-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff6ca-104">Syntax</span></span>  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="ff6ca-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="ff6ca-105">Arguments</span></span>  
  
|<span data-ttu-id="ff6ca-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ff6ca-106">Term</span></span>|<span data-ttu-id="ff6ca-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ff6ca-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="ff6ca-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-108">Required.</span></span> <span data-ttu-id="ff6ca-109">Имя файла, который будет содержать отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="ff6ca-110">Заключите имя файла в кавычки (» «), если имя содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff6ca-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff6ca-111">Remarks</span></span>  
 <span data-ttu-id="ff6ca-112">Следующие сведения добавляется `file`:</span><span class="sxs-lookup"><span data-stu-id="ff6ca-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="ff6ca-113">Копия всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="ff6ca-114">Список параметров компилятора, используемые при компиляции.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="ff6ca-115">Сведения о версии о компилятора, среды CLR и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="ff6ca-116">Выходные данные компилятора (если есть).</span><span class="sxs-lookup"><span data-stu-id="ff6ca-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="ff6ca-117">Описание проблемы, для которого будет предложено.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="ff6ca-118">Описание предполагаемого способа разрешения проблемы должны быть исправлены, для которого будет предложено.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="ff6ca-119">Поскольку копия всех файлов исходного кода в `file`, может потребоваться воспроизвести предполагаемую ошибку в максимально короткой программе.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff6ca-120">`/bugreport` Параметр создает файл, который содержит конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-120">The `/bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="ff6ca-121">Это включает в себя текущее время, версия компилятора [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] версии, версия операционной системы, имя пользователя, аргументы командной строки, с помощью которых компилятор был запущен, весь код исходной и двоичной форме какой-либо связанной сборки.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="ff6ca-122">Этот параметр может осуществляться с помощью параметров командной строки в файле Web.config для серверных компиляция [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="ff6ca-123">Чтобы избежать этого, измените файл Machine.config следует запретить пользователям компиляцию на сервере.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="ff6ca-124">Если этот параметр используется с `/errorreport:prompt`, `/errorreport:queue`, или `/errorreport:send`, и в приложении происходит внутренняя ошибка компилятора, сведения в `file` отправляется в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-124">If this option is used with `/errorreport:prompt`, `/errorreport:queue`, or `/errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="ff6ca-125">Эти сведения помогут инженерам Майкрософт определить причину ошибки и помогут улучшить следующий выпуск [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff6ca-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="ff6ca-126">По умолчанию никакая информация отправляется в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="ff6ca-127">Тем не менее, при компиляции приложения с помощью `/errorreport:queue`, который включен по умолчанию, приложение собирает отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-127">However, when you compile an application by using `/errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="ff6ca-128">Затем при входе администратора система отчета об ошибках Отображает всплывающее окно, которое позволяет администратору переслать в корпорацию Майкрософт отчеты о любых ошибках, произошедших с момента входа в систему.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff6ca-129">`/bugreport` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff6ca-130">Пример</span><span class="sxs-lookup"><span data-stu-id="ff6ca-130">Example</span></span>  
 <span data-ttu-id="ff6ca-131">В следующем примере компилируется `T2.vb` и помещает все сведения отчетность об ошибках в файле `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="ff6ca-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="ff6ca-132">См. также</span><span class="sxs-lookup"><span data-stu-id="ff6ca-132">See Also</span></span>  
 [<span data-ttu-id="ff6ca-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="ff6ca-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="ff6ca-134">/ Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff6ca-134">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="ff6ca-135">/errorreport</span><span class="sxs-lookup"><span data-stu-id="ff6ca-135">/errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [<span data-ttu-id="ff6ca-136">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="ff6ca-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="ff6ca-137">trustLevel элемент для securityPolicy (схема параметров ASP.NET)</span><span class="sxs-lookup"><span data-stu-id="ff6ca-137">trustLevel Element for securityPolicy (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/729ab04c-03da-4ee5-86b1-be9d08a09369)
