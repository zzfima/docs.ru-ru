---
title: "/ nostdlib (Visual Basic) | Документы Microsoft"
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
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
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
ms.openlocfilehash: 046e2b845324ed1c2f8c15bbb029fe84f7693f6e
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="nostdlib-visual-basic"></a><span data-ttu-id="f449d-102">/nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f449d-102">/nostdlib (Visual Basic)</span></span>
<span data-ttu-id="f449d-103">Указывает компилятору не ссылаться на стандартные библиотеки автоматически.</span><span class="sxs-lookup"><span data-stu-id="f449d-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f449d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f449d-104">Syntax</span></span>  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="f449d-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="f449d-105">Remarks</span></span>  
 <span data-ttu-id="f449d-106">`/nostdlib` Удаляет автоматическую ссылку на сборку System.dll и предотвращает чтение файла Vbc.rsp компилятор.</span><span class="sxs-lookup"><span data-stu-id="f449d-106">The `/nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="f449d-107">Файл Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe — ссылается на часто используемые [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] сборки и Импортируемые пространства имен `System` и `Microsoft.VisualBasic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f449d-107">The Vbc.rsp file—which is located in the same directory as the Vbc.exe file—references the commonly used [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f449d-108">Сборки Mscorlib.dll и Microsoft.VisualBasic.dll всегда имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="f449d-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f449d-109">`/nostdlib` Параметр недоступен из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="f449d-109">The `/nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f449d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f449d-110">Example</span></span>  
 <span data-ttu-id="f449d-111">Следующий код компилирует `T2.vb` без ссылок на стандартные библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f449d-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="f449d-112">Необходимо задать `_MYTYPE` константы условной компиляции, в строку «Пустой» для удаления `My` объекта.</span><span class="sxs-lookup"><span data-stu-id="f449d-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f449d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f449d-113">See Also</span></span>  
 <span data-ttu-id="f449d-114">[/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="f449d-114">[/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="f449d-115"> [Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f449d-115"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f449d-116"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="f449d-116"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="f449d-117"> [Настройка доступа к объектам через My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span><span class="sxs-lookup"><span data-stu-id="f449d-117"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)</span></span>
