---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: c8e193a8cb4d4dbc7515c32139bad9dce8b48ed7
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005615"
---
# <a name="-errorreport"></a><span data-ttu-id="b97df-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="b97df-102">-errorreport</span></span>

<span data-ttu-id="b97df-103">Указывает, каким образом компилятор Visual Basic должен сообщать о внутренних ошибках компилятора.</span><span class="sxs-lookup"><span data-stu-id="b97df-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="b97df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b97df-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="b97df-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="b97df-105">Remarks</span></span>

<span data-ttu-id="b97df-106">Этот параметр обеспечивает удобный способ сообщения Visual Basic внутренней ошибки компилятора (ICE) группе Visual Basic корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b97df-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="b97df-107">По умолчанию компилятор не отправляет сведения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b97df-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="b97df-108">Однако если возникает внутренняя ошибка компилятора, этот параметр позволяет сообщить об ошибке в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b97df-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="b97df-109">Эта информация поможет инженерам Майкрософт определить причину и поможет улучшить следующий выпуск Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b97df-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="b97df-110">Возможность отправки отчетов пользователем зависит от разрешений политики компьютера и пользователя.</span><span class="sxs-lookup"><span data-stu-id="b97df-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="b97df-111">В следующей таблице приводится сводка по результату использования параметра `-errorreport`.</span><span class="sxs-lookup"><span data-stu-id="b97df-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="b97df-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="b97df-112">Option</span></span>|<span data-ttu-id="b97df-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="b97df-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="b97df-114">При возникновении внутренней ошибки компилятора появляется диалоговое окно, в котором можно просмотреть точные данные, собранные компилятором.</span><span class="sxs-lookup"><span data-stu-id="b97df-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="b97df-115">Вы можете определить, есть ли в отчете об ошибках конфиденциальные сведения, и принять решение о том, отправляются они в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b97df-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="b97df-116">Если вы решили отправить его, а параметры политики компьютера и пользователя разрешают, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b97df-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="b97df-117">Отчет об ошибке помещается в очередь.</span><span class="sxs-lookup"><span data-stu-id="b97df-117">Queues the error report.</span></span> <span data-ttu-id="b97df-118">При входе с правами администратора можно сообщить о любых сбоях с момента последнего входа в систему (вам не будет предложено отправить отчеты об ошибках более одного раза в три дня).</span><span class="sxs-lookup"><span data-stu-id="b97df-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="b97df-119">Это поведение по умолчанию, если параметр `-errorreport` не указан.</span><span class="sxs-lookup"><span data-stu-id="b97df-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="b97df-120">Если возникла внутренняя ошибка компилятора, и параметры политики компьютера и пользователя разрешают эту ошибку, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b97df-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="b97df-121">Параметр `-errorreport:send` пытается автоматически отправить сведения об ошибке в корпорацию Майкрософт, если отчеты включены в параметрах системы [отчеты об ошибках Windows](/windows/desktop/wer/windows-error-reporting) .</span><span class="sxs-lookup"><span data-stu-id="b97df-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="b97df-122">Если возникла внутренняя ошибка компилятора, она не будет собрана или отправлена в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b97df-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="b97df-123">Компилятор отправляет данные, включающие стек, в момент возникновения ошибки, который обычно включает в себя некоторый исходный код.</span><span class="sxs-lookup"><span data-stu-id="b97df-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="b97df-124">Если `-errorreport` используется с параметром [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) , то отправляется весь исходный файл.</span><span class="sxs-lookup"><span data-stu-id="b97df-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="b97df-125">Этот вариант лучше всего использовать с параметром [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) , так как он позволяет специалистам Майкрософт более легко воспроизвести ошибку.</span><span class="sxs-lookup"><span data-stu-id="b97df-125">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="b97df-126">Параметр `-errorreport` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="b97df-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="b97df-127">Пример</span><span class="sxs-lookup"><span data-stu-id="b97df-127">Example</span></span>

<span data-ttu-id="b97df-128">Следующий код пытается скомпилировать `T2.vb`, и если компилятор обнаруживает внутреннюю ошибку компилятора, он предлагает отправить отчет об ошибке в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b97df-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="b97df-129">См. также</span><span class="sxs-lookup"><span data-stu-id="b97df-129">See also</span></span>

- [<span data-ttu-id="b97df-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="b97df-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b97df-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="b97df-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="b97df-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="b97df-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
