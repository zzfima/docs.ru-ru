---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8e5eb9db7af861a8439b47adb8f5e515331fae6e
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="601bc-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="601bc-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="601bc-103">Отключает отображение авторских прав и информационные сообщения во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="601bc-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="601bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="601bc-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="601bc-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="601bc-105">Remarks</span></span>  
 <span data-ttu-id="601bc-106">При указании `-nologo`, компилятор не отображает баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="601bc-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="601bc-107">По умолчанию `-nologo` не действует.</span><span class="sxs-lookup"><span data-stu-id="601bc-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="601bc-108">`-nologo` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="601bc-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="601bc-109">Пример</span><span class="sxs-lookup"><span data-stu-id="601bc-109">Example</span></span>  
 <span data-ttu-id="601bc-110">Следующий код компилирует `T2.vb` и не будут отображаться баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="601bc-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="601bc-111">См. также</span><span class="sxs-lookup"><span data-stu-id="601bc-111">See Also</span></span>  
 [<span data-ttu-id="601bc-112">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="601bc-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="601bc-113">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="601bc-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
