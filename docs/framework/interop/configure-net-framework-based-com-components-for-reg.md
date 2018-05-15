---
title: Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации
ms.date: 03/30/2017
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 744ce1f2810eee025f071cafaa71e473b6ed4c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="9c81b-102">Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации</span><span class="sxs-lookup"><span data-stu-id="9c81b-102">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>
<span data-ttu-id="9c81b-103">Активация компонентов на основе платформы .NET Framework без регистрации осуществляется лишь немного сложнее, чем для COM-компонентов.</span><span class="sxs-lookup"><span data-stu-id="9c81b-103">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="9c81b-104">При установке требуются два манифеста:</span><span class="sxs-lookup"><span data-stu-id="9c81b-104">The setup requires two manifests:</span></span>  
  
-   <span data-ttu-id="9c81b-105">Для определения управляемого компонента в COM-приложениях используется манифест приложения в стиле Win32.</span><span class="sxs-lookup"><span data-stu-id="9c81b-105">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
-   <span data-ttu-id="9c81b-106">Компоненты на основе платформы .NET Framework используют манифест компонента для получения необходимых для активации сведений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9c81b-106">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="9c81b-107">В этом разделе описывается, как связать манифест приложения с приложением, манифест компонента с компонентом и внедрить манифест компонента в сборку.</span><span class="sxs-lookup"><span data-stu-id="9c81b-107">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
### <a name="to-create-an-application-manifest"></a><span data-ttu-id="9c81b-108">Создание манифеста приложения</span><span class="sxs-lookup"><span data-stu-id="9c81b-108">To create an application manifest</span></span>  
  
1.  <span data-ttu-id="9c81b-109">С помощью редактора XML создайте (или измените) манифест приложения, принадлежащий COM-приложению, которое взаимодействует с одним или несколькими управляемыми компонентами.</span><span class="sxs-lookup"><span data-stu-id="9c81b-109">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2.  <span data-ttu-id="9c81b-110">Вставьте следующий стандартный заголовок в начало файла:</span><span class="sxs-lookup"><span data-stu-id="9c81b-110">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     <span data-ttu-id="9c81b-111">Сведения об элементах манифеста и их атрибутов см. в разделе [манифесты приложения](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx).</span><span class="sxs-lookup"><span data-stu-id="9c81b-111">For information about manifest elements and their attributes, see [Application Manifests](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx).</span></span>  
  
3.  <span data-ttu-id="9c81b-112">Определите владельца манифеста.</span><span class="sxs-lookup"><span data-stu-id="9c81b-112">Identify the owner of the manifest.</span></span> <span data-ttu-id="9c81b-113">В следующем примере владельцем файла манифеста является `myComApp` версии 1.</span><span class="sxs-lookup"><span data-stu-id="9c81b-113">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  <span data-ttu-id="9c81b-114">Определите зависимые сборки.</span><span class="sxs-lookup"><span data-stu-id="9c81b-114">Identify dependent assemblies.</span></span> <span data-ttu-id="9c81b-115">В следующем примере `myComApp` зависит от `myManagedComp`.</span><span class="sxs-lookup"><span data-stu-id="9c81b-115">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="9c81b-116">Сохраните файл манифеста под соответствующим именем.</span><span class="sxs-lookup"><span data-stu-id="9c81b-116">Save and name the manifest file.</span></span> <span data-ttu-id="9c81b-117">Имя манифеста приложения состоит из имени исполняемого файла сборки и расширения manifest.</span><span class="sxs-lookup"><span data-stu-id="9c81b-117">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="9c81b-118">Например, для приложения myComApp.exe файл манифеста будет носить имя myComApp.exe.manifest.</span><span class="sxs-lookup"><span data-stu-id="9c81b-118">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
 <span data-ttu-id="9c81b-119">Манифест приложения можно установить в тот же каталог, что и COM-приложение.</span><span class="sxs-lookup"><span data-stu-id="9c81b-119">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="9c81b-120">Также его можно добавить в качестве ресурса в EXE-файл приложения.</span><span class="sxs-lookup"><span data-stu-id="9c81b-120">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="9c81b-121">За дополнительной информацией, Дополнительные сведения см. в разделе [о сборках Side-by-Side](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx).</span><span class="sxs-lookup"><span data-stu-id="9c81b-121">For additional information, For more information, see [About Side-by-Side Assemblies](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx).</span></span>  
  
#### <a name="to-create-a-component-manifest"></a><span data-ttu-id="9c81b-122">Создание манифеста компонента</span><span class="sxs-lookup"><span data-stu-id="9c81b-122">To create a component manifest</span></span>  
  
