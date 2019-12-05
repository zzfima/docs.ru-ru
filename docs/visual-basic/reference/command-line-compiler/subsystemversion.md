---
title: -subsystemversion
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: e8607f8254783b5486b02ccc4c7e4081da506fae
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802158"
---
# <a name="-subsystemversion-visual-basic"></a><span data-ttu-id="335be-102">-subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="335be-102">-subsystemversion (Visual Basic)</span></span>

<span data-ttu-id="335be-103">Указывает минимальную версию подсистемы, в которой может выполняться созданный исполняемый файл, то есть определяет версии Windows, в которых может работать исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="335be-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="335be-104">Чаще всего этот параметр предоставляет исполняемому файлу возможность использовать определенные возможности безопасности, недоступные в прежних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="335be-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="335be-105">Чтобы задать саму подсистему, используйте параметр компилятора [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="335be-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="335be-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="335be-106">Syntax</span></span>

```vb
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="335be-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="335be-107">Parameters</span></span>

`major.minor`

<span data-ttu-id="335be-108">Минимальная требуемая версия подсистемы, через точку записывается основная и дополнительная версии.</span><span class="sxs-lookup"><span data-stu-id="335be-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="335be-109">Например, можно указать, что приложение не может выполняться в операционной системе старше Windows 7, если задать для этого параметра значение 6.01, как указано в таблице ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="335be-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="335be-110">Необходимо указать значения для параметра `major` и `minor` в виде целых чисел.</span><span class="sxs-lookup"><span data-stu-id="335be-110">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="335be-111">Нули в начале версии `minor` не изменяют версию, нули в конце — изменяют.</span><span class="sxs-lookup"><span data-stu-id="335be-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="335be-112">Например, 6.1 и 6.01 — одна версия, а 6.10 — другая.</span><span class="sxs-lookup"><span data-stu-id="335be-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="335be-113">Рекомендуется указывать дополнительный номер версии двумя цифрами, чтобы избежать путаницы.</span><span class="sxs-lookup"><span data-stu-id="335be-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="335be-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="335be-114">Remarks</span></span>

<span data-ttu-id="335be-115">В следующей таблице перечислены распространенные версии подсистем Windows.</span><span class="sxs-lookup"><span data-stu-id="335be-115">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="335be-116">Версия Windows</span><span class="sxs-lookup"><span data-stu-id="335be-116">Windows version</span></span>|<span data-ttu-id="335be-117">Версия подсистемы</span><span class="sxs-lookup"><span data-stu-id="335be-117">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="335be-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="335be-118">Windows 2000</span></span>|<span data-ttu-id="335be-119">5,00</span><span class="sxs-lookup"><span data-stu-id="335be-119">5.00</span></span>|
|<span data-ttu-id="335be-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="335be-120">Windows XP</span></span>|<span data-ttu-id="335be-121">5.01</span><span class="sxs-lookup"><span data-stu-id="335be-121">5.01</span></span>|
|<span data-ttu-id="335be-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="335be-122">Windows Server 2003</span></span>|<span data-ttu-id="335be-123">5.02</span><span class="sxs-lookup"><span data-stu-id="335be-123">5.02</span></span>|
|<span data-ttu-id="335be-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="335be-124">Windows Vista</span></span>|<span data-ttu-id="335be-125">6.00</span><span class="sxs-lookup"><span data-stu-id="335be-125">6.00</span></span>|
|<span data-ttu-id="335be-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="335be-126">Windows 7</span></span>|<span data-ttu-id="335be-127">6.01</span><span class="sxs-lookup"><span data-stu-id="335be-127">6.01</span></span>|
|<span data-ttu-id="335be-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="335be-128">Windows Server 2008</span></span>|<span data-ttu-id="335be-129">6.01</span><span class="sxs-lookup"><span data-stu-id="335be-129">6.01</span></span>|
|<span data-ttu-id="335be-130">Windows 8</span><span class="sxs-lookup"><span data-stu-id="335be-130">Windows 8</span></span>|<span data-ttu-id="335be-131">6.02</span><span class="sxs-lookup"><span data-stu-id="335be-131">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="335be-132">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="335be-132">Default values</span></span>

<span data-ttu-id="335be-133">Значение по умолчанию параметра компилятора **-subsystemversion** зависит от условий в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="335be-133">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="335be-134">Значение по умолчанию — 6.02, если задан любой параметр компилятора из следующего списка.</span><span class="sxs-lookup"><span data-stu-id="335be-134">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="335be-135">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="335be-135">-target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)

  - [<span data-ttu-id="335be-136">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="335be-136">-target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)

  - [<span data-ttu-id="335be-137">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="335be-137">-platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)

- <span data-ttu-id="335be-138">Значение по умолчанию — 6.00, если используется средство MSBuild, приложение предназначено для .NET Framework 4.5 и не установлены параметры компилятора, определенные ранее в этом списке.</span><span class="sxs-lookup"><span data-stu-id="335be-138">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="335be-139">Если ни одно из предыдущих условий не верно, значение по умолчанию — 4.00.</span><span class="sxs-lookup"><span data-stu-id="335be-139">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="335be-140">Задание этого параметра</span><span class="sxs-lookup"><span data-stu-id="335be-140">Setting this option</span></span>

<span data-ttu-id="335be-141">Чтобы задать параметр компилятора **-subsystemversion** в Visual Studio, необходимо открыть VBPROJ-файл и указать значение для свойства `SubsystemVersion` в XML MSBuild.</span><span class="sxs-lookup"><span data-stu-id="335be-141">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="335be-142">Этот параметр невозможно задать в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="335be-142">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="335be-143">Дополнительные сведения см. выше в подразделе "Значения по умолчанию" или в разделе [Общие свойства проектов MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="335be-143">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="335be-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="335be-144">See also</span></span>

- [<span data-ttu-id="335be-145">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="335be-145">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

- [<span data-ttu-id="335be-146">Свойства MSBuild</span><span class="sxs-lookup"><span data-stu-id="335be-146">MSBuild Properties</span></span>](/visualstudio/msbuild/msbuild-properties)
