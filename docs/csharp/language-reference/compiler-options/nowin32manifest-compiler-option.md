---
title: -nowin32manifest (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /nowin32manifest
helpviewer_keywords:
- nowin32manifest compiler option [C#]
- -nowin32manifest compiler option [C#]
- /nowin32manifest compiler option [C#]
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
ms.openlocfilehash: 8820410bfdbce2f9986605f37af4d14957471126
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602716"
---
# <a name="-nowin32manifest-c-compiler-options"></a><span data-ttu-id="c179b-102">-nowin32manifest (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="c179b-102">-nowin32manifest (C# Compiler Options)</span></span>
<span data-ttu-id="c179b-103">С помощью параметра **-nowin32manifest** можно указать компилятору не внедрять манифест приложения в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="c179b-103">Use the **-nowin32manifest** option to instruct the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c179b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c179b-104">Syntax</span></span>  
  
```console  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="c179b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="c179b-105">Remarks</span></span>  
 <span data-ttu-id="c179b-106">При использовании этого параметра приложение будет подлежать виртуализации в Windows Vista, если манифест приложения не будет предоставлен в файле ресурсов Win32 или на более поздних этапах сборки.</span><span class="sxs-lookup"><span data-stu-id="c179b-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span>  
  
 <span data-ttu-id="c179b-107">В Visual Studio этот параметр можно задать на странице **Свойство приложения**, выбрав в раскрывающемся списке **Манифест** пункт **Создать приложение без манифеста**.</span><span class="sxs-lookup"><span data-stu-id="c179b-107">In Visual Studio, set this option in the **Application Property** page by selecting the **Create Application Without a Manifest** option in the **Manifest** drop down list.</span></span> <span data-ttu-id="c179b-108">Дополнительные сведения см. в разделе [Страница "Приложение" в конструкторе проектов (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="c179b-108">For more information, see [Application Page, Project Designer (C#)](/visualstudio/ide/reference/application-page-project-designer-csharp).</span></span>  
  
 <span data-ttu-id="c179b-109">Дополнительные сведения о создании манифестов см. в разделе [-win32manifest (параметры компилятора C#)](./win32manifest-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c179b-109">For more information about manifest creation, see [-win32manifest (C# Compiler Options)](./win32manifest-compiler-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c179b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c179b-110">See also</span></span>

- [<span data-ttu-id="c179b-111">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="c179b-111">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c179b-112">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="c179b-112">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
