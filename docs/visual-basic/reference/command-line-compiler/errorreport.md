---
title: "/ ERRORREPORT | Документы Microsoft"
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
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c2f9a9daf6aed6348baeb2c4de2fe5caef70f52b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="errorreport"></a><span data-ttu-id="c2d7e-102">/errorreport</span><span class="sxs-lookup"><span data-stu-id="c2d7e-102">/errorreport</span></span>
<span data-ttu-id="c2d7e-103">Указывает, как компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] должен сообщать о внутренних ошибках.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-103">Specifies how the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d7e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2d7e-104">Syntax</span></span>  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="c2d7e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2d7e-105">Remarks</span></span>  
 <span data-ttu-id="c2d7e-106">Этот параметр предоставляет удобный способ отчета [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Внутренняя ошибка компилятора (ICE) для [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] корпорации Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-106">This option provides a convenient way to report a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] internal compiler error (ICE) to the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] team at Microsoft.</span></span> <span data-ttu-id="c2d7e-107">По умолчанию компилятор отправляет никакие сведения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="c2d7e-108">Однако при возникновении внутренней ошибки компилятора, этот параметр позволяет отчет об ошибке в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="c2d7e-109">Эти сведения помогут инженерам Майкрософт определить причину и помогут улучшить следующий выпуск [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2d7e-109">That information will help Microsoft engineers identify the cause and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="c2d7e-110">Возможность отправки отчетов зависит от разрешений политики компьютера и пользователя.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="c2d7e-111">В следующей таблице перечислены эффект `/errorreport` параметр.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-111">The following table summarizes the effect of the `/errorreport` option.</span></span>  
  
|<span data-ttu-id="c2d7e-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="c2d7e-112">Option</span></span>|<span data-ttu-id="c2d7e-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="c2d7e-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="c2d7e-114">При возникновении внутренней ошибки компилятора, диалоговое окно появится, можно просмотреть точные данные, собранные компилятором.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="c2d7e-115">Можно определить, если важную информацию в отчет об ошибке и принять решение о том, следует ли отправлять их в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="c2d7e-116">Если вы решили отправить его разрешена параметрами политики компьютера и пользователя, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="c2d7e-117">Очереди отчета об ошибках.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-117">Queues the error report.</span></span> <span data-ttu-id="c2d7e-118">При входе в систему с правами администратора может обо всех сбоях с момента последнего входа (вы не предлагается отправлять отчеты об ошибках, более одного раза в три дня).</span><span class="sxs-lookup"><span data-stu-id="c2d7e-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="c2d7e-119">Это поведение по умолчанию при `/errorreport` параметр не указан.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-119">This is the default behavior when the `/errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="c2d7e-120">Если происходит внутренняя ошибка компилятора, и разрешена параметрами политики компьютера и пользователя, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="c2d7e-121">Параметр `/errorReport:send` пытается автоматически отправлять информацию об ошибках в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-121">The option `/errorReport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="c2d7e-122">Этот параметр зависит от реестра.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-122">This option depends on the registry.</span></span> <span data-ttu-id="c2d7e-123">Дополнительные сведения о настройке соответствующих значений в реестре в разделе [как включить автоматическое создание отчетов об ошибках в средствах командной строки Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).</span><span class="sxs-lookup"><span data-stu-id="c2d7e-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="c2d7e-124">При возникновении внутренней ошибки компилятора, его не быть собираются и отправляются в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="c2d7e-125">Компилятор отправляет данные, включающие стека во время ошибки, которая обычно включает некоторые исходный код.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="c2d7e-126">Если `/errorreport` используется с [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) параметр, а затем отправляется весь исходный файл.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-126">If `/errorreport` is used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="c2d7e-127">Этот параметр лучше всего использовать с [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) вариант, поскольку он позволяет инженерам корпорации Майкрософт более легко воспроизвести ошибку.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2d7e-128">`/errorreport` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-128">The `/errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2d7e-129">Пример</span><span class="sxs-lookup"><span data-stu-id="c2d7e-129">Example</span></span>  
 <span data-ttu-id="c2d7e-130">Следующий код попытается скомпилировать `T2.vb`, и если компилятор обнаруживает Внутренняя ошибка компилятора, будет предложено отправить отчет об ошибках в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c2d7e-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c2d7e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d7e-131">See Also</span></span>  
 <span data-ttu-id="c2d7e-132">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2d7e-132">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="c2d7e-133"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="c2d7e-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="c2d7e-134"> [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)</span><span class="sxs-lookup"><span data-stu-id="c2d7e-134"> [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)</span></span>
