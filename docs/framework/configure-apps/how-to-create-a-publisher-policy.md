---
title: Практическое руководство. Создание политики издателя
ms.date: 03/30/2017
helpviewer_keywords:
- publisher policy assembly
- publisher policy files
- GAC (global assembly cache), publisher policy assembly
- global assembly cache, publisher policy assembly
ms.assetid: 8046bc5d-2fa9-4277-8a5e-6dcc96c281d9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3fdc3786be3307e8c882a33b5139ee34344733b8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504822"
---
# <a name="how-to-create-a-publisher-policy"></a><span data-ttu-id="c1cde-102">Практическое руководство. Создание политики издателя</span><span class="sxs-lookup"><span data-stu-id="c1cde-102">How to: Create a Publisher Policy</span></span>
<span data-ttu-id="c1cde-103">Поставщики сборок можно указать, что приложения должны использовать более новой версии сборки, включая файл политики издателя с обновленной сборкой.</span><span class="sxs-lookup"><span data-stu-id="c1cde-103">Vendors of assemblies can state that applications should use a newer version of an assembly by including a publisher policy file with the upgraded assembly.</span></span> <span data-ttu-id="c1cde-104">Файл политики издателя указывает перенаправление сборки и параметры базы кода и используется тот же формат, что и файл конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="c1cde-104">The publisher policy file specifies assembly redirection and code base settings, and uses the same format as an application configuration file.</span></span> <span data-ttu-id="c1cde-105">Файл политики издателя компилируется в сборку и помещен в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="c1cde-105">The publisher policy file is compiled into an assembly and placed in the global assembly cache.</span></span>  
  
 <span data-ttu-id="c1cde-106">Существует три действия, связанные с созданием политики издателя:</span><span class="sxs-lookup"><span data-stu-id="c1cde-106">There are three steps involved in creating a publisher policy:</span></span>  
  
1.  <span data-ttu-id="c1cde-107">Создайте файл политики издателя.</span><span class="sxs-lookup"><span data-stu-id="c1cde-107">Create a publisher policy file.</span></span>  
  
2.  <span data-ttu-id="c1cde-108">Создание сборки политики издателя.</span><span class="sxs-lookup"><span data-stu-id="c1cde-108">Create a publisher policy assembly.</span></span>  
  
