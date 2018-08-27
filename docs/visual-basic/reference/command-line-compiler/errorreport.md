---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d093b8ce4413a375e79eec239be37e83ac674d05
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929947"
---
# <a name="-errorreport"></a><span data-ttu-id="2048a-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="2048a-102">-errorreport</span></span>

<span data-ttu-id="2048a-103">Указывает, как компилятор Visual Basic должна сообщать о внутренних ошибках компилятора.</span><span class="sxs-lookup"><span data-stu-id="2048a-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="2048a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2048a-104">Syntax</span></span>

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="2048a-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="2048a-105">Remarks</span></span>

<span data-ttu-id="2048a-106">Этот параметр предоставляет удобный способ сообщить Visual Basic внутренней ошибке компилятора (ICE) для Visual Basic корпорации Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2048a-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="2048a-107">По умолчанию, компилятор не отправляет сведения в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2048a-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="2048a-108">Тем не менее если вы столкнулись с внутренней ошибки компилятора, этот параметр позволяет сообщить об ошибке в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2048a-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="2048a-109">Эти сведения помогут определить причину инженерами корпорации Майкрософт и помогут улучшить следующую версию Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2048a-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="2048a-110">Возможность отправлять отчеты пользователем зависит от политики разрешений компьютера и пользователя.</span><span class="sxs-lookup"><span data-stu-id="2048a-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="2048a-111">В следующей таблице перечислены последствия `-errorreport` параметр.</span><span class="sxs-lookup"><span data-stu-id="2048a-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="2048a-112">Параметр</span><span class="sxs-lookup"><span data-stu-id="2048a-112">Option</span></span>|<span data-ttu-id="2048a-113">Поведение</span><span class="sxs-lookup"><span data-stu-id="2048a-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="2048a-114">При возникновении внутренней ошибки компилятора, диалоговое окно появится, можно просмотреть точные данные, собранные компилятором.</span><span class="sxs-lookup"><span data-stu-id="2048a-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="2048a-115">Можно определить, если имеется конфиденциальную информацию в отчет об ошибке и принять решение о том, следует ли отправлять их в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2048a-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="2048a-116">Если вы решили отправить его, а разрешена параметрами политики компьютера и пользователя, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2048a-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="2048a-117">Отчет об ошибке помещается в очередь.</span><span class="sxs-lookup"><span data-stu-id="2048a-117">Queues the error report.</span></span> <span data-ttu-id="2048a-118">При входе в систему как администратор, вы можете сообщить сбоев с момента последнего входа (вам будет не предложено отправить отчеты об ошибках более одного раза каждые три дня).</span><span class="sxs-lookup"><span data-stu-id="2048a-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="2048a-119">Это поведение по умолчанию при `-errorreport` параметр не указан.</span><span class="sxs-lookup"><span data-stu-id="2048a-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="2048a-120">Если происходит внутренняя ошибка компилятора разрешена параметрами политики компьютера и пользователя, компилятор отправляет данные в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2048a-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="2048a-121">Параметр `-errorreport:send` пытается автоматически отправлять сведения об ошибках в корпорацию Майкрософт, если отчеты включаются по [отчеты об ошибках Windows](/windows/desktop/wer/windows-error-reporting) параметры системы.</span><span class="sxs-lookup"><span data-stu-id="2048a-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="2048a-122">При возникновении внутренней ошибки компилятора, его не быть собранные или отправленные в Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2048a-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="2048a-123">Компилятор отправляет данные, которые содержат стека на момент возникновения ошибки, который обычно включает в себя некоторый исходный код.</span><span class="sxs-lookup"><span data-stu-id="2048a-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="2048a-124">Если `-errorreport` используется с [- bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) параметр, а затем отправляется всего исходного файла.</span><span class="sxs-lookup"><span data-stu-id="2048a-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="2048a-125">Этот параметр лучше всего использовать с [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) параметр, так как она позволяет инженерам корпорации Майкрософт более легко воспроизвести ошибку.</span><span class="sxs-lookup"><span data-stu-id="2048a-125">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="2048a-126">`-errorreport` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="2048a-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="2048a-127">Пример</span><span class="sxs-lookup"><span data-stu-id="2048a-127">Example</span></span>

<span data-ttu-id="2048a-128">Следующий код попытается скомпилировать `T2.vb`, и если компилятор обнаруживает внутренней ошибки компилятора, вам будет предложено отправить отчет об ошибках в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2048a-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="2048a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2048a-129">See also</span></span>

- [<span data-ttu-id="2048a-130">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="2048a-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="2048a-131">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="2048a-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="2048a-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="2048a-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
