---
title: -subsystemversion (параметры компилятора C#)
ms.date: 07/20/2015
ms.assetid: a99fce81-9d92-4813-9874-bee777041445
ms.openlocfilehash: d76c9424340b4b6f3c211c849b466be55eb79d1e
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802042"
---
# <a name="-subsystemversion-c-compiler-options"></a><span data-ttu-id="f1b73-102">-subsystemversion (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="f1b73-102">-subsystemversion (C# Compiler Options)</span></span>

<span data-ttu-id="f1b73-103">Указывает минимальную версию подсистемы, в которой может выполняться созданный исполняемый файл, то есть определяет версии Windows, в которых может работать исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="f1b73-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="f1b73-104">Чаще всего этот параметр предоставляет исполняемому файлу возможность использовать определенные возможности безопасности, недоступные в прежних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="f1b73-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="f1b73-105">Чтобы задать саму подсистему, используйте параметр компилятора [-target](./target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f1b73-105">To specify the subsystem itself, use the [-target](./target-compiler-option.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1b73-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f1b73-106">Syntax</span></span>

```console
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="f1b73-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f1b73-107">Parameters</span></span>

`major.minor`

<span data-ttu-id="f1b73-108">Минимальная требуемая версия подсистемы, через точку записывается основная и дополнительная версии.</span><span class="sxs-lookup"><span data-stu-id="f1b73-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="f1b73-109">Например, можно указать, что приложение не может выполняться в операционной системе старше Windows 7, если задать для этого параметра значение 6.01, как указано в таблице ниже в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f1b73-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="f1b73-110">Необходимо указать значения для параметра `major` и `minor` в виде целых чисел.</span><span class="sxs-lookup"><span data-stu-id="f1b73-110">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="f1b73-111">Нули в начале версии `minor` не изменяют версию, нули в конце — изменяют.</span><span class="sxs-lookup"><span data-stu-id="f1b73-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="f1b73-112">Например, 6.1 и 6.01 — одна версия, а 6.10 — другая.</span><span class="sxs-lookup"><span data-stu-id="f1b73-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="f1b73-113">Рекомендуется указывать дополнительный номер версии двумя цифрами, чтобы избежать путаницы.</span><span class="sxs-lookup"><span data-stu-id="f1b73-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="f1b73-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="f1b73-114">Remarks</span></span>

<span data-ttu-id="f1b73-115">В следующей таблице перечислены распространенные версии подсистем Windows.</span><span class="sxs-lookup"><span data-stu-id="f1b73-115">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="f1b73-116">Версия Windows</span><span class="sxs-lookup"><span data-stu-id="f1b73-116">Windows version</span></span>|<span data-ttu-id="f1b73-117">Версия подсистемы</span><span class="sxs-lookup"><span data-stu-id="f1b73-117">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="f1b73-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="f1b73-118">Windows 2000</span></span>|<span data-ttu-id="f1b73-119">5.00</span><span class="sxs-lookup"><span data-stu-id="f1b73-119">5.00</span></span>|
|<span data-ttu-id="f1b73-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="f1b73-120">Windows XP</span></span>|<span data-ttu-id="f1b73-121">5.01</span><span class="sxs-lookup"><span data-stu-id="f1b73-121">5.01</span></span>|
|<span data-ttu-id="f1b73-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="f1b73-122">Windows Server 2003</span></span>|<span data-ttu-id="f1b73-123">5.02</span><span class="sxs-lookup"><span data-stu-id="f1b73-123">5.02</span></span>|
|<span data-ttu-id="f1b73-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="f1b73-124">Windows Vista</span></span>|<span data-ttu-id="f1b73-125">6.00</span><span class="sxs-lookup"><span data-stu-id="f1b73-125">6.00</span></span>|
|<span data-ttu-id="f1b73-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="f1b73-126">Windows 7</span></span>|<span data-ttu-id="f1b73-127">6.01</span><span class="sxs-lookup"><span data-stu-id="f1b73-127">6.01</span></span>|
|<span data-ttu-id="f1b73-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="f1b73-128">Windows Server 2008</span></span>|<span data-ttu-id="f1b73-129">6.01</span><span class="sxs-lookup"><span data-stu-id="f1b73-129">6.01</span></span>|
|<span data-ttu-id="f1b73-130">Windows 8</span><span class="sxs-lookup"><span data-stu-id="f1b73-130">Windows 8</span></span>|<span data-ttu-id="f1b73-131">6.02</span><span class="sxs-lookup"><span data-stu-id="f1b73-131">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="f1b73-132">Значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f1b73-132">Default values</span></span>

<span data-ttu-id="f1b73-133">Значение по умолчанию параметра компилятора **-subsystemversion** зависит от условий в следующем списке:</span><span class="sxs-lookup"><span data-stu-id="f1b73-133">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="f1b73-134">Значение по умолчанию — 6.02, если задан любой параметр компилятора из следующего списка.</span><span class="sxs-lookup"><span data-stu-id="f1b73-134">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="f1b73-135">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="f1b73-135">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)

  - [<span data-ttu-id="f1b73-136">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="f1b73-136">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)

  - [<span data-ttu-id="f1b73-137">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="f1b73-137">-platform:arm</span></span>](./platform-compiler-option.md)

- <span data-ttu-id="f1b73-138">Значение по умолчанию — 6.00, если используется средство MSBuild, приложение предназначено для .NET Framework 4.5 и не установлены параметры компилятора, определенные ранее в этом списке.</span><span class="sxs-lookup"><span data-stu-id="f1b73-138">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="f1b73-139">Если ни одно из предыдущих условий не верно, значение по умолчанию — 4.00.</span><span class="sxs-lookup"><span data-stu-id="f1b73-139">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="f1b73-140">Задание этого параметра</span><span class="sxs-lookup"><span data-stu-id="f1b73-140">Setting this option</span></span>

<span data-ttu-id="f1b73-141">Чтобы задать параметр компилятора **-subsystemversion** в Visual Studio, нужно открыть CSPROJ-файл и указать значение для свойства `SubsystemVersion` в XML MSBuild.</span><span class="sxs-lookup"><span data-stu-id="f1b73-141">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .csproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="f1b73-142">Этот параметр невозможно задать в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f1b73-142">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="f1b73-143">Дополнительные сведения см. выше в подразделе "Значения по умолчанию" или в разделе [Общие свойства проектов MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="f1b73-143">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1b73-144">См. также</span><span class="sxs-lookup"><span data-stu-id="f1b73-144">See also</span></span>

- [<span data-ttu-id="f1b73-145">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="f1b73-145">C# Compiler Options</span></span>](./index.md)
