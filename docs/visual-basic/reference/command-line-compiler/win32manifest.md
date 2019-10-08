---
title: -win32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
ms.openlocfilehash: cae6b34aadf6698a337e52aa1ea1ce44206836ac
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004623"
---
# <a name="-win32manifest-visual-basic"></a><span data-ttu-id="d04a4-102">-win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d04a4-102">-win32manifest (Visual Basic)</span></span>
<span data-ttu-id="d04a4-103">Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).</span><span class="sxs-lookup"><span data-stu-id="d04a4-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d04a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d04a4-104">Syntax</span></span>  
  
```console  
-win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="d04a4-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d04a4-105">Arguments</span></span>  
  
|<span data-ttu-id="d04a4-106">Термин</span><span class="sxs-lookup"><span data-stu-id="d04a4-106">Term</span></span>|<span data-ttu-id="d04a4-107">Определение</span><span class="sxs-lookup"><span data-stu-id="d04a4-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="d04a4-108">Путь к файлу пользовательского манифеста.</span><span class="sxs-lookup"><span data-stu-id="d04a4-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d04a4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d04a4-109">Remarks</span></span>  
 <span data-ttu-id="d04a4-110">По умолчанию компилятор Visual Basic внедряет манифест приложения, указывающий требуемый уровень выполнения asInvoker.</span><span class="sxs-lookup"><span data-stu-id="d04a4-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="d04a4-111">Он создает манифест в той же папке, в которой создается исполняемый файл, обычно в папке bin\Debug или bin\Release при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d04a4-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="d04a4-112">Если вы хотите предоставить пользовательский манифест, например для указания требуемого уровня выполнения highestAvailable или requireAdministrator, используйте этот параметр, чтобы указать имя файла.</span><span class="sxs-lookup"><span data-stu-id="d04a4-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d04a4-113">Этот параметр и параметр [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="d04a4-113">This option and the [-win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="d04a4-114">При попытке использовать оба параметра в одной командной строке возникнет ошибка сборки.</span><span class="sxs-lookup"><span data-stu-id="d04a4-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="d04a4-115">Приложение без манифеста, определяющего запрошенный уровень выполнения, требует виртуализации файлов или реестра с помощью функции "Контроль учетных записей" в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="d04a4-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="d04a4-116">Дополнительные сведения о виртуализации см. в статье [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista) (Развертывание ClickOnce в Windows Vista).</span><span class="sxs-lookup"><span data-stu-id="d04a4-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="d04a4-117">Приложение будет подвергаться виртуализации, если выполняется одно из следующих условий.</span><span class="sxs-lookup"><span data-stu-id="d04a4-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1. <span data-ttu-id="d04a4-118">Вы используете параметр `-nowin32manifest` и не предоставляете манифест на более позднем этапе сборки или в составе файла ресурсов Windows (RES-файл) с помощью параметра `-win32resource`.</span><span class="sxs-lookup"><span data-stu-id="d04a4-118">You use the `-nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `-win32resource` option.</span></span>  
  
2. <span data-ttu-id="d04a4-119">Вы предоставляете пользовательский манифест, не определяющий запрошенный уровень выполнения.</span><span class="sxs-lookup"><span data-stu-id="d04a4-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 <span data-ttu-id="d04a4-120">Visual Studio создает файл по умолчанию с расширением .manifest и сохраняет его в каталоги отладки и выпуска вместе с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="d04a4-120">Visual Studio creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="d04a4-121">Можно просмотреть или изменить файл App. manifest по умолчанию, щелкнув **Просмотреть параметры UAC** на вкладке **приложение** в конструкторе проектов.</span><span class="sxs-lookup"><span data-stu-id="d04a4-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="d04a4-122">Дополнительные сведения см. в разделе [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d04a4-122">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="d04a4-123">Манифест приложения можно предоставить в качестве настраиваемого этапа, выполняемого после сборки, или как часть файла ресурсов Win32 с помощью параметра `-nowin32manifest`.</span><span class="sxs-lookup"><span data-stu-id="d04a4-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `-nowin32manifest` option.</span></span> <span data-ttu-id="d04a4-124">Этот же параметр можно использовать, если вы хотите, чтобы ваше приложение требовало виртуализации файлов или реестров в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="d04a4-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="d04a4-125">Это позволит компилятору не создавать и внедрять манифест по умолчанию в PE-файле.</span><span class="sxs-lookup"><span data-stu-id="d04a4-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d04a4-126">Пример</span><span class="sxs-lookup"><span data-stu-id="d04a4-126">Example</span></span>  
 <span data-ttu-id="d04a4-127">В следующем примере показан манифест по умолчанию, который Visual Basic компилятор вставляет в PE.</span><span class="sxs-lookup"><span data-stu-id="d04a4-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d04a4-128">Компилятор вставляет имя стандартного приложения MyApplication. app в XML-файл манифеста.</span><span class="sxs-lookup"><span data-stu-id="d04a4-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="d04a4-129">Это позволяет приложениям работать в Windows Server 2003 с пакетом обновления 3.</span><span class="sxs-lookup"><span data-stu-id="d04a4-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d04a4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d04a4-130">See also</span></span>

- [<span data-ttu-id="d04a4-131">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d04a4-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d04a4-132">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d04a4-132">-nowin32manifest (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)
