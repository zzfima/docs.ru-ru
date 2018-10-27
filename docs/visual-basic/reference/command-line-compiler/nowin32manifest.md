---
title: -nowin32manifest (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
ms.openlocfilehash: 382e8fd089211f6d23a1e6baff93bf08f19248c8
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50035765"
---
# <a name="-nowin32manifest-visual-basic"></a><span data-ttu-id="8ee93-102">-nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ee93-102">-nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="8ee93-103">Указывает компилятору не внедрять манифест приложения в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="8ee93-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ee93-104">Syntax</span></span>  
  
```  
-nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ee93-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ee93-105">Remarks</span></span>  
 <span data-ttu-id="8ee93-106">При использовании этого параметра приложение будет подлежать виртуализации в Windows Vista, если манифест приложения не будет предоставлен в файле ресурсов Win32 или на более поздних этапах сборки.</span><span class="sxs-lookup"><span data-stu-id="8ee93-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="8ee93-107">Дополнительные сведения о виртуализации см. в разделе [развертывание ClickOnce в Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="8ee93-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="8ee93-108">Дополнительные сведения о создании манифестов см. в разделе [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span><span class="sxs-lookup"><span data-stu-id="8ee93-108">For more information about manifest creation, see [-win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee93-109">См. также</span><span class="sxs-lookup"><span data-stu-id="8ee93-109">See Also</span></span>  
 [<span data-ttu-id="8ee93-110">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="8ee93-110">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="8ee93-111">Страница "Приложение" в конструкторе проектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ee93-111">Application Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/application-page-project-designer-visual-basic)
