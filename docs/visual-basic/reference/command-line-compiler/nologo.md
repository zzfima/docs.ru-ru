---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 21c708ef632cc0ed923713cd49e22d44848b4db3
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131148"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="0e2a5-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e2a5-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="0e2a5-103">Отключает отображение авторских прав и информационных сообщений во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e2a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e2a5-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="0e2a5-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e2a5-105">Remarks</span></span>  
 <span data-ttu-id="0e2a5-106">Если указать `-nologo`, компилятор не отображается баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="0e2a5-107">По умолчанию `-nologo` не действует.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e2a5-108">`-nologo` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e2a5-109">Пример</span><span class="sxs-lookup"><span data-stu-id="0e2a5-109">Example</span></span>  
 <span data-ttu-id="0e2a5-110">Следующий код компилирует `T2.vb` и не отображается баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="0e2a5-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e2a5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0e2a5-111">See Also</span></span>  
 [<span data-ttu-id="0e2a5-112">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="0e2a5-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0e2a5-113">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="0e2a5-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
