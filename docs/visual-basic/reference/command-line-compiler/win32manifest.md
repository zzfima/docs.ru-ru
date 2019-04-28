---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: 15fe62457ed11ffcd08a1db3aa8be57080f22869
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774781"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="b20ea-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b20ea-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="b20ea-103">Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).</span><span class="sxs-lookup"><span data-stu-id="b20ea-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b20ea-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b20ea-104">Syntax</span></span>  
  
```  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="b20ea-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b20ea-105">Arguments</span></span>  
  
|<span data-ttu-id="b20ea-106">Термин</span><span class="sxs-lookup"><span data-stu-id="b20ea-106">Term</span></span>|<span data-ttu-id="b20ea-107">Определение</span><span class="sxs-lookup"><span data-stu-id="b20ea-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="b20ea-108">Путь к пользовательский файл манифеста.</span><span class="sxs-lookup"><span data-stu-id="b20ea-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b20ea-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b20ea-109">Remarks</span></span>  
 <span data-ttu-id="b20ea-110">По умолчанию компилятор Visual Basic внедряет манифест приложения, определяющий запрошенный уровень выполнения asInvoker.</span><span class="sxs-lookup"><span data-stu-id="b20ea-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="b20ea-111">Он создает манифест в той же папке, в котором создается исполняемый файл, обычно в папку bin\Debug или bin\Release при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b20ea-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="b20ea-112">Если вы хотите предоставить пользовательский манифест, например указать запрошенный уровень выполнения highestAvailable и requireAdministrator, используйте этот параметр для указания имени файла.</span><span class="sxs-lookup"><span data-stu-id="b20ea-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b20ea-113">Этот параметр и [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="b20ea-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="b20ea-114">При попытке использовать оба параметра в одной командной строке, вы получите ошибку построения.</span><span class="sxs-lookup"><span data-stu-id="b20ea-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="b20ea-115">Приложение без манифеста, определяющего запрошенный уровень выполнения, требует виртуализации файлов или реестра с помощью функции "Контроль учетных записей" в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="b20ea-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="b20ea-116">Дополнительные сведения о виртуализации см. в статье [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista) (Развертывание ClickOnce в Windows Vista).</span><span class="sxs-lookup"><span data-stu-id="b20ea-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="b20ea-117">Приложение будет подлежать виртуализации, если выполняется любое из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="b20ea-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="b20ea-118">Использовании `-nowin32manifest` и не предоставляете манифест на более позднем этапе сборки или как часть файла ресурсов Windows (RES-файл) с помощью `-win32resource` параметр.</span><span class="sxs-lookup"><span data-stu-id="b20ea-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="b20ea-119">Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.</span><span class="sxs-lookup"><span data-stu-id="b20ea-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="b20ea-120">Visual Studio создает файл по умолчанию с расширением .manifest и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="b20ea-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="b20ea-121">Можно просмотреть или изменить файл app.manifest по умолчанию, нажав кнопку **параметров контроля учетных Записей представление** на **приложения** вкладки конструктора проектов.</span><span class="sxs-lookup"><span data-stu-id="b20ea-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="b20ea-122">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b20ea-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="b20ea-123">Можно предоставить манифест приложения в качестве пользовательского шага после сборки или в составе файла ресурсов Win32 с помощью `-nowin32manifest` параметр.</span><span class="sxs-lookup"><span data-stu-id="b20ea-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="b20ea-124">Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="b20ea-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="b20ea-125">Это предотвратит компилятор создавать и внедрять манифест по умолчанию в PE-файла.</span><span class="sxs-lookup"><span data-stu-id="b20ea-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20ea-126">Пример</span><span class="sxs-lookup"><span data-stu-id="b20ea-126">Example</span></span>  
 <span data-ttu-id="b20ea-127">Следующий пример показывает манифест по умолчанию, что компилятор Visual Basic вставляет в PE-ФАЙЛ.</span><span class="sxs-lookup"><span data-stu-id="b20ea-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b20ea-128">Компилятор вставляет код имя стандартного приложения MyApplication.app в манифест XML.</span><span class="sxs-lookup"><span data-stu-id="b20ea-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="b20ea-129">Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.</span><span class="sxs-lookup"><span data-stu-id="b20ea-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b20ea-130">См. также</span><span class="sxs-lookup"><span data-stu-id="b20ea-130">See also</span></span>

- [<span data-ttu-id="b20ea-131">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="b20ea-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="b20ea-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b20ea-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