1.  <span data-ttu-id="9c81b-123">С помощью редактора XML создайте манифест компонента, описывающий управляемую сборку.</span><span class="sxs-lookup"><span data-stu-id="9c81b-123">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2.  <span data-ttu-id="9c81b-124">Вставьте следующий стандартный заголовок в начало файла:</span><span class="sxs-lookup"><span data-stu-id="9c81b-124">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  <span data-ttu-id="9c81b-125">Определите владельца файла.</span><span class="sxs-lookup"><span data-stu-id="9c81b-125">Identify the owner of the file.</span></span> <span data-ttu-id="9c81b-126">Элемент `<assemblyIdentity>` элемента `<dependentAssembly>` в файле манифеста приложения должен соответствовать аналогичному элементу в манифесте компонента.</span><span class="sxs-lookup"><span data-stu-id="9c81b-126">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="9c81b-127">В следующем примере владельцем файла манифеста является `myManagedComp` версии 1.2.3.4.</span><span class="sxs-lookup"><span data-stu-id="9c81b-127">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  <span data-ttu-id="9c81b-128">Определите каждый класс в сборке.</span><span class="sxs-lookup"><span data-stu-id="9c81b-128">Identify each class in the assembly.</span></span> <span data-ttu-id="9c81b-129">Используйте `<clrClass>` элемент для уникальной идентификации каждого класса в управляемой сборке.</span><span class="sxs-lookup"><span data-stu-id="9c81b-129">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="9c81b-130">Атрибуты элемента, вложенного в `<assembly>`, определены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9c81b-130">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="9c81b-131">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9c81b-131">Attribute</span></span>|<span data-ttu-id="9c81b-132">Описание</span><span class="sxs-lookup"><span data-stu-id="9c81b-132">Description</span></span>|<span data-ttu-id="9c81b-133">Обязательно</span><span class="sxs-lookup"><span data-stu-id="9c81b-133">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="9c81b-134">Идентификатор, который задает активируемый класс.</span><span class="sxs-lookup"><span data-stu-id="9c81b-134">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="9c81b-135">Да</span><span class="sxs-lookup"><span data-stu-id="9c81b-135">Yes</span></span>|  
    |`description`|<span data-ttu-id="9c81b-136">Строка, которая сообщает пользователю о компоненте.</span><span class="sxs-lookup"><span data-stu-id="9c81b-136">A string that informs the user about the component.</span></span> <span data-ttu-id="9c81b-137">По умолчанию используется пустая строка.</span><span class="sxs-lookup"><span data-stu-id="9c81b-137">An empty string is the default.</span></span>|<span data-ttu-id="9c81b-138">Нет</span><span class="sxs-lookup"><span data-stu-id="9c81b-138">No</span></span>|  
    |`name`|<span data-ttu-id="9c81b-139">Строка, представляющая управляемый класс.</span><span class="sxs-lookup"><span data-stu-id="9c81b-139">A string that represents the managed class.</span></span>|<span data-ttu-id="9c81b-140">Да</span><span class="sxs-lookup"><span data-stu-id="9c81b-140">Yes</span></span>|  
    |`progid`|<span data-ttu-id="9c81b-141">Идентификатор, который используется для отложенной активации.</span><span class="sxs-lookup"><span data-stu-id="9c81b-141">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="9c81b-142">Нет</span><span class="sxs-lookup"><span data-stu-id="9c81b-142">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="9c81b-143">Потоковая модель COM.</span><span class="sxs-lookup"><span data-stu-id="9c81b-143">The COM threading model.</span></span> <span data-ttu-id="9c81b-144">По умолчанию используется значение "Both" (Оба).</span><span class="sxs-lookup"><span data-stu-id="9c81b-144">"Both" is the default value.</span></span>|<span data-ttu-id="9c81b-145">Нет</span><span class="sxs-lookup"><span data-stu-id="9c81b-145">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="9c81b-146">Используемая версия среды CLR.</span><span class="sxs-lookup"><span data-stu-id="9c81b-146">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="9c81b-147">Если этот атрибут не задан, а среда CLR еще не загружена, компонент загружает последнюю установленную версию среды CLR, предшествующую версии 4.</span><span class="sxs-lookup"><span data-stu-id="9c81b-147">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="9c81b-148">Если указать v1.0.3705, v1.1.4322 или v2.0.50727, автоматически выполняется накат версии до последней установленной версии среды CLR, предшествующей версии 4 (как правило, v2.0.50727).</span><span class="sxs-lookup"><span data-stu-id="9c81b-148">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="9c81b-149">Если уже загружена другая версия среды CLR и не удается загрузить указанную версию в рамках параллельного процесса, загружается указанная версия. В противном случае используется загруженная версия CLR.</span><span class="sxs-lookup"><span data-stu-id="9c81b-149">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="9c81b-150">Это может привести к сбою загрузки.</span><span class="sxs-lookup"><span data-stu-id="9c81b-150">This might cause a load failure.</span></span>|<span data-ttu-id="9c81b-151">Нет</span><span class="sxs-lookup"><span data-stu-id="9c81b-151">No</span></span>|  
    |`tlbid`|<span data-ttu-id="9c81b-152">Идентификатор библиотеки типов, содержащей сведения о типе класса.</span><span class="sxs-lookup"><span data-stu-id="9c81b-152">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="9c81b-153">Нет</span><span class="sxs-lookup"><span data-stu-id="9c81b-153">No</span></span>|  
  
     <span data-ttu-id="9c81b-154">Во всех тегах атрибутов учитывается регистр символов.</span><span class="sxs-lookup"><span data-stu-id="9c81b-154">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="9c81b-155">Просматривая библиотеку типов, экспортированную для сборки с помощью средства ObjectViewer OLE/COM (Oleview.exe), можно получить идентификаторы классов (CLSID), программ (ProgID), потоковые модели и версию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="9c81b-155">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="9c81b-156">В следующем манифесте компонента определяются два класса: `testClass1` и `testClass2`.</span><span class="sxs-lookup"><span data-stu-id="9c81b-156">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"   
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="9c81b-157">Сохраните файл манифеста под соответствующим именем.</span><span class="sxs-lookup"><span data-stu-id="9c81b-157">Save and name the manifest file.</span></span> <span data-ttu-id="9c81b-158">Имя манифеста компонента состоит из имени библиотеки сборки и расширения manifest.</span><span class="sxs-lookup"><span data-stu-id="9c81b-158">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="9c81b-159">Например, манифест для myManagedComp.dll будет носить имя myManagedComp.manifest.</span><span class="sxs-lookup"><span data-stu-id="9c81b-159">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="9c81b-160">Манифест компонента необходимо внедрить в сборку в качестве ресурса.</span><span class="sxs-lookup"><span data-stu-id="9c81b-160">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="9c81b-161">Внедрение манифеста компонента в управляемую сборку</span><span class="sxs-lookup"><span data-stu-id="9c81b-161">To embed a component manifest in a managed assembly</span></span>  
  
