---
title: "/ win32manifest (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /win32manifest compiler option [Visual Basic]
- win32manifest compiler option [Visual Basic]
- -win32manifest compiler option [Visual Basic]
ms.assetid: 9e3191b4-90db-41c8-966a-28036fd20005
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4a9693bd7eb03dee5a2a9f2d43360b963e9fd876
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="win32manifest-visual-basic"></a><span data-ttu-id="fd11a-102">/win32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd11a-102">/win32manifest (Visual Basic)</span></span>
<span data-ttu-id="fd11a-103">Определяет пользовательский файл манифеста приложения Win32 для внедрения в переносимый исполняемый файл проекта (PE-файл).</span><span class="sxs-lookup"><span data-stu-id="fd11a-103">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd11a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd11a-104">Syntax</span></span>  
  
```  
/win32manifest: fileName  
```  
  
## <a name="arguments"></a><span data-ttu-id="fd11a-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="fd11a-105">Arguments</span></span>  
  
|<span data-ttu-id="fd11a-106">Термин</span><span class="sxs-lookup"><span data-stu-id="fd11a-106">Term</span></span>|<span data-ttu-id="fd11a-107">Определение</span><span class="sxs-lookup"><span data-stu-id="fd11a-107">Definition</span></span>|  
|---|---|  
|`fileName`|<span data-ttu-id="fd11a-108">Путь пользовательского файла манифеста.</span><span class="sxs-lookup"><span data-stu-id="fd11a-108">The path of the custom manifest file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd11a-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd11a-109">Remarks</span></span>  
 <span data-ttu-id="fd11a-110">По умолчанию компилятор Visual Basic внедряет манифест приложения, который указывает запрошенный уровень asInvoker.</span><span class="sxs-lookup"><span data-stu-id="fd11a-110">By default, the Visual Basic compiler embeds an application manifest that specifies a requested execution level of asInvoker.</span></span> <span data-ttu-id="fd11a-111">Он создает манифест в той же папке, в которой построена исполняемый файл, обычно папке bin\Debug или bin\Release при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fd11a-111">It creates the manifest in the same folder in which the executable file is built, typically the bin\Debug or bin\Release folder when you use Visual Studio.</span></span> <span data-ttu-id="fd11a-112">Если необходимо предоставить пользовательский манифест, например для указания запрошенный уровень выполнения highestAvailable или requireAdministrator, используйте этот параметр для указания имени файла.</span><span class="sxs-lookup"><span data-stu-id="fd11a-112">If you want to supply a custom manifest, for example to specify a requested execution level of highestAvailable or requireAdministrator, use this option to specify the name of the file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd11a-113">Этот параметр и [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) параметр являются взаимоисключающими.</span><span class="sxs-lookup"><span data-stu-id="fd11a-113">This option and the [/win32resource](../../../visual-basic/reference/command-line-compiler/win32resource.md) option are mutually exclusive.</span></span> <span data-ttu-id="fd11a-114">При попытке использовать оба параметра в одной командной строке, вы получите ошибку построения.</span><span class="sxs-lookup"><span data-stu-id="fd11a-114">If you try to use both options in the same command line, you will get a build error.</span></span>  
  
 <span data-ttu-id="fd11a-115">Приложение, имеющее без манифеста приложения, который указывает запрошенный уровень выполнения будут применяться виртуализация файлов и реестра в разделе функции контроля учетных записей в Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="fd11a-115">An application that has no application manifest that specifies a requested execution level will be subject to file/registry virtualization under the User Account Control feature in Windows Vista.</span></span> <span data-ttu-id="fd11a-116">Дополнительные сведения о виртуализации см. в разделе [развертывание ClickOnce в Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="fd11a-116">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="fd11a-117">Приложение подлежит виртуализации, если выполняется любое из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="fd11a-117">Your application will be subject to virtualization if either of the following conditions is true:</span></span>  
  
1.  <span data-ttu-id="fd11a-118">Использовать `/nowin32manifest` вариант и не предоставляется манифест на более позднем этапе построения или в составе файла ресурсов Windows (RES-файл) с помощью `/win32resource` параметр.</span><span class="sxs-lookup"><span data-stu-id="fd11a-118">You use the `/nowin32manifest` option and you do not provide a manifest in a later build step or as part of a Windows Resource (.res) file by using the `/win32resource` option.</span></span>  
  
2.  <span data-ttu-id="fd11a-119">Необходимо предоставить пользовательский манифест, который не указывает запрошенный уровень выполнения.</span><span class="sxs-lookup"><span data-stu-id="fd11a-119">You provide a custom manifest that does not specify a requested execution level.</span></span>  
  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="fd11a-120">Создает стандартный файл манифеста и сохраняет его в каталоге отладки и выпуска наряду с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="fd11a-120"> creates a default .manifest file and stores it in the debug and release directories alongside the executable file.</span></span> <span data-ttu-id="fd11a-121">Можно просмотреть или изменить стандартный файл app.manifest, щелкнув **просмотреть параметры контроля учетных Записей** на **приложения** в конструкторе проектов.</span><span class="sxs-lookup"><span data-stu-id="fd11a-121">You can view or edit the default app.manifest file by clicking **View UAC Settings** on the **Application** tab in the Project Designer.</span></span> <span data-ttu-id="fd11a-122">Дополнительные сведения см. в разделе [страница "приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fd11a-122">For more information, see [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="fd11a-123">Можно предоставить манифест приложения как пользовательское действие после построения, или как часть файла ресурсов Win32 с помощью `/nowin32manifest` параметр.</span><span class="sxs-lookup"><span data-stu-id="fd11a-123">You can provide the application manifest as a custom post-build step or as part of a Win32 resource file by using the `/nowin32manifest` option.</span></span> <span data-ttu-id="fd11a-124">Используйте этот же параметр, если требуется возможность виртуализации файлов или реестра на Windows Vista приложения.</span><span class="sxs-lookup"><span data-stu-id="fd11a-124">Use that same option if you want your application to be subject to file or registry virtualization on Windows Vista.</span></span> <span data-ttu-id="fd11a-125">Это помешает компилятору создать и внедрить манифест по умолчанию в PE-файле.</span><span class="sxs-lookup"><span data-stu-id="fd11a-125">This will prevent the compiler from creating and embedding a default manifest in the PE file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd11a-126">Пример</span><span class="sxs-lookup"><span data-stu-id="fd11a-126">Example</span></span>  
 <span data-ttu-id="fd11a-127">Следующий пример показывает манифест по умолчанию, компилятор Visual Basic вставляет в PE-ФАЙЛ.</span><span class="sxs-lookup"><span data-stu-id="fd11a-127">The following example shows the default manifest that the Visual Basic compiler inserts into a PE.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd11a-128">Компилятор вставляет имя стандартного приложения MyApplication.app в манифест XML.</span><span class="sxs-lookup"><span data-stu-id="fd11a-128">The compiler inserts a standard application name MyApplication.app into the manifest XML.</span></span> <span data-ttu-id="fd11a-129">Это делается для того, чтобы позволить приложениям работать в Windows Server 2003 с пакетом обновления 3.</span><span class="sxs-lookup"><span data-stu-id="fd11a-129">This is a workaround to enable applications to run on Windows Server 2003 Service Pack 3.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="fd11a-130">См. также</span><span class="sxs-lookup"><span data-stu-id="fd11a-130">See Also</span></span>  
 <span data-ttu-id="fd11a-131">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fd11a-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fd11a-132"> [/ nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span><span class="sxs-lookup"><span data-stu-id="fd11a-132"> [/nowin32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)</span></span>
