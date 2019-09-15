---
title: Практическое руководство. Создание политики издателя
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
ms.openlocfilehash: 5484dfeb8cf5292fb43393bb39b9878114119d29
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991195"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="8f5cf-102">Практическое руководство. Создание политики издателя</span><span class="sxs-lookup"><span data-stu-id="8f5cf-102">How to: Create a Publisher Policy</span></span>

<span data-ttu-id="8f5cf-103">Поставщики сборок могут указать, что приложения должны использовать более новую версию сборки, включив файл политики издателя с обновленной сборкой.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="8f5cf-104">Файл политики издателя определяет параметры перенаправления сборок и базы кода, а также использует тот же формат, что и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="8f5cf-105">Файл политики издателя компилируется в сборку и помещается в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>

<span data-ttu-id="8f5cf-106">Создание политики издателя состоит из трех этапов.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-106">There are three steps involved in creating a publisher policy:</span></span>

1. <span data-ttu-id="8f5cf-107">Создайте файл политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-107">Create a publisher policy file.</span></span>

2. <span data-ttu-id="8f5cf-108">Создание сборки политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-108">Create a publisher policy assembly.</span></span>

3. <span data-ttu-id="8f5cf-109">Добавьте сборку политики издателя в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-109">Add the publisher policy assembly to the global assembly cache.</span></span>