1.  <span data-ttu-id="9c81b-162">Создайте скрипт ресурсов, содержащий следующую инструкцию:</span><span class="sxs-lookup"><span data-stu-id="9c81b-162">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="9c81b-163">В этой инструкции `myManagedComp.manifest` определяет имя внедряемого манифеста компонента.</span><span class="sxs-lookup"><span data-stu-id="9c81b-163">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="9c81b-164">В этом примере файл скрипта будет носить имя `myresource.rc`.</span><span class="sxs-lookup"><span data-stu-id="9c81b-164">For this example, the script file name is `myresource.rc`.</span></span>  
  
2.  <span data-ttu-id="9c81b-165">Скомпилируйте скрипт с помощью средства компиляции ресурсов Microsoft Windows (Rc.exe).</span><span class="sxs-lookup"><span data-stu-id="9c81b-165">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="9c81b-166">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9c81b-166">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="9c81b-167">Программа Rc.exe создает файл ресурсов `myresource.res`.</span><span class="sxs-lookup"><span data-stu-id="9c81b-167">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3.  <span data-ttu-id="9c81b-168">Снова скомпилируйте исходный файл сборки и укажите файл ресурсов с помощью параметра **/win32res**:</span><span class="sxs-lookup"><span data-stu-id="9c81b-168">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     <span data-ttu-id="9c81b-169">Файл, содержащий внедренный ресурс, также будет носить имя `myresource.res`.</span><span class="sxs-lookup"><span data-stu-id="9c81b-169">Again, `myresource.res` is the name of the resource file containing embedded resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c81b-170">См. также</span><span class="sxs-lookup"><span data-stu-id="9c81b-170">See Also</span></span>  
 [<span data-ttu-id="9c81b-171">COM-взаимодействие без регистрации</span><span class="sxs-lookup"><span data-stu-id="9c81b-171">Registration-Free COM Interop</span></span>](registration-free-com-interop.md)  
 <span data-ttu-id="9c81b-172">[Требования для регистрации COM-взаимодействия без](https://msdn.microsoft.com/library/0c43bc57-eecf-4e6c-8114-490141cce4da(v=vs.100)))</span><span class="sxs-lookup"><span data-stu-id="9c81b-172">[Requirements for Registration-Free COM Interop](https://msdn.microsoft.com/library/0c43bc57-eecf-4e6c-8114-490141cce4da(v=vs.100)))</span></span>  
 <span data-ttu-id="9c81b-173">[Настройка COM-компонентов для активации без регистрации](https://msdn.microsoft.com/library/bfe9b02f-d964-4784-960e-a1f94692fbfe(v=vs.100)))</span><span class="sxs-lookup"><span data-stu-id="9c81b-173">[Configuring COM Components for Registration-Free Activation](https://msdn.microsoft.com/library/bfe9b02f-d964-4784-960e-a1f94692fbfe(v=vs.100)))</span></span>  
 [<span data-ttu-id="9c81b-174">Пошаговое руководство. Активация компонентов на основе платформы .NET без регистрации</span><span class="sxs-lookup"><span data-stu-id="9c81b-174">Registration-Free Activation of .NET-Based Components: A Walkthrough</span></span>](https://msdn.microsoft.com/library/ms973915.aspx)
