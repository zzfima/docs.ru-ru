---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 75c3e5842447a8f0812d5a90d7157f7a6a496936
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962449"
---
# <a name="-bugreport"></a><span data-ttu-id="121cd-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="121cd-102">-bugreport</span></span>
<span data-ttu-id="121cd-103">Создает файл, который можно использовать при создании отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="121cd-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="121cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="121cd-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="121cd-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="121cd-105">Arguments</span></span>  
  
|<span data-ttu-id="121cd-106">Термин</span><span class="sxs-lookup"><span data-stu-id="121cd-106">Term</span></span>|<span data-ttu-id="121cd-107">Определение</span><span class="sxs-lookup"><span data-stu-id="121cd-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="121cd-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="121cd-108">Required.</span></span> <span data-ttu-id="121cd-109">Имя файла, который будет содержать отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="121cd-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="121cd-110">Заключите имя файла в кавычки (""), если оно содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="121cd-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="121cd-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="121cd-111">Remarks</span></span>  
 <span data-ttu-id="121cd-112">Следующие сведения добавляются в `file`:</span><span class="sxs-lookup"><span data-stu-id="121cd-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="121cd-113">Копия всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="121cd-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="121cd-114">Список параметров компилятора, используемых при компиляции.</span><span class="sxs-lookup"><span data-stu-id="121cd-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="121cd-115">Сведения о версии компилятора, среды CLR и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="121cd-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="121cd-116">Выходные данные компилятора (если есть).</span><span class="sxs-lookup"><span data-stu-id="121cd-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="121cd-117">Описание проблемы, для которой выводится запрос.</span><span class="sxs-lookup"><span data-stu-id="121cd-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="121cd-118">Описание того, как вы считаете, что проблема должна быть исправлена, для которой выводится запрос.</span><span class="sxs-lookup"><span data-stu-id="121cd-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="121cd-119">Так как копия всех файлов исходного кода включена в `file`, может потребоваться воспроизвести код ошибки в самой короткой программе.</span><span class="sxs-lookup"><span data-stu-id="121cd-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="121cd-120">`-bugreport` Параметр создает файл, содержащий потенциально конфиденциальную информацию.</span><span class="sxs-lookup"><span data-stu-id="121cd-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="121cd-121">К ним относятся текущее время, версия компилятора, .NET Framework версия, версия ОС, имя пользователя, аргументы командной строки, с которыми был запущен Компилятор, весь исходный код и двоичная форма любой сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="121cd-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="121cd-122">Доступ к этому параметру можно получить, указав параметры командной строки в файле Web. config для компиляции приложения ASP.NET на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="121cd-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="121cd-123">Чтобы избежать этого, измените файл Machine. config, чтобы запретить пользователям компиляцию на сервере.</span><span class="sxs-lookup"><span data-stu-id="121cd-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="121cd-124">Если этот параметр используется `-errorreport:prompt`с, `-errorreport:queue`или `-errorreport:send`, а приложение обнаруживает внутреннюю ошибку компилятора, информация в `file` отправляется в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="121cd-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="121cd-125">Эта информация поможет инженерам Майкрософт определить причину ошибки и улучшить следующий выпуск Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="121cd-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="121cd-126">По умолчанию никакие сведения не отправляются в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="121cd-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="121cd-127">Однако при компиляции приложения с помощью `-errorreport:queue`, которое включено по умолчанию, приложение собирает свои отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="121cd-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="121cd-128">Затем, когда администратор компьютера входит в систему, система отчетов об ошибках отображает всплывающее окно, которое позволяет администратору пересылать в корпорацию Майкрософт любые отчеты об ошибках, произошедшие с момента входа в систему.</span><span class="sxs-lookup"><span data-stu-id="121cd-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="121cd-129">Этот `/bugreport` параметр недоступен в среде разработки Visual Studio. он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="121cd-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="121cd-130">Пример</span><span class="sxs-lookup"><span data-stu-id="121cd-130">Example</span></span>  
 <span data-ttu-id="121cd-131">В следующем примере выполняется компиляция `T2.vb` и помещает в файл `Problem.txt`все сведения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="121cd-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="121cd-132">См. также</span><span class="sxs-lookup"><span data-stu-id="121cd-132">See also</span></span>

- [<span data-ttu-id="121cd-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="121cd-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="121cd-134">-Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="121cd-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="121cd-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="121cd-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="121cd-136">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="121cd-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="121cd-137">[Элемент trustLevel для параметра securityPolicy (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="121cd-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
