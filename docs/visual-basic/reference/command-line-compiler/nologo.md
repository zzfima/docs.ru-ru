---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 011c9499eaa728588e6181e33a96dd75b4a7b84b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="fd3d4-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd3d4-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="fd3d4-103">Отключает отображение авторских прав и информационные сообщения во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="fd3d4-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd3d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd3d4-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="fd3d4-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd3d4-105">Remarks</span></span>  
 <span data-ttu-id="fd3d4-106">При указании `-nologo`, компилятор не отображает баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="fd3d4-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="fd3d4-107">По умолчанию `-nologo` не действует.</span><span class="sxs-lookup"><span data-stu-id="fd3d4-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd3d4-108">`-nologo` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="fd3d4-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd3d4-109">Пример</span><span class="sxs-lookup"><span data-stu-id="fd3d4-109">Example</span></span>  
 <span data-ttu-id="fd3d4-110">Следующий код компилирует `T2.vb` и не будут отображаться баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="fd3d4-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd3d4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="fd3d4-111">See Also</span></span>  
 [<span data-ttu-id="fd3d4-112">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="fd3d4-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="fd3d4-113">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="fd3d4-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
