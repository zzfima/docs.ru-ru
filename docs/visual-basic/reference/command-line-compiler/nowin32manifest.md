---
title: "/ nowin32manifest (Visual Basic) | Документы Microsoft"
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
- /nowin32manifest compiler option [Visual Basic]
- nowin32manifest compiler option [Visual Basic]
- -nowin32manifest compiler option [Visual Basic]
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: 7
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
ms.openlocfilehash: 975711c9ee2e56b3c3c33611dd56eb6dc6082471
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="nowin32manifest-visual-basic"></a><span data-ttu-id="68851-102">/nowin32manifest (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68851-102">/nowin32manifest (Visual Basic)</span></span>
<span data-ttu-id="68851-103">Указывает компилятору не внедрять манифест приложения в исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="68851-103">Instructs the compiler not to embed any application manifest into the executable file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68851-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68851-104">Syntax</span></span>  
  
```  
/nowin32manifest  
```  
  
## <a name="remarks"></a><span data-ttu-id="68851-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="68851-105">Remarks</span></span>  
 <span data-ttu-id="68851-106">Когда этот параметр используется, приложение будет виртуализации в Windows Vista, если не предоставить манифест приложения в файле ресурсов Win32 или на более поздних этапах построения.</span><span class="sxs-lookup"><span data-stu-id="68851-106">When this option is used, the application will be subject to virtualization on Windows Vista unless you provide an application manifest in a Win32 Resource file or during a later build step.</span></span> <span data-ttu-id="68851-107">Дополнительные сведения о виртуализации см. в разделе [развертывание ClickOnce в Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span><span class="sxs-lookup"><span data-stu-id="68851-107">For more information about virtualization, see [ClickOnce Deployment on Windows Vista](https://docs.microsoft.com/visualstudio/deployment/clickonce-deployment-on-windows-vista).</span></span>  
  
 <span data-ttu-id="68851-108">Дополнительные сведения о создании манифестов см. в разделе [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span><span class="sxs-lookup"><span data-stu-id="68851-108">For more information about manifest creation, see [/win32manifest (Visual Basic)](../../../visual-basic/reference/command-line-compiler/win32manifest.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68851-109">См. также</span><span class="sxs-lookup"><span data-stu-id="68851-109">See Also</span></span>  
 <span data-ttu-id="68851-110">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="68851-110">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="68851-111"> [Страница "Приложение" в конструкторе проектов (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="68851-111"> [Application Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/application-page-project-designer-visual-basic)</span></span>
