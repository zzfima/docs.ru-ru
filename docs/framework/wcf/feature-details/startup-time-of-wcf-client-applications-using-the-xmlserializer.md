---
title: Практическое руководство. Сокращение времени запуска клиентских приложений WCF с использованием XmlSerializer
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: ca15d710a30586135f0d030e155b09b63a22ee45
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976060"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="b8a91-102">Практическое руководство. Сокращение времени запуска клиентских приложений WCF с использованием XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="b8a91-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="b8a91-103">Службы и клиентские приложения, использующие типы данных, сериализуемые с помощью сериализатора <xref:System.Xml.Serialization.XmlSerializer>, создают и компилируют код сериализации для этих типов данных во время выполнения, что может привести к снижению производительности при запуске.</span><span class="sxs-lookup"><span data-stu-id="b8a91-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8a91-104">Предварительно созданный код сериализации может использоваться только в клиентских приложениях, но не в службах.</span><span class="sxs-lookup"><span data-stu-id="b8a91-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="b8a91-105">[Средство служебной программы метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) может улучшить производительность при запуске этих приложений, создавая необходимый код сериализации из скомпилированных сборок для приложения.</span><span class="sxs-lookup"><span data-stu-id="b8a91-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="b8a91-106">Svcutil.exe создает код сериализации для всех типов данных, используемых в контрактах служб в скомпилированной сборке приложения, которые могут быть сериализованы с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b8a91-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="b8a91-107">Контракты служб и операций, предусматривающие использование <xref:System.Xml.Serialization.XmlSerializer>, отмечены атрибутом <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8a91-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="b8a91-108">Создание кода сериализации XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="b8a91-108">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="b8a91-109">Скомпилируйте код службы или клиента в одну или несколько сборок.</span><span class="sxs-lookup"><span data-stu-id="b8a91-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="b8a91-110">Откройте окно командной строки SDK.</span><span class="sxs-lookup"><span data-stu-id="b8a91-110">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="b8a91-111">Из командной строки запустите средство Svcutil.exe, используя следующий формат.</span><span class="sxs-lookup"><span data-stu-id="b8a91-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="b8a91-112">Аргумент `assemblyPath` задает путь к сборке, содержащей типы из контракта службы.</span><span class="sxs-lookup"><span data-stu-id="b8a91-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="b8a91-113">Svcutil.exe создает код сериализации для всех типов данных, используемых в контрактах служб в скомпилированной сборке приложения, которые могут быть сериализованы с помощью <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="b8a91-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="b8a91-114">Svcutil.exe может формировать только код сериализации на C#.</span><span class="sxs-lookup"><span data-stu-id="b8a91-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="b8a91-115">Для каждой входной сборки создается один файл исходного кода.</span><span class="sxs-lookup"><span data-stu-id="b8a91-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="b8a91-116">Нельзя использовать параметр **/Language** для изменения языка созданного кода.</span><span class="sxs-lookup"><span data-stu-id="b8a91-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="b8a91-117">Чтобы указать путь к зависимым сборкам, используйте параметр **/Reference** .</span><span class="sxs-lookup"><span data-stu-id="b8a91-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="b8a91-118">Предоставьте приложению доступ к созданному коду сериализации одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="b8a91-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1. <span data-ttu-id="b8a91-119">Скомпилируйте созданный код сериализации в отдельную сборку с именем [*Исходная сборка*]. XmlSerializer. dll (например, MyApp. XmlSerializers. dll).</span><span class="sxs-lookup"><span data-stu-id="b8a91-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="b8a91-120">Приложение должно иметь возможность загрузить эту сборку, которая должна быть подписана с помощью того же ключа, что и исходная сборка.</span><span class="sxs-lookup"><span data-stu-id="b8a91-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="b8a91-121">В случае повторной компиляции исходной сборки необходимо заново создать сборку сериализации.</span><span class="sxs-lookup"><span data-stu-id="b8a91-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2. <span data-ttu-id="b8a91-122">Скомпилируйте созданный код сериализации в отдельную сборку и используйте атрибут <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> в контракте службы, в котором используется атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8a91-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="b8a91-123">Задайте свойство <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> или <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> так, чтобы оно указывало на скомпилированную сборку сериализации.</span><span class="sxs-lookup"><span data-stu-id="b8a91-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3. <span data-ttu-id="b8a91-124">Скомпилируйте созданный код сериализации в сборку приложения и добавьте атрибут <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> в контракт службы, в котором используется атрибут <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8a91-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="b8a91-125">Не задавайте свойства <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> или <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>.</span><span class="sxs-lookup"><span data-stu-id="b8a91-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="b8a91-126">По умолчанию предполагается, что сборка сериализации по умолчанию является текущей сборкой.</span><span class="sxs-lookup"><span data-stu-id="b8a91-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="b8a91-127">Создание кода сериализации XmlSerializer в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b8a91-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="b8a91-128">Создание проектов службы и клиента WCF в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8a91-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="b8a91-129">Затем добавьте ссылку на службу в клиентский проект.</span><span class="sxs-lookup"><span data-stu-id="b8a91-129">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="b8a91-130">Добавьте <xref:System.ServiceModel.XmlSerializerFormatAttribute> в контракт службы в файле *Reference.CS* в проекте клиентского приложения в разделе **укзать** -> **Reference. svcmap**.</span><span class="sxs-lookup"><span data-stu-id="b8a91-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="b8a91-131">Обратите внимание, что для просмотра этих файлов необходимо показать все файлы в **Обозреватель решений** .</span><span class="sxs-lookup"><span data-stu-id="b8a91-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="b8a91-132">Создайте клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="b8a91-132">Build the client app.</span></span>  
  
