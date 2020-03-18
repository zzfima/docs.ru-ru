---
title: Настройка атрибутов сборки
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], attributes
- assembly binding, attributes
- assembly manifest, attributes
ms.assetid: 36a98a81-b5b5-4c19-912a-11f91eff7f4e
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 0e4e2e595ed4f95511bd23ab0ed00139f71b2c8b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73740470"
---
# <a name="set-assembly-attributes"></a><span data-ttu-id="68a07-102">Настройка атрибутов сборки</span><span class="sxs-lookup"><span data-stu-id="68a07-102">Set assembly attributes</span></span>

<span data-ttu-id="68a07-103">Атрибуты сборки — это значения, которые предоставляют сведения о сборке.</span><span class="sxs-lookup"><span data-stu-id="68a07-103">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="68a07-104">Атрибуты разделяются на следующие группы.</span><span class="sxs-lookup"><span data-stu-id="68a07-104">The attributes are divided into the following sets of information:</span></span>

- <span data-ttu-id="68a07-105">Атрибуты удостоверения сборки</span><span class="sxs-lookup"><span data-stu-id="68a07-105">Assembly identity attributes</span></span>

- <span data-ttu-id="68a07-106">Информационные атрибуты</span><span class="sxs-lookup"><span data-stu-id="68a07-106">Informational attributes</span></span>

- <span data-ttu-id="68a07-107">Атрибуты манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="68a07-107">Assembly manifest attributes</span></span>

- <span data-ttu-id="68a07-108">Атрибуты строгого имени</span><span class="sxs-lookup"><span data-stu-id="68a07-108">Strong name attributes</span></span>

## <a name="assembly-identity-attributes"></a><span data-ttu-id="68a07-109">Атрибуты удостоверения сборки</span><span class="sxs-lookup"><span data-stu-id="68a07-109">Assembly identity attributes</span></span>

<span data-ttu-id="68a07-110">Три атрибута вместе со строгим именем (если оно применимо) определяют удостоверение сборки: имя, версия, язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="68a07-110">Three attributes, together with a strong name (if applicable), determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="68a07-111">Эти атрибуты формируют полное имя сборки и являются обязательными при ссылке на сборку в коде.</span><span class="sxs-lookup"><span data-stu-id="68a07-111">These attributes form the full name of the assembly and are required when referencing the assembly in code.</span></span> <span data-ttu-id="68a07-112">Атрибуты можно использовать для задания версии сборки и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="68a07-112">You can use attributes to set an assembly's version and culture.</span></span> <span data-ttu-id="68a07-113">Компилятор или [компоновщик сборок (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) задает значение имени при создании сборки на основе файла, содержащего манифест сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-113">The compiler or the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) sets the name value when the assembly is created, based on the file containing the assembly manifest.</span></span>

<span data-ttu-id="68a07-114">В следующей таблице описаны атрибуты версии и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="68a07-114">The following table describes the version and culture attributes.</span></span>

