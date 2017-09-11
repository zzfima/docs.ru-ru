---
title: "-errorreport (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /errorreport
dev_langs:
- CSharp
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
caps.latest.revision: 35
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d32ec08da36509527b153166ae15019f129aad71
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="errorreport-c-compiler-options"></a><span data-ttu-id="88525-102">/errorreport (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="88525-102">/errorreport (C# Compiler Options)</span></span>
<span data-ttu-id="88525-103">Этот параметр предоставляет удобный способ для сообщения о внутренней ошибке компилятора C# в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88525-103">This option provides a convenient way to report a C# internal compiler error to Microsoft.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88525-104">В Windows Vista и Windows Server 2008 параметры отчетов об ошибках, установленные в среде Visual Studio, не переопределяют параметры отчетов об ошибках Windows.</span><span class="sxs-lookup"><span data-stu-id="88525-104">On Windows Vista and Windows Server 2008, the error reporting settings that you make for Visual Studio do not override the settings made through Windows Error Reporting (WER).</span></span> <span data-ttu-id="88525-105">Параметры отчетов об ошибках Windows всегда имеют приоритет над параметрами отчетов об ошибках Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="88525-105">WER settings always take precedence over Visual Studio error reporting settings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88525-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88525-106">Syntax</span></span>  
  
```console  
/errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a><span data-ttu-id="88525-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="88525-107">Arguments</span></span>  
 <span data-ttu-id="88525-108">**none**</span><span class="sxs-lookup"><span data-stu-id="88525-108">**none**</span></span>  
 <span data-ttu-id="88525-109">Не будет выполняться сбор отчетов о внутренних ошибках компилятора и их отправка в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88525-109">Reports about internal compiler errors will not be collected or sent to Microsoft.</span></span>  
  
 <span data-ttu-id="88525-110">**prompt**</span><span class="sxs-lookup"><span data-stu-id="88525-110">**prompt**</span></span>  
 <span data-ttu-id="88525-111">Запрашивает отправку отчета при получении внутренней ошибки компилятора.</span><span class="sxs-lookup"><span data-stu-id="88525-111">Prompts you to send a report when you receive an internal compiler error.</span></span> <span data-ttu-id="88525-112">**prompt** является параметром по умолчанию при компиляции приложения в среде разработки.</span><span class="sxs-lookup"><span data-stu-id="88525-112">**prompt** is the default when you compile an application in the development environment.</span></span>  
  
 <span data-ttu-id="88525-113">**queue**</span><span class="sxs-lookup"><span data-stu-id="88525-113">**queue**</span></span>  
 <span data-ttu-id="88525-114">Отчет об ошибке помещается в очередь.</span><span class="sxs-lookup"><span data-stu-id="88525-114">Queues the error report.</span></span> <span data-ttu-id="88525-115">При входе в систему с правами администратора можно сообщить о всех сбоях, произошедших со времени последнего входа в систему.</span><span class="sxs-lookup"><span data-stu-id="88525-115">When you log on with administrative credentials, you can report any failures since the last time that you were logged on.</span></span> <span data-ttu-id="88525-116">Предложение отправить отчеты об ошибках выводится не чаще одного раза в три дня.</span><span class="sxs-lookup"><span data-stu-id="88525-116">You will not be prompted to send reports for failures more than once every three days.</span></span> <span data-ttu-id="88525-117">**queue** является параметром по умолчанию при компиляции приложения из командной строки.</span><span class="sxs-lookup"><span data-stu-id="88525-117">**queue** is the default when you compile an application at the command line.</span></span>  
  
 <span data-ttu-id="88525-118">**send**</span><span class="sxs-lookup"><span data-stu-id="88525-118">**send**</span></span>  
 <span data-ttu-id="88525-119">Отчеты о внутренних ошибках компилятора автоматически отправляются в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88525-119">Automatically sends reports of internal compiler errors to Microsoft.</span></span> <span data-ttu-id="88525-120">Чтобы включить этот параметр, необходимо сначала согласиться с политикой сбора данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88525-120">To enable this option, you must first agree to the Microsoft data collection policy.</span></span> <span data-ttu-id="88525-121">При первом указании параметра **/errorreport:send** на компьютере отобразится сообщение компилятора с ссылкой на веб-сайт, на котором содержится политика сбора данных Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88525-121">The first time that you specify **/errorreport:send** on a computer, a compiler message will refer you to a Web site that contains the Microsoft data collection policy.</span></span>  
  
 <span data-ttu-id="88525-122">Этот параметр зависит от параметров реестра.</span><span class="sxs-lookup"><span data-stu-id="88525-122">This option depends on registry settings.</span></span> <span data-ttu-id="88525-123">Сведения о задании соответствующих значений в реестре см. на странице [Включение автоматического формирования отчетов в средствах командной строки Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695) на веб-сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="88525-123">For information about how to set the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695) on the MSDN Web site.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88525-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="88525-124">Remarks</span></span>  
 <span data-ttu-id="88525-125">Внутренние ошибки компилятора происходят, когда компилятору не удается обработать файл исходного кода.</span><span class="sxs-lookup"><span data-stu-id="88525-125">An internal compiler error (ICE) results when the compiler cannot process a source code file.</span></span> <span data-ttu-id="88525-126">При возникновении внутренней ошибки компилятор не создает выходной файл и не предоставляет никакой полезной диагностической информации для исправления кода.</span><span class="sxs-lookup"><span data-stu-id="88525-126">When an ICE occurs, the compiler does not produce an output file or any useful diagnostic that you can use to fix your code.</span></span>  
  
 <span data-ttu-id="88525-127">В предыдущих выпусках при возникновении внутренней ошибки компилятора отображалось окно с предложением сообщить о проблеме в службу технической поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="88525-127">In previous releases, when you received an ICE, you were encouraged to contact Microsoft Product Support Services to report the problem.</span></span> <span data-ttu-id="88525-128">С помощью параметра **/errorreport** можно предоставить сведения о внутренней ошибке компилятора группе разработчиков Visual C#.</span><span class="sxs-lookup"><span data-stu-id="88525-128">By using **/errorreport**, you can provide ICE information to the Visual C# team.</span></span> <span data-ttu-id="88525-129">Эти отчеты об ошибках могут помочь улучшить будущие версии компилятора.</span><span class="sxs-lookup"><span data-stu-id="88525-129">Your error reports can help improve future compiler releases.</span></span>  
  
 <span data-ttu-id="88525-130">Возможность отправлять отчеты пользователем зависит от политики разрешений компьютера и пользователя.</span><span class="sxs-lookup"><span data-stu-id="88525-130">A user's ability to send reports depends on computer and user policy permissions.</span></span>  
  
 <span data-ttu-id="88525-131">Дополнительные сведения об отладчике ошибок см. в разделе [Описание средства Доктор Ватсон для Windows (Drwtsn32.exe)](http://go.microsoft.com/fwlink/?LinkId=147286).</span><span class="sxs-lookup"><span data-stu-id="88525-131">For more information about error debugger, see [Description of the Dr. Watson for Windows (Drwtsn32.exe) Tool](http://go.microsoft.com/fwlink/?LinkId=147286).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="88525-132">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="88525-132">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="88525-133">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="88525-133">Open the project's **Properties** page.</span></span> <span data-ttu-id="88525-134">Дополнительные сведения см. в разделе [Страница "Сборка" в конструкторе проектов (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="88525-134">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="88525-135">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="88525-135">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="88525-136">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="88525-136">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="88525-137">Измените свойство **Отчеты о внутренних ошибках компилятора**.</span><span class="sxs-lookup"><span data-stu-id="88525-137">Modify the **Internal Compiler Error Reporting** property.</span></span>  
  
 <span data-ttu-id="88525-138">Дополнительные сведения об установке этого параметра компилятора программным путем см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span><span class="sxs-lookup"><span data-stu-id="88525-138">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88525-139">См. также</span><span class="sxs-lookup"><span data-stu-id="88525-139">See Also</span></span>  
 [<span data-ttu-id="88525-140">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="88525-140">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)

