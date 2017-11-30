---
title: "-win32manifest (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /win32manifest
helpviewer_keywords:
- /win32manifest compiler option [C#]
- win32manifest compiler option [C#]
- -win32manifest compiler option [C#]
ms.assetid: 9460ea1b-6c9f-44b8-8f73-301b30a01de1
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 40b1fa1f9aa465a56eccaf5fff5cf7bb59144e85
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="win32manifest-c-compiler-options"></a><span data-ttu-id="6fc14-102">/win32manifest (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="6fc14-102">/win32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="6fc14-103">Параметр **/win32manifest** позволяет указать пользовательский файл манифеста приложения win32manifest для внедрения в переносимый исполняемый файл проекта (PE-файл).</span><span class="sxs-lookup"><span data-stu-id="6fc14-103">Use the **/win32manifest** option to specify a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fc14-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fc14-104">Syntax</span></span>  
  
```console  
/win32manifest: filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="6fc14-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="6fc14-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="6fc14-106">Имя и расположение пользовательского файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="6fc14-106">The name and location of the custom manifest file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fc14-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="6fc14-107">Remarks</span></span>  
 <span data-ttu-id="6fc14-108">По умолчанию компилятор [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] внедряет манифест приложения, определяющий запрошенный уровень выполнения "asInvoker".</span><span class="sxs-lookup"><span data-stu-id="6fc14-108">By default, the [!INCLUDE[csharp_current_short](~/includes/csharp-current-short-md.md)] compiler embeds an application manifest that specifies a requested execution level of "asInvoker."</span></span> <span data-ttu-id="6fc14-109">Он создает манифест в той же папке, в которой создан исполняемый файл, обычно в папке bin\Debug или bin\Release при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6fc14-109">It creates the manifest in the same folder in which the executable is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="6fc14-110">Если необходимо предоставить пользовательский манифест, например, чтобы задать уровень выполнения highestAvailable or requireAdministrator, используйте этот параметр, чтобы указать имя файла.</span><span class="sxs-lookup"><span data-stu-id="6fc14-110">If you want to supply a custom manifest, for example to specify a requested execution level of "highestAvailable" or "requireAdministrator," use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fc14-111">Этот параметр и параметр [/win32res (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="6fc14-111">This option and the [/win32res (C# Compiler Options)](../../../csharp/language-reference/compiler-options/win32res-compiler-option.md) option are mutually exclusive.</span></span> <span data-ttu-id="6fc14-112">При попытке использовать оба параметра в одной командной строке возникнет ошибка построения.</span><span class="sxs-lookup"><span data-stu-id="6fc14-112">If you try to use both options in the same command line you will get a build error.</span></span>  
  
 <span data-ttu-id="6fc14-113">Приложение, имеющее без манифеста приложения, который указывает запрошенный уровень выполнения будет зависеть от виртуализации файлов и реестра с возможностью контроль учетных записей пользователей в Windows.</span><span class="sxs-lookup"><span data-stu-id="6fc14-113">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows.</span></span> <span data-ttu-id="6fc14-114">Дополнительные сведения см. в разделе [контроль учетных записей пользователей](/windows/access-protection/user-account-control/user-account-control-overview).</span><span class="sxs-lookup"><span data-stu-id="6fc14-114">For more information, see [User Account Control](/windows/access-protection/user-account-control/user-account-control-overview).</span></span>  
  
 <span data-ttu-id="6fc14-115">Приложение требует виртуализации в любом из следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="6fc14-115">Your application will be subject to virtualization if either of these conditions is true:</span></span>  
  
-   <span data-ttu-id="6fc14-116">Вы используете параметр **/nowin32manifest** и не предоставляете манифест на более позднем этапе сборки или в файле ресурсов Windows (RES-файла) с помощью параметра **/win32res**.</span><span class="sxs-lookup"><span data-stu-id="6fc14-116">You use the **/nowin32manifest** option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the **/win32res** option.</span></span>  
  
-   <span data-ttu-id="6fc14-117">Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.</span><span class="sxs-lookup"><span data-stu-id="6fc14-117">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="6fc14-118"> создает стандартный файл с расширением MANIFEST и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="6fc14-118"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="6fc14-119">Пользовательский манифест можно добавить, создав его в любом текстовом редакторе и добавив полученный файл в проект.</span><span class="sxs-lookup"><span data-stu-id="6fc14-119">You can add a custom manifest by creating one in any text editor and then adding the file to the project.</span></span> <span data-ttu-id="6fc14-120">Кроме того, можно щелкнуть значок **проект** в **обозревателе решений** и нажать кнопку **Добавить новый элемент**, а затем **Файл манифеста приложения**.</span><span class="sxs-lookup"><span data-stu-id="6fc14-120">Alternatively, you can right-click the **Project** icon in **Solution Explorer**, click **Add New Item**, and then click **Application Manifest File**.</span></span> <span data-ttu-id="6fc14-121">Добавленный новый или существующий файл манифеста появится в раскрывающемся списке **Манифест**.</span><span class="sxs-lookup"><span data-stu-id="6fc14-121">After you have added your new or existing manifest file, it will appear in the **Manifest** drop down list.</span></span> <span data-ttu-id="6fc14-122">Дополнительные сведения см. в разделе [Страница "Приложение" в конструкторе проектов (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="6fc14-122">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="6fc14-123">Манифест приложения можно предоставить во время пользовательского действия, выполняемого после сборки, или в составе файла ресурсов Win32 с помощью параметра [/nowin32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6fc14-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the [/nowin32manifest (C# Compiler Options)](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md) option.</span></span> <span data-ttu-id="6fc14-124">Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="6fc14-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="6fc14-125">В этом случае компилятор не будет создавать и внедрять манифест по умолчанию в переносимый исполняемый файл (PE).</span><span class="sxs-lookup"><span data-stu-id="6fc14-125">This will prevent the compiler from creating and embedding a default manifest in the portable executable (PE) file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fc14-126">Пример</span><span class="sxs-lookup"><span data-stu-id="6fc14-126">Example</span></span>  
 <span data-ttu-id="6fc14-127">В приведенном ниже примере показан манифест по умолчанию, который компилятор Visual C# вставляет в PE.</span><span class="sxs-lookup"><span data-stu-id="6fc14-127">The following example shows the default manifest that the Visual C# compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fc14-128">Компилятор вставляет в XML-код имя стандартного приложения, "MyApplication.app".</span><span class="sxs-lookup"><span data-stu-id="6fc14-128">The compiler inserts a standard application name " MyApplication.app " into the xml.</span></span> <span data-ttu-id="6fc14-129">Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.</span><span class="sxs-lookup"><span data-stu-id="6fc14-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" standalone="yes"?>  
<assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
  <assemblyIdentity version="1.0.0.0" name="MyApplication.app"/>  
  <trustInfo xmlns="urn:schemas-microsoft-com:asm.v2">  
    <security>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <requestedExecutionLevel level="asInvoker"/>  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
</assembly>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6fc14-130">См. также</span><span class="sxs-lookup"><span data-stu-id="6fc14-130">See Also</span></span>  
 [<span data-ttu-id="6fc14-131">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="6fc14-131">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="6fc14-132">/ nowin32manifest (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="6fc14-132">/nowin32manifest (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/nowin32manifest-compiler-option.md)  
 [<span data-ttu-id="6fc14-133">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="6fc14-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
