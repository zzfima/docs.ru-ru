---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 02d84bceb0242988c70889ddd5d3dc7530f6e808
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793549"
---
# <a name="-bugreport"></a><span data-ttu-id="330b0-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="330b0-102">-bugreport</span></span>

<span data-ttu-id="330b0-103">Создает файл, который можно использовать при создании отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="330b0-103">Creates a file that you can use when you file a bug report.</span></span>

## <a name="syntax"></a><span data-ttu-id="330b0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="330b0-104">Syntax</span></span>

```console
-bugreport:file
```

## <a name="arguments"></a><span data-ttu-id="330b0-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="330b0-105">Arguments</span></span>

|<span data-ttu-id="330b0-106">Термин</span><span class="sxs-lookup"><span data-stu-id="330b0-106">Term</span></span>|<span data-ttu-id="330b0-107">Определение</span><span class="sxs-lookup"><span data-stu-id="330b0-107">Definition</span></span>|
|---|---|
|`file`|<span data-ttu-id="330b0-108">Обязательное</span><span class="sxs-lookup"><span data-stu-id="330b0-108">Required.</span></span> <span data-ttu-id="330b0-109">Имя файла, который будет содержать отчет об ошибке.</span><span class="sxs-lookup"><span data-stu-id="330b0-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="330b0-110">Заключите имя файла в кавычки (""), если оно содержит пробел.</span><span class="sxs-lookup"><span data-stu-id="330b0-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|

## <a name="remarks"></a><span data-ttu-id="330b0-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="330b0-111">Remarks</span></span>

<span data-ttu-id="330b0-112">Следующие сведения добавляются в `file`:</span><span class="sxs-lookup"><span data-stu-id="330b0-112">The following information is added to `file`:</span></span>

- <span data-ttu-id="330b0-113">Копия всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="330b0-113">A copy of all source-code files in the compilation.</span></span>

- <span data-ttu-id="330b0-114">Список параметров компилятора, используемых при компиляции.</span><span class="sxs-lookup"><span data-stu-id="330b0-114">A list of the compiler options used in the compilation.</span></span>

- <span data-ttu-id="330b0-115">Сведения о версии компилятора, среды CLR и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="330b0-115">Version information about your compiler, common language runtime, and operating system.</span></span>

- <span data-ttu-id="330b0-116">Выходные данные компилятора (если есть).</span><span class="sxs-lookup"><span data-stu-id="330b0-116">Compiler output, if any.</span></span>

- <span data-ttu-id="330b0-117">Описание проблемы, для которой выводится запрос.</span><span class="sxs-lookup"><span data-stu-id="330b0-117">A description of the problem, for which you are prompted.</span></span>

- <span data-ttu-id="330b0-118">Описание того, как вы считаете, что проблема должна быть исправлена, для которой выводится запрос.</span><span class="sxs-lookup"><span data-stu-id="330b0-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>

<span data-ttu-id="330b0-119">Поскольку копия всех файлов исходного кода включается в `file`, может возникнуть необходимость воспроизвести код ошибки в самой короткой программе.</span><span class="sxs-lookup"><span data-stu-id="330b0-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="330b0-120">Параметр `-bugreport` создает файл, содержащий потенциально конфиденциальную информацию.</span><span class="sxs-lookup"><span data-stu-id="330b0-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="330b0-121">К ним относятся текущее время, версия компилятора, .NET Framework версия, версия ОС, имя пользователя, аргументы командной строки, с которыми был запущен Компилятор, весь исходный код и двоичная форма любой сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="330b0-121">This includes current time, compiler version, .NET Framework version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="330b0-122">Доступ к этому параметру можно получить, указав параметры командной строки в файле Web. config для компиляции приложения ASP.NET на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="330b0-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an ASP.NET application.</span></span> <span data-ttu-id="330b0-123">Чтобы избежать этого, измените файл Machine. config, чтобы запретить пользователям компиляцию на сервере.</span><span class="sxs-lookup"><span data-stu-id="330b0-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>

<span data-ttu-id="330b0-124">Если этот параметр используется с `-errorreport:prompt`, `-errorreport:queue`или `-errorreport:send`и приложение обнаруживает внутреннюю ошибку компилятора, информация в `file` отправляется в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="330b0-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="330b0-125">Эта информация поможет инженерам Майкрософт определить причину ошибки и улучшить следующий выпуск Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="330b0-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="330b0-126">По умолчанию никакие сведения не отправляются в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="330b0-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="330b0-127">Однако при компиляции приложения с помощью `-errorreport:queue`, которое включено по умолчанию, приложение собирает свои отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="330b0-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="330b0-128">Затем, когда администратор компьютера входит в систему, система отчетов об ошибках отображает всплывающее окно, которое позволяет администратору пересылать в корпорацию Майкрософт любые отчеты об ошибках, произошедшие с момента входа в систему.</span><span class="sxs-lookup"><span data-stu-id="330b0-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>

> [!NOTE]
> <span data-ttu-id="330b0-129">Параметр `-bugreport` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="330b0-129">The `-bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="330b0-130">Пример</span><span class="sxs-lookup"><span data-stu-id="330b0-130">Example</span></span>

<span data-ttu-id="330b0-131">Следующий пример компилирует *T2. vb* и помещает все сведения об ошибках в файл *проблема. txt*.</span><span class="sxs-lookup"><span data-stu-id="330b0-131">The following example compiles *T2.vb* and puts all bug-reporting information in the file *Problem.txt*.</span></span>

```console
vbc -bugreport:problem.txt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="330b0-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="330b0-132">See also</span></span>

- [<span data-ttu-id="330b0-133">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="330b0-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="330b0-134">-Debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="330b0-134">-debug (Visual Basic)</span></span>](debug.md)
- [<span data-ttu-id="330b0-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="330b0-135">-errorreport</span></span>](errorreport.md)
- [<span data-ttu-id="330b0-136">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="330b0-136">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- <span data-ttu-id="330b0-137">[Элемент trustLevel для параметра securityPolicy (схема параметров ASP.NET)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="330b0-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
