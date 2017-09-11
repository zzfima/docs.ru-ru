---
title: "/ bugreport | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
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
ms.openlocfilehash: b959ef7958cffbbb31f3907eaf8749ca93ac538d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="bugreport"></a><span data-ttu-id="cf45b-102">/bugreport</span><span class="sxs-lookup"><span data-stu-id="cf45b-102">/bugreport</span></span>
<span data-ttu-id="cf45b-103">Создает файл, который можно использовать, если файл отчета об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cf45b-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf45b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf45b-104">Syntax</span></span>  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf45b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cf45b-105">Arguments</span></span>  
  
|<span data-ttu-id="cf45b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="cf45b-106">Term</span></span>|<span data-ttu-id="cf45b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="cf45b-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="cf45b-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="cf45b-108">Required.</span></span> <span data-ttu-id="cf45b-109">Имя файла, который будет содержать отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="cf45b-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="cf45b-110">Заключите имя файла в кавычки (» «), если имя содержит пробелы.</span><span class="sxs-lookup"><span data-stu-id="cf45b-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf45b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf45b-111">Remarks</span></span>  
 <span data-ttu-id="cf45b-112">Добавляется следующее `file`:</span><span class="sxs-lookup"><span data-stu-id="cf45b-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="cf45b-113">Копия всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="cf45b-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="cf45b-114">Список использованных при компиляции параметров компилятора.</span><span class="sxs-lookup"><span data-stu-id="cf45b-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="cf45b-115">Сведения о версии о компилятора, среды CLR и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="cf45b-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="cf45b-116">Выходные данные компилятора в, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="cf45b-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="cf45b-117">Описание проблемы, для которого будет предложено.</span><span class="sxs-lookup"><span data-stu-id="cf45b-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="cf45b-118">Описание предполагаемого способа разрешения проблемы должна быть устранена, для которого будет предложено.</span><span class="sxs-lookup"><span data-stu-id="cf45b-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="cf45b-119">Поскольку копию всех файлов исходного кода в `file`, может потребоваться воспроизвести предполагаемую ошибку в максимально короткой программе.</span><span class="sxs-lookup"><span data-stu-id="cf45b-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf45b-120">`/bugreport` Параметр создает файл, который содержит конфиденциальные сведения.</span><span class="sxs-lookup"><span data-stu-id="cf45b-120">The `/bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="cf45b-121">Это включает в себя текущее время, версия компилятора [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] версии, версия операционной системы, имя пользователя, аргументы командной строки, с помощью которых компилятор был запущен, весь исходный код и двоичная форма какой-либо связанной сборки.</span><span class="sxs-lookup"><span data-stu-id="cf45b-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="cf45b-122">Этот параметр может осуществляться с помощью параметров командной строки в файле Web.config для компиляции серверных [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] приложения.</span><span class="sxs-lookup"><span data-stu-id="cf45b-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] application.</span></span> <span data-ttu-id="cf45b-123">Чтобы избежать этого, измените файл Machine.config следует запретить пользователям компиляцию на сервере.</span><span class="sxs-lookup"><span data-stu-id="cf45b-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="cf45b-124">Если этот параметр используется с `/errorreport:prompt`, `/errorreport:queue`, или `/errorreport:send`, и в приложении происходит внутренняя ошибка компилятора, сведения в `file` отправляется корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cf45b-124">If this option is used with `/errorreport:prompt`, `/errorreport:queue`, or `/errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="cf45b-125">Эти сведения помогут инженерам Майкрософт определить причину ошибки и помогут улучшить следующий выпуск [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf45b-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="cf45b-126">По умолчанию никакая информация отправляется в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="cf45b-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="cf45b-127">Тем не менее, при компиляции приложения с помощью `/errorreport:queue`, который включен по умолчанию, приложение собирает отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="cf45b-127">However, when you compile an application by using `/errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="cf45b-128">Затем при входе в систему администратора системы отчетов об ошибках Отображает всплывающее окно, которое позволяет администратору переслать в корпорацию Майкрософт отчеты о любых ошибках, произошедших с момента входа в систему.</span><span class="sxs-lookup"><span data-stu-id="cf45b-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf45b-129">`/bugreport` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="cf45b-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf45b-130">Пример</span><span class="sxs-lookup"><span data-stu-id="cf45b-130">Example</span></span>  
 <span data-ttu-id="cf45b-131">В следующем примере компилируется `T2.vb` и помещает все сведения отчетность об ошибках в файле `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="cf45b-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf45b-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cf45b-132">See Also</span></span>  
 <span data-ttu-id="cf45b-133">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf45b-133">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="cf45b-134"> [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="cf45b-134"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="cf45b-135"> [/ ERRORREPORT](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span><span class="sxs-lookup"><span data-stu-id="cf45b-135"> [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md) </span></span>  
<span data-ttu-id="cf45b-136"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="cf45b-136"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="cf45b-137"> [Элемент trustLevel для securityPolicy (схема параметров ASP.NET)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span><span class="sxs-lookup"><span data-stu-id="cf45b-137"> [trustLevel Element for securityPolicy (ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)</span></span>
