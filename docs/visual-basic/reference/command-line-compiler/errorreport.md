---
title: -errorreport
ms.date: 03/10/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8c6a81d3491f4876cfbca80aa8fda6640187176
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650937"
---
# <a name="-errorreport"></a><span data-ttu-id="33859-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="33859-102">-errorreport</span></span>
<span data-ttu-id="33859-103">Указывает, как компилятор Visual Basic должна сообщать о внутренних ошибках компилятора.</span><span class="sxs-lookup"><span data-stu-id="33859-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33859-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33859-104">Syntax</span></span>  
  
```  
-errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="33859-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="33859-105">Remarks</span></span>  
 <span data-ttu-id="33859-106">Этот параметр предоставляет удобный способ сообщить Visual Basic внутренней ошибке компилятора (ICE) к группе разработчиков Visual Basic корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33859-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="33859-107">По умолчанию компилятор не отправляет сведения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33859-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="33859-108">Однако при возникновении внутренней ошибки компилятора, этот параметр позволяет сообщить об ошибке в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33859-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="33859-109">Эти сведения помогут определить причину инженерам Майкрософт и помогут улучшить следующий выпуск Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="33859-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>  
  
 <span data-ttu-id="33859-110">Возможность отправки отчетов зависит от разрешений политики компьютера и пользователя.</span><span class="sxs-lookup"><span data-stu-id="33859-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="33859-111">В следующей таблице перечислены действия `-errorreport` параметр.</span><span class="sxs-lookup"><span data-stu-id="33859-111">The following table summarizes the effect of the `-errorreport` option.</span></span>  
  
|<span data-ttu-id="33859-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="33859-112">Option</span></span>|<span data-ttu-id="33859-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="33859-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="33859-114">При возникновении внутренней ошибки компилятора, диалоговое окно появится, чтобы можно было просматривать точные данные, собранные компилятором.</span><span class="sxs-lookup"><span data-stu-id="33859-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="33859-115">Можно определить, если любой конфиденциальной информации в отчет об ошибке и принять решение о том, будут ли отправляться в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33859-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="33859-116">Если вы решили отправить его, и разрешена параметрами политики компьютера и пользователя, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33859-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="33859-117">Отчет об ошибке помещается в очередь.</span><span class="sxs-lookup"><span data-stu-id="33859-117">Queues the error report.</span></span> <span data-ttu-id="33859-118">При входе в систему с правами администратора может обо всех сбоях с момента последнего входа (не будет предлагаться отправлять отчеты об ошибках в более чем один раз каждые три дня).</span><span class="sxs-lookup"><span data-stu-id="33859-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="33859-119">Это поведение по умолчанию при `-errorreport` параметр не указан.</span><span class="sxs-lookup"><span data-stu-id="33859-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="33859-120">Если происходит внутренняя ошибка компилятора разрешена параметрами политики компьютера и пользователя, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33859-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="33859-121">Параметр `-errorreport:send` пытается автоматически отправлять в корпорацию Майкрософт сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="33859-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="33859-122">Этот параметр зависит от реестра.</span><span class="sxs-lookup"><span data-stu-id="33859-122">This option depends on the registry.</span></span> <span data-ttu-id="33859-123">Дополнительные сведения о настройке соответствующие значения в реестре см. в разделе [как включить автоматическое создание отчетов об ошибках в средства командной строки Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695).</span><span class="sxs-lookup"><span data-stu-id="33859-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="33859-124">При возникновении внутренней ошибки компилятора, он не быть собираются и отправляются в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33859-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="33859-125">Компилятор отправляет данные, включая стека во время ошибки, которая обычно также часть исходного кода.</span><span class="sxs-lookup"><span data-stu-id="33859-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="33859-126">Если `-errorreport` используется с [- bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) параметр отправляться всего исходного файла.</span><span class="sxs-lookup"><span data-stu-id="33859-126">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="33859-127">Этот вариант лучше всего использовать с [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) вариант, так как она позволяет инженерам корпорации Майкрософт более легко воспроизвести ошибку.</span><span class="sxs-lookup"><span data-stu-id="33859-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33859-128">`-errorreport` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="33859-128">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33859-129">Пример</span><span class="sxs-lookup"><span data-stu-id="33859-129">Example</span></span>  
 <span data-ttu-id="33859-130">Следующий код попытается скомпилировать `T2.vb`, и если компилятор обнаруживает Внутренняя ошибка компилятора, предлагается отправить отчет об ошибке в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="33859-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc -errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="33859-131">См. также</span><span class="sxs-lookup"><span data-stu-id="33859-131">See Also</span></span>  
 [<span data-ttu-id="33859-132">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="33859-132">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="33859-133">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="33859-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="33859-134">-bugreport</span><span class="sxs-lookup"><span data-stu-id="33859-134">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