|<span data-ttu-id="68a07-115">Атрибут удостоверения сборки</span><span class="sxs-lookup"><span data-stu-id="68a07-115">Assembly identity attribute</span></span>|<span data-ttu-id="68a07-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="68a07-116">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="68a07-117">Перечислимое поле, указывающее язык и региональные параметры, поддерживаемые сборкой.</span><span class="sxs-lookup"><span data-stu-id="68a07-117">Enumerated field indicating the culture that the assembly supports.</span></span> <span data-ttu-id="68a07-118">В сборке можно также указать независимость от языка и региональных параметров, чтобы указать, что сборка содержит ресурсы для языка и региональных параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="68a07-118">An assembly can also specify culture independence, indicating that it contains the resources for the default culture.</span></span> <span data-ttu-id="68a07-119">**Примечание.** Среда выполнения рассматривает любую сборку, у которой для атрибута языка и региональных параметров не задано значение NULL, в качестве вспомогательной сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-119">**Note:**  The runtime treats any assembly that does not have the culture attribute set to null as a satellite assembly.</span></span> <span data-ttu-id="68a07-120">Такие сборки подчиняются правилам привязки вспомогательных сборок.</span><span class="sxs-lookup"><span data-stu-id="68a07-120">Such assemblies are subject to satellite assembly binding rules.</span></span> <span data-ttu-id="68a07-121">Дополнительные сведения см. в разделе [Обнаружение сборок в среде выполнения](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="68a07-121">For more information, see [How the runtime locates assemblies](../../framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>|
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="68a07-122">Значение, задающее атрибуты сборки: например, может ли сборка выполняться параллельно.</span><span class="sxs-lookup"><span data-stu-id="68a07-122">Value that sets assembly attributes, such as whether the assembly can be run side by side.</span></span>|
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="68a07-123">Числовое значение в формате *основной_номер*.*дополнительный_номер*.*номер_сборки*.*номер_редакции* (например, 2.4.0.0).</span><span class="sxs-lookup"><span data-stu-id="68a07-123">Numeric value in the format *major*.*minor*.*build*.*revision* (for example, 2.4.0.0).</span></span> <span data-ttu-id="68a07-124">Среда CLR использует это значение для выполнения операций привязки в сборках со строгими именами.</span><span class="sxs-lookup"><span data-stu-id="68a07-124">The common language runtime uses this value to perform binding operations in strong-named assemblies.</span></span> <span data-ttu-id="68a07-125">**Примечание.** Если атрибут <xref:System.Reflection.AssemblyInformationalVersionAttribute> не применен к сборке, то номер версии, задаваемый атрибутом <xref:System.Reflection.AssemblyVersionAttribute>, используется свойствами <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68a07-125">**Note:**  If the <xref:System.Reflection.AssemblyInformationalVersionAttribute> attribute is not applied to an assembly, the version number specified by the <xref:System.Reflection.AssemblyVersionAttribute> attribute is used by the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>, <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType>, and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|

<span data-ttu-id="68a07-126">В следующем примере кода показано, как применить атрибуты версии и языка и региональных параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-126">The following code example shows how to apply the version and culture attributes to an assembly.</span></span>

```cpp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")];
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")];
```

```csharp
// Set version number for the assembly.
[assembly:AssemblyVersionAttribute("4.3.2.1")]
// Set culture as German.
[assembly:AssemblyCultureAttribute("de")]
```

```vb
' Set version number for the assembly.
<Assembly:AssemblyVersionAttribute("4.3.2.1")>
' Set culture as German.
<Assembly:AssemblyCultureAttribute("de")>
```

## <a name="informational-attributes"></a><span data-ttu-id="68a07-127">Информационные атрибуты</span><span class="sxs-lookup"><span data-stu-id="68a07-127">Informational attributes</span></span>

<span data-ttu-id="68a07-128">Информационные атрибуты можно использовать для предоставления дополнительных сведений о компании или продукте в сборке.</span><span class="sxs-lookup"><span data-stu-id="68a07-128">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="68a07-129">В следующей таблице описаны информационные атрибуты, которые можно применить к сборке.</span><span class="sxs-lookup"><span data-stu-id="68a07-129">The following table describes the informational attributes you can apply to an assembly.</span></span>

|<span data-ttu-id="68a07-130">Информационный атрибут</span><span class="sxs-lookup"><span data-stu-id="68a07-130">Informational attribute</span></span>|<span data-ttu-id="68a07-131">Описание:</span><span class="sxs-lookup"><span data-stu-id="68a07-131">Description</span></span>|
|-----------------------------|-----------------|
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="68a07-132">Строковое значение, содержащее название компании.</span><span class="sxs-lookup"><span data-stu-id="68a07-132">String value specifying a company name.</span></span>|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="68a07-133">Строковое значение, содержащее сведения об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="68a07-133">String value specifying copyright information.</span></span>|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="68a07-134">Строковое значение, содержащее номер версии файла Win32.</span><span class="sxs-lookup"><span data-stu-id="68a07-134">String value specifying the Win32 file version number.</span></span> <span data-ttu-id="68a07-135">Обычно по умолчанию здесь используется версия сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-135">This normally defaults to the assembly version.</span></span>|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="68a07-136">Строковое значение, содержащее сведения о версии, которые не используются средой CLR, например полный номер версии продукта.</span><span class="sxs-lookup"><span data-stu-id="68a07-136">String value specifying version information that is not used by the common language runtime, such as a full product version number.</span></span> <span data-ttu-id="68a07-137">**Примечание.** Если этот атрибут применен к сборке, указываемую им строку можно получить во время выполнения с помощью свойства <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="68a07-137">**Note:**  If this attribute is applied to an assembly, the string it specifies can be obtained at run time by using the <xref:System.Windows.Forms.Application.ProductVersion%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="68a07-138">Эта строка также используется в пути и разделе реестра, предоставляемых свойствами <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="68a07-138">The string is also used in the path and registry key provided by the <xref:System.Windows.Forms.Application.UserAppDataPath%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.Application.UserAppDataRegistry%2A?displayProperty=nameWithType> properties.</span></span>|
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="68a07-139">Строковое значение, содержащее сведения о продукте.</span><span class="sxs-lookup"><span data-stu-id="68a07-139">String value specifying product information.</span></span>|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="68a07-140">Строковое значение, содержащее сведения о товарном знаке.</span><span class="sxs-lookup"><span data-stu-id="68a07-140">String value specifying trademark information.</span></span>|

<span data-ttu-id="68a07-141">Эти атрибуты могут отображаться на странице свойств сборки в Windows и могут быть переопределены с помощью параметра компилятора **/win32res** , с помощью которого вы можете задать собственный файл ресурсов Win32.</span><span class="sxs-lookup"><span data-stu-id="68a07-141">These attributes can appear on the Windows Properties page of the assembly, or they can be overridden using the **/win32res** compiler option to specify your own Win32 resource file.</span></span>

## <a name="assembly-manifest-attributes"></a><span data-ttu-id="68a07-142">Атрибуты манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="68a07-142">Assembly manifest attributes</span></span>

<span data-ttu-id="68a07-143">Атрибуты манифеста сборки можно использовать для предоставления сведений в манифесте сборки, включая название, описание, псевдоним по умолчанию и конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="68a07-143">You can use assembly manifest attributes to provide information in the assembly manifest, including title, description, the default alias, and configuration.</span></span> <span data-ttu-id="68a07-144">В следующей таблице описаны атрибуты манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-144">The following table describes the assembly manifest attributes.</span></span>

|<span data-ttu-id="68a07-145">Атрибуты манифеста сборки</span><span class="sxs-lookup"><span data-stu-id="68a07-145">Assembly manifest attribute</span></span>|<span data-ttu-id="68a07-146">Описание:</span><span class="sxs-lookup"><span data-stu-id="68a07-146">Description</span></span>|
|---------------------------------|-----------------|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="68a07-147">Строковое значение, содержащее конфигурацию сборки, например Retail или Debug.</span><span class="sxs-lookup"><span data-stu-id="68a07-147">String value indicating the configuration of the assembly, such as Retail or Debug.</span></span> <span data-ttu-id="68a07-148">Среда выполнения не использует это значение.</span><span class="sxs-lookup"><span data-stu-id="68a07-148">The runtime does not use this value.</span></span>|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="68a07-149">Строковое значение, содержащее псевдоним по умолчанию, используемый для ссылки на эту сборку из других сборок.</span><span class="sxs-lookup"><span data-stu-id="68a07-149">String value specifying a default alias to be used by referencing assemblies.</span></span> <span data-ttu-id="68a07-150">Это значение предоставляет понятное имя, если имя сборки само по себе не является понятным (например, если это значение идентификатора GUID).</span><span class="sxs-lookup"><span data-stu-id="68a07-150">This value provides a friendly name when the name of the assembly itself is not friendly (such as a GUID value).</span></span> <span data-ttu-id="68a07-151">Это значение можно также использовать как краткую форму полного имени сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-151">This value can also be used as a short form of the full assembly name.</span></span>|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="68a07-152">Строковое значение, содержащее краткое описание сути и назначения сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-152">String value specifying a short description that summarizes the nature and purpose of the assembly.</span></span>|
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="68a07-153">Строковое значение, содержащее понятное имя сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-153">String value specifying a friendly name for the assembly.</span></span> <span data-ttu-id="68a07-154">Например, сборка с именем *comdlg* может иметь название "Элемент управления стандартного диалогового окна Майкрософт".</span><span class="sxs-lookup"><span data-stu-id="68a07-154">For example, an assembly named *comdlg* might have the title Microsoft Common Dialog Control.</span></span>|

## <a name="strong-name-attributes"></a><span data-ttu-id="68a07-155">Атрибуты строгого имени</span><span class="sxs-lookup"><span data-stu-id="68a07-155">Strong name attributes</span></span>

<span data-ttu-id="68a07-156">Атрибуты строгого имени можно использовать для задания строгого имени сборки.</span><span class="sxs-lookup"><span data-stu-id="68a07-156">You can use strong name attributes to set a strong name for an assembly.</span></span> <span data-ttu-id="68a07-157">В таблице ниже описываются атрибуты строгого имени.</span><span class="sxs-lookup"><span data-stu-id="68a07-157">The following table describes the strong name attributes.</span></span>

|<span data-ttu-id="68a07-158">Атрибут строгого имени</span><span class="sxs-lookup"><span data-stu-id="68a07-158">Strong name attribute</span></span>|<span data-ttu-id="68a07-159">Описание:</span><span class="sxs-lookup"><span data-stu-id="68a07-159">Description</span></span>|
|----------------------------|-----------------|
|<xref:System.Reflection.AssemblyDelaySignAttribute>|<span data-ttu-id="68a07-160">Логическое значение, указывающее, что используется отложенная подпись.</span><span class="sxs-lookup"><span data-stu-id="68a07-160">Boolean value indicating that delay signing is being used.</span></span>|
|<xref:System.Reflection.AssemblyKeyFileAttribute>|<span data-ttu-id="68a07-161">Строковое значение, указывающее имя файла, который содержит открытый ключ (при использовании отложенной подписи), или открытый и закрытый ключи, передаваемые в качестве параметра в конструктор этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="68a07-161">String value indicating the name of the file that contains either the public key (if using delay signing) or both the public and private keys passed as a parameter to the constructor of this attribute.</span></span> <span data-ttu-id="68a07-162">Обратите внимание, что имя файла указано относительно пути к выходному файлу (*EXE* или *DLL*), а не пути к исходному файлу.</span><span class="sxs-lookup"><span data-stu-id="68a07-162">Note that the file name is relative to the output file path (the *.exe* or *.dll*), not the source file path.</span></span>|
|<xref:System.Reflection.AssemblyKeyNameAttribute>|<span data-ttu-id="68a07-163">Указывает контейнер ключей, содержащий пару ключей, передаваемых в качестве параметра в конструктор этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="68a07-163">Indicates the key container that contains the key pair passed as a parameter to the constructor of this attribute.</span></span>|

<span data-ttu-id="68a07-164">В следующем примере кода показаны атрибуты, применяемые при использовании отложенной подписи для создания сборки со строгим именем с помощью файла открытого ключа *myKey.snk*.</span><span class="sxs-lookup"><span data-stu-id="68a07-164">The following code example shows the attributes to apply when using delay signing to create a strong-named assembly with a public key file called *myKey.snk*.</span></span>

```cpp
[assembly:AssemblyKeyFileAttribute("myKey.snk")];
[assembly:AssemblyDelaySignAttribute(true)];
```

```csharp
[assembly:AssemblyKeyFileAttribute("myKey.snk")]
[assembly:AssemblyDelaySignAttribute(true)]
```

```vb
<Assembly:AssemblyKeyFileAttribute("myKey.snk")>
<Assembly:AssemblyDelaySignAttribute(True)>
```

## <a name="see-also"></a><span data-ttu-id="68a07-165">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="68a07-165">See also</span></span>

- [<span data-ttu-id="68a07-166">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="68a07-166">Create assemblies</span></span>](create.md)