4. <span data-ttu-id="b8a91-133">Используйте [средство служебной программы для метаданных ServiceModel (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать предварительно созданный файл сериализатора *. CS* с помощью команды:</span><span class="sxs-lookup"><span data-stu-id="b8a91-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="b8a91-134">Аргумент _ указывает путь к клиентской сборке WCF.</span><span class="sxs-lookup"><span data-stu-id="b8a91-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="b8a91-135">Например:</span><span class="sxs-lookup"><span data-stu-id="b8a91-135">Such as:</span></span>  
  
    ```console  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="b8a91-136">Будет создан файл *WCFClient.XmlSerializers.dll.CS* .</span><span class="sxs-lookup"><span data-stu-id="b8a91-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="b8a91-137">Скомпилируйте предварительно созданную сборку сериализации.</span><span class="sxs-lookup"><span data-stu-id="b8a91-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="b8a91-138">В зависимости от примера, приведенного на предыдущем шаге, команда Compile будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b8a91-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```console  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="b8a91-139">Убедитесь, что созданная *вкфклиент. XmlSerializer. dll* находится в том же каталоге, что и клиентское приложение, которое в данном случае является *вкфклиент. exe* .</span><span class="sxs-lookup"><span data-stu-id="b8a91-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="b8a91-140">Запустите клиентское приложение обычным образом.</span><span class="sxs-lookup"><span data-stu-id="b8a91-140">Run the client app as usual.</span></span> <span data-ttu-id="b8a91-141">Будет использоваться предварительно созданная сборка сериализации.</span><span class="sxs-lookup"><span data-stu-id="b8a91-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8a91-142">Пример</span><span class="sxs-lookup"><span data-stu-id="b8a91-142">Example</span></span>  
 <span data-ttu-id="b8a91-143">Следующая команда создает типы сериализации для типов `XmlSerializer`, используемых любыми контрактами служб в сборке.</span><span class="sxs-lookup"><span data-stu-id="b8a91-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```console  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8a91-144">См. также</span><span class="sxs-lookup"><span data-stu-id="b8a91-144">See also</span></span>

- [<span data-ttu-id="b8a91-145">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="b8a91-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
