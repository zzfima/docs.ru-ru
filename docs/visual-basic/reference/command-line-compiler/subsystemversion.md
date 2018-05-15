---
title: -subsystemversion (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22eb8aa1cd86dba4a1a65edf31a3b18df7085a33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-subsystemversion-visual-basic"></a><span data-ttu-id="16d6c-102">-subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16d6c-102">-subsystemversion (Visual Basic)</span></span>
<span data-ttu-id="16d6c-103">Указывает минимальную версию подсистемы, в которой может выполняться созданный исполняемый файл, то есть определяет версии Windows, в которых может работать исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="16d6c-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="16d6c-104">Чаще всего этот параметр предоставляет исполняемому файлу возможность использовать определенные возможности безопасности, недоступные в прежних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="16d6c-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="16d6c-105">Чтобы задать саму подсистему, используйте параметр компилятора [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="16d6c-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16d6c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16d6c-106">Syntax</span></span>  
  
```vb  
-subsystemversion:major.minor  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16d6c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="16d6c-107">Parameters</span></span>  
 `major.minor`  
 <span data-ttu-id="16d6c-108">Минимальная требуемая версия подсистемы, через точку записывается основная и дополнительная версии.</span><span class="sxs-lookup"><span data-stu-id="16d6c-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="16d6c-109">Например, можно указать, что приложение не может выполняться в операционной системе старше Windows 7, если задать для этого параметра значение 6.01, как указано в таблице ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="16d6c-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="16d6c-110">Необходимо указать значения для параметра `major` и `minor` в виде целых чисел.</span><span class="sxs-lookup"><span data-stu-id="16d6c-110">You must specify the values for `major` and `minor` as integers.</span></span>  
  
 <span data-ttu-id="16d6c-111">Нули в начале версии `minor` не изменяют версию, нули в конце — изменяют.</span><span class="sxs-lookup"><span data-stu-id="16d6c-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="16d6c-112">Например, 6.1 и 6.01 — одна версия, а 6.10 — другая.</span><span class="sxs-lookup"><span data-stu-id="16d6c-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="16d6c-113">Рекомендуется указывать дополнительный номер версии двумя цифрами, чтобы избежать путаницы.</span><span class="sxs-lookup"><span data-stu-id="16d6c-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16d6c-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="16d6c-114">Remarks</span></span>  
 <span data-ttu-id="16d6c-115">В следующей таблице перечислены распространенные версии подсистем Windows.</span><span class="sxs-lookup"><span data-stu-id="16d6c-115">The following table lists common subsystem versions of Windows.</span></span>  
  
|<span data-ttu-id="16d6c-116">Версия Windows</span><span class="sxs-lookup"><span data-stu-id="16d6c-116">Windows version</span></span>|<span data-ttu-id="16d6c-117">Версия подсистемы</span><span class="sxs-lookup"><span data-stu-id="16d6c-117">Subsystem version</span></span>|  
|---------------------|-----------------------|  
|<span data-ttu-id="16d6c-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="16d6c-118">Windows 2000</span></span>|<span data-ttu-id="16d6c-119">5.00</span><span class="sxs-lookup"><span data-stu-id="16d6c-119">5.00</span></span>|  
|<span data-ttu-id="16d6c-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="16d6c-120">Windows XP</span></span>|<span data-ttu-id="16d6c-121">5.01</span><span class="sxs-lookup"><span data-stu-id="16d6c-121">5.01</span></span>|  
|<span data-ttu-id="16d6c-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="16d6c-122">Windows Server 2003</span></span>|<span data-ttu-id="16d6c-123">5.02</span><span class="sxs-lookup"><span data-stu-id="16d6c-123">5.02</span></span>|  
|<span data-ttu-id="16d6c-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="16d6c-124">Windows Vista</span></span>|<span data-ttu-id="16d6c-125">6.00</span><span class="sxs-lookup"><span data-stu-id="16d6c-125">6.00</span></span>|  
|<span data-ttu-id="16d6c-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="16d6c-126">Windows 7</span></span>|<span data-ttu-id="16d6c-127">6.01</span><span class="sxs-lookup"><span data-stu-id="16d6c-127">6.01</span></span>|  
|<span data-ttu-id="16d6c-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="16d6c-128">Windows Server 2008</span></span>|<span data-ttu-id="16d6c-129">6.01</span><span class="sxs-lookup"><span data-stu-id="16d6c-129">6.01</span></span>|  
|[!INCLUDE[win8](~/includes/win8-md.md)]|<span data-ttu-id="16d6c-130">6.02</span><span class="sxs-lookup"><span data-stu-id="16d6c-130">6.02</span></span>|  
  
## <a name="default-values"></a><span data-ttu-id="16d6c-131">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="16d6c-131">Default values</span></span>  
 <span data-ttu-id="16d6c-132">Значение по умолчанию параметра компилятора **-subsystemversion** зависит от условий в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="16d6c-132">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>  
  
-   <span data-ttu-id="16d6c-133">Значение по умолчанию — 6.02, если задан любой параметр компилятора из следующего списка.</span><span class="sxs-lookup"><span data-stu-id="16d6c-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>  
  
    -   [<span data-ttu-id="16d6c-134">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="16d6c-134">-target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="16d6c-135">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="16d6c-135">-target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
  
    -   [<span data-ttu-id="16d6c-136">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="16d6c-136">-platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)  
  
-   <span data-ttu-id="16d6c-137">Значение по умолчанию — 6.00, если используется средство MSBuild, приложение предназначено для [!INCLUDE[net_v45](~/includes/net-v45-md.md)], и не установлены параметры компилятора, определенные ранее в этом списке.</span><span class="sxs-lookup"><span data-stu-id="16d6c-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](~/includes/net-v45-md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>  
  
-   <span data-ttu-id="16d6c-138">Если ни одно из предыдущих условий не верно, значение по умолчанию — 4.00.</span><span class="sxs-lookup"><span data-stu-id="16d6c-138">The default value is 4.00 if none of the previous conditions is true.</span></span>  
  
## <a name="setting-this-option"></a><span data-ttu-id="16d6c-139">Задание этого параметра</span><span class="sxs-lookup"><span data-stu-id="16d6c-139">Setting this option</span></span>  
 <span data-ttu-id="16d6c-140">Чтобы задать **- subsystemversion** параметра компилятора в Visual Studio, необходимо открыть VBPROJ-файл и указать значение для `SubsystemVersion` свойство в MSBuild XML.</span><span class="sxs-lookup"><span data-stu-id="16d6c-140">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="16d6c-141">Этот параметр невозможно задать в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="16d6c-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="16d6c-142">Дополнительные сведения см. выше в подразделе "Значения по умолчанию" или в разделе [Общие свойства проектов MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="16d6c-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="16d6c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="16d6c-143">See Also</span></span>  
[<span data-ttu-id="16d6c-144">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="16d6c-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

[<span data-ttu-id="16d6c-145">Свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="16d6c-145">MSBuild Properties</span></span>](/visualstudio/msbuild/msbuild-properties)