3.  <span data-ttu-id="c1cde-109">Добавьте сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="c1cde-109">Add the publisher policy assembly to the global assembly cache.</span></span>  
  
 <span data-ttu-id="c1cde-110">Схема для политики издателя описана в [Перенаправление версий сборки](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span><span class="sxs-lookup"><span data-stu-id="c1cde-110">The schema for publisher policy is described in [Redirecting Assembly Versions](../../../docs/framework/configure-apps/redirect-assembly-versions.md).</span></span> <span data-ttu-id="c1cde-111">В следующем примере показано издателя файл политики, который перенаправляет одну версию `myAssembly` в другой.</span><span class="sxs-lookup"><span data-stu-id="c1cde-111">The following example shows a publisher policy file that redirects one version of `myAssembly` to another.</span></span>  
  
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
  
 <span data-ttu-id="c1cde-112">Чтобы узнать, как для указания базового кода, см. в разделе [Указание расположения сборки](../../../docs/framework/configure-apps/specify-assembly-location.md).</span><span class="sxs-lookup"><span data-stu-id="c1cde-112">To learn how to specify a code base, see [Specifying an Assembly's Location](../../../docs/framework/configure-apps/specify-assembly-location.md).</span></span>  
  
## <a name="creating-the-publisher-policy-assembly"></a><span data-ttu-id="c1cde-113">Создание сборки политики издателя</span><span class="sxs-lookup"><span data-stu-id="c1cde-113">Creating the Publisher Policy Assembly</span></span>  
 <span data-ttu-id="c1cde-114">Используйте [компоновщик сборок (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) для создания сборки политики издателя.</span><span class="sxs-lookup"><span data-stu-id="c1cde-114">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the publisher policy assembly.</span></span>  
  
#### <a name="to-create-a-publisher-policy-assembly"></a><span data-ttu-id="c1cde-115">Для создания сборки политики издателя</span><span class="sxs-lookup"><span data-stu-id="c1cde-115">To create a publisher policy assembly</span></span>  
  
1.  <span data-ttu-id="c1cde-116">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="c1cde-116">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="c1cde-117">**Al/LINK:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:**  *keyPairFile* **/Platform:** *processorArchitecture*</span><span class="sxs-lookup"><span data-stu-id="c1cde-117">**al /link:** *publisherPolicyFile* **/out:** *publisherPolicyAssemblyFile* **/keyfile:** *keyPairFile* **/platform:** *processorArchitecture*</span></span>  
  
     <span data-ttu-id="c1cde-118">В этой команде:</span><span class="sxs-lookup"><span data-stu-id="c1cde-118">In this command:</span></span>  
  
    -   <span data-ttu-id="c1cde-119">*PublisherPolicyFile* аргумента — имя файла политики издателя.</span><span class="sxs-lookup"><span data-stu-id="c1cde-119">The *publisherPolicyFile* argument is the name of the publisher policy file.</span></span>  
  
    -   <span data-ttu-id="c1cde-120">*PublisherPolicyAssemblyFile* аргумента — имя сборки политики издателя, полученный в результате этой команды.</span><span class="sxs-lookup"><span data-stu-id="c1cde-120">The *publisherPolicyAssemblyFile* argument is the name of the publisher policy assembly that results from this command.</span></span> <span data-ttu-id="c1cde-121">Имя файла сборки должны иметь формат:</span><span class="sxs-lookup"><span data-stu-id="c1cde-121">The assembly file name must follow the format:</span></span>  
  
         <span data-ttu-id="c1cde-122">**политика.**</span><span class="sxs-lookup"><span data-stu-id="c1cde-122">**policy.**</span></span> <span data-ttu-id="c1cde-123">*majorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="c1cde-123">*majorNumber* **.**</span></span> <span data-ttu-id="c1cde-124">*minorNumber* **.**</span><span class="sxs-lookup"><span data-stu-id="c1cde-124">*minorNumber* **.**</span></span> <span data-ttu-id="c1cde-125">*mainAssemblyName* **.dll**</span><span class="sxs-lookup"><span data-stu-id="c1cde-125">*mainAssemblyName* **.dll**</span></span>  
  
    -   <span data-ttu-id="c1cde-126">*KeyPairFile* аргумента — имя файла, содержащего пару ключей.</span><span class="sxs-lookup"><span data-stu-id="c1cde-126">The *keyPairFile* argument is the name of the file containing the key pair.</span></span> <span data-ttu-id="c1cde-127">Необходимо подписать сборку и сборки политики издателя ту же пару ключей.</span><span class="sxs-lookup"><span data-stu-id="c1cde-127">You must sign the assembly and publisher policy assembly with the same key pair.</span></span>  
  
    -   <span data-ttu-id="c1cde-128">*ProcessorArchitecture* аргумент определяет платформы, являющейся целевой для сборки с конкретного процессора.</span><span class="sxs-lookup"><span data-stu-id="c1cde-128">The *processorArchitecture* argument identifies the platform targeted by a processor-specific assembly.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c1cde-129">Возможность использования на архитектуру процессора является новым в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="c1cde-129">The ability to target a specific processor architecture is new in the .NET Framework version 2.0.</span></span>  
  
     <span data-ttu-id="c1cde-130">Следующая команда создает сборку политики издателя `policy.1.0.myAssembly` из файла политики издателя с именем `pub.config`, назначает строгое имя сборки с помощью пары ключей в `sgKey.snk` файла и указывает, что целевой x86 архитектура процессора.</span><span class="sxs-lookup"><span data-stu-id="c1cde-130">The following command creates a publisher policy assembly called `policy.1.0.myAssembly` from a publisher policy file called `pub.config`, assigns a strong name to the assembly using the key pair in the `sgKey.snk` file, and specifies that the assembly targets the x86 processor architecture.</span></span>  
  
    ```  
    al /link:pub.config /out:policy.1.0.myAssembly.dll /keyfile:sgKey.snk /platform:x86  
    ```  
  
     <span data-ttu-id="c1cde-131">Сборка политики издателя должен соответствовать архитектуре процессора сборки, к которому он применяется.</span><span class="sxs-lookup"><span data-stu-id="c1cde-131">The publisher policy assembly must match the processor architecture of the assembly that it applies to.</span></span> <span data-ttu-id="c1cde-132">Таким образом Если сборка имеет <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> значение <xref:System.Reflection.ProcessorArchitecture.MSIL>, сборка политики издателя для этой сборки, которые должны создаваться с помощью `/platform:anycpu`.</span><span class="sxs-lookup"><span data-stu-id="c1cde-132">Thus, if your assembly has a <xref:System.Reflection.AssemblyName.ProcessorArchitecture%2A> value of <xref:System.Reflection.ProcessorArchitecture.MSIL>, the publisher policy assembly for that assembly must be created with `/platform:anycpu`.</span></span> <span data-ttu-id="c1cde-133">Необходимо предоставить отдельную сборку политики издателя для каждой сборки для конкретного процессора.</span><span class="sxs-lookup"><span data-stu-id="c1cde-133">You must provide a separate publisher policy assembly for each processor-specific assembly.</span></span>  
  
     <span data-ttu-id="c1cde-134">Вследствие этого правила является, чтобы изменить архитектуру процессора для сборки, необходимо изменить основной или вспомогательной компонент номера версии, таким образом, можно указать новую сборку политики издателя с правильную архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="c1cde-134">A consequence of this rule is that in order to change the processor architecture for an assembly, you must change the major or minor component of the version number, so that you can supply a new publisher policy assembly with the correct processor architecture.</span></span> <span data-ttu-id="c1cde-135">Старая сборка политики издателя не может применяться к сборке, если она имеет архитектуру процессора, отличной от.</span><span class="sxs-lookup"><span data-stu-id="c1cde-135">The old publisher policy assembly cannot service your assembly once your assembly has a different processor architecture.</span></span>  
  
     <span data-ttu-id="c1cde-136">Второе — то, что компоновщик версии 2.0 не может использоваться для создания сборки политики издателя для сборки, скомпилированной с помощью более ранних версий платформы .NET Framework, поскольку он всегда задает архитектуру процессора.</span><span class="sxs-lookup"><span data-stu-id="c1cde-136">Another consequence is that the version 2.0 linker cannot be used to create a publisher policy assembly for an assembly compiled using earlier versions of the .NET Framework, because it always specifies processor architecture.</span></span>  
  
## <a name="adding-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="c1cde-137">Добавление сборки политики издателя в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="c1cde-137">Adding the Publisher Policy Assembly to the Global Assembly Cache</span></span>  
 <span data-ttu-id="c1cde-138">Используйте [средство глобального кэша сборок (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) добавляемый сборку в глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="c1cde-138">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to add the publisher policy assembly to the global assembly cache.</span></span>  
  
#### <a name="to-add-the-publisher-policy-assembly-to-the-global-assembly-cache"></a><span data-ttu-id="c1cde-139">Чтобы добавить сборку в глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="c1cde-139">To add the publisher policy assembly to the global assembly cache</span></span>  
  
1.  <span data-ttu-id="c1cde-140">Введите следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="c1cde-140">Type the following command at the command prompt:</span></span>  
  
     <span data-ttu-id="c1cde-141">**Gacutil /i***publisherPolicyAssemblyFile*</span><span class="sxs-lookup"><span data-stu-id="c1cde-141">**gacutil /i**  *publisherPolicyAssemblyFile*</span></span>  
  
     <span data-ttu-id="c1cde-142">Следующая команда добавляет `policy.1.0.myAssembly.dll` в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="c1cde-142">The following command adds `policy.1.0.myAssembly.dll` to the global assembly cache.</span></span>  
  
    ```  
    gacutil /i policy.1.0.myAssembly.dll  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c1cde-143">Сборку в глобальный кэш сборок невозможно, если исходный файл политики издателя находится в том же каталоге, что и сборка.</span><span class="sxs-lookup"><span data-stu-id="c1cde-143">The publisher policy assembly cannot be added to the global assembly cache unless the original publisher policy file is located in the same directory as the assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1cde-144">См. также</span><span class="sxs-lookup"><span data-stu-id="c1cde-144">See Also</span></span>  
 [<span data-ttu-id="c1cde-145">Программирование с использованием сборок</span><span class="sxs-lookup"><span data-stu-id="c1cde-145">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="c1cde-146">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="c1cde-146">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="c1cde-147">Настройка приложений</span><span class="sxs-lookup"><span data-stu-id="c1cde-147">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="c1cde-148">Настройка приложений .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c1cde-148">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [<span data-ttu-id="c1cde-149">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c1cde-149">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="c1cde-150">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="c1cde-150">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="c1cde-151">Перенаправление версий сборки</span><span class="sxs-lookup"><span data-stu-id="c1cde-151">Redirecting Assembly Versions</span></span>](../../../docs/framework/configure-apps/redirect-assembly-versions.md)