<span data-ttu-id="8f5cf-110">Схема для политики издателя описана в разделе [Перенаправление версий сборки](redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="8f5cf-110">The schema for publisher policy is described in [Redirecting Assembly Versions](redirect-assembly-versions.md).</span></span> <span data-ttu-id="8f5cf-111">В следующем примере показан файл политики издателя, который перенаправляет одну версию `myAssembly` на другую.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
       <dependentAssembly>
         <assemblyIdentity name="myAssembly"
                           publicKeyToken="32ab4ba45e0a69a1"
                           culture="en-us" />
         <!-- Redirecting to version 2.0.0.0 of the assembly. -->
         <bindingRedirect oldVersion="1.0.0.0"
                          newVersion="2.0.0.0"/>
       </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="8f5cf-112">Сведения о том, как указать базу кода, см. в разделе [Указание расположения сборки](specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="8f5cf-112">To learn how to specify a code base, see [Specifying an Assembly's Location](specify-assembly-location.md).</span></span>

## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="8f5cf-113">Создание сборки политики издателя</span><span class="sxs-lookup"><span data-stu-id="8f5cf-113">Creating the Publisher Policy Assembly</span></span>

<span data-ttu-id="8f5cf-114">Используйте [Компоновщик сборок (Al. exe)](../tools/al-exe-assembly-linker.md) для создания сборки политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-114">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>

#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="8f5cf-115">Создание сборки политики издателя</span><span class="sxs-lookup"><span data-stu-id="8f5cf-115">To create a publisher policy assembly</span></span>

<span data-ttu-id="8f5cf-116">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8f5cf-116">Type the following command at the command prompt:</span></span>

<span data-ttu-id="8f5cf-117">**Al/Link:** *публишерполицифиле* **/out:** *публишерполициассемблифиле* **/keyfile:** *кэйпаирфиле* **/Platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="8f5cf-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>

<span data-ttu-id="8f5cf-118">В этой команде:</span><span class="sxs-lookup"><span data-stu-id="8f5cf-118">In this command:</span></span>

- <span data-ttu-id="8f5cf-119">Аргумент *публишерполицифиле* — это имя файла политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>

- <span data-ttu-id="8f5cf-120">Аргумент *публишерполициассемблифиле* — это имя сборки политики издателя, полученное в результате выполнения этой команды.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="8f5cf-121">Имя файла сборки должно соответствовать формату:</span><span class="sxs-lookup"><span data-stu-id="8f5cf-121">The assembly file name must follow the format:</span></span>

  <span data-ttu-id="8f5cf-122">**политик.**</span><span class="sxs-lookup"><span data-stu-id="8f5cf-122">**policy.**</span></span> <span data-ttu-id="8f5cf-123">*мажорнумбер* **.**</span><span class="sxs-lookup"><span data-stu-id="8f5cf-123">*majorNumber* **.**</span></span> <span data-ttu-id="8f5cf-124">*минорнумбер* **.**</span><span class="sxs-lookup"><span data-stu-id="8f5cf-124">*minorNumber* **.**</span></span> <span data-ttu-id="8f5cf-125">*маинассемблинаме* **. dll**</span><span class="sxs-lookup"><span data-stu-id="8f5cf-125">*mainAssemblyName* **.dll**</span></span>

- <span data-ttu-id="8f5cf-126">Аргумент *кэйпаирфиле* — это имя файла, содержащего пару ключей.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="8f5cf-127">Сборку политики сборки и издателя необходимо подписать с помощью той же пары ключей.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>

- <span data-ttu-id="8f5cf-128">Аргумент *processorArchitecture* определяет платформу, на которую ссылается сборка для конкретного процессора.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>

  > [!NOTE]
  > <span data-ttu-id="8f5cf-129">Возможность ориентироваться на конкретную архитектуру процессора доступна начиная с .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-129">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.</span></span>

<span data-ttu-id="8f5cf-130">Возможность ориентироваться на конкретную архитектуру процессора доступна начиная с версии .NET Framework 2.0. Следующая команда создает сборку `policy.1.0.myAssembly` политики издателя с именем из `pub.config`файла политики издателя, присваивает строгое имя сборка, использующая пару ключей в `sgKey.snk` файле, и указывает, что сборка предназначена для архитектуры процессора x86.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-130">The ability to target a specific processor architecture is available starting with .NET Framework 2.0.The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>

```
al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86
```

<span data-ttu-id="8f5cf-131">Сборка политики издателя должна соответствовать архитектуре процессора сборки, к которой он применяется.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="8f5cf-132">Таким же <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> , если сборка имеет <xref:System.Reflection.ProcessorArchitecture.MSIL>значение, сборка политики издателя для этой сборки должна быть создана с помощью `/platform:anycpu`.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="8f5cf-133">Для каждой сборки конкретного процессора необходимо предоставить отдельную сборку политики издателя.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>

<span data-ttu-id="8f5cf-134">Следствием этого правила является то, что для изменения архитектуры процессора для сборки необходимо изменить основной или дополнительный компонент номера версии, чтобы можно было указать новую сборку политики издателя с правильной архитектурой процессора.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="8f5cf-135">Старая сборка политики издателя не может обслуживать сборку, если сборка имеет другую архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>

<span data-ttu-id="8f5cf-136">Другой следствием является то, что компоновщик версии 2,0 нельзя использовать для создания сборки политики издателя для сборки, скомпилированной с помощью более ранних версий .NET Framework, так как она всегда определяет архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>

## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="8f5cf-137">Добавление сборки политики издателя в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="8f5cf-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>

<span data-ttu-id="8f5cf-138">Используйте [средство глобального кэша сборок (Gacutil. exe)](../tools/gacutil-exe-gac-tool.md) , чтобы добавить сборку политики издателя в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>

### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="8f5cf-139">Добавление сборки политики издателя в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="8f5cf-139">To add the publisher policy assembly to the global assembly cache</span></span>

<span data-ttu-id="8f5cf-140">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8f5cf-140">Type the following command at the command prompt:</span></span>

<span data-ttu-id="8f5cf-141">**gacutil/i** *публишерполициассемблифиле*</span><span class="sxs-lookup"><span data-stu-id="8f5cf-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>

<span data-ttu-id="8f5cf-142">Следующая команда добавляет `policy.1.0.myAssembly.dll` в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>

```
gacutil /i policy.1.0.myAssembly.dll
```

> [!IMPORTANT]
> <span data-ttu-id="8f5cf-143">Сборка политики издателя не может быть добавлена в глобальный кэш сборок, если файл политики исходного издателя не находится в том же каталоге, что и сборка.</span><span class="sxs-lookup"><span data-stu-id="8f5cf-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f5cf-144">См. также</span><span class="sxs-lookup"><span data-stu-id="8f5cf-144">See also</span></span>

- [<span data-ttu-id="8f5cf-145">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="8f5cf-145">Programming with Assemblies</span></span>](../../standard/assembly/program.md)
- [<span data-ttu-id="8f5cf-146">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="8f5cf-146">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="8f5cf-147">Настройка приложений с помощью файлов конфигурации</span><span class="sxs-lookup"><span data-stu-id="8f5cf-147">Configuring Apps by using Configuration Files</span></span>](index.md)
- [<span data-ttu-id="8f5cf-148">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="8f5cf-148">Runtime Settings Schema</span></span>](./file-schema/runtime/index.md)
- [<span data-ttu-id="8f5cf-149">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="8f5cf-149">Configuration File Schema</span></span>](./file-schema/index.md)
- [<span data-ttu-id="8f5cf-150">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="8f5cf-150">Redirecting Assembly Versions</span></span>](redirect-assembly-versions.md)
