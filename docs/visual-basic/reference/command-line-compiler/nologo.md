---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 1b9cedc3e45795a66c203d4c86bb071045a1d3f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550478"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="a48a4-102">-nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a48a4-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="a48a4-103">Отключает отображение авторских прав и информационных сообщений во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="a48a4-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a48a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a48a4-104">Syntax</span></span>  
  
```  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="a48a4-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="a48a4-105">Remarks</span></span>  
 <span data-ttu-id="a48a4-106">Если указать `-nologo`, компилятор не отображается баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="a48a4-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="a48a4-107">По умолчанию `-nologo` не действует.</span><span class="sxs-lookup"><span data-stu-id="a48a4-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a48a4-108">`-nologo` Не доступна из среды разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="a48a4-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a48a4-109">Пример</span><span class="sxs-lookup"><span data-stu-id="a48a4-109">Example</span></span>  
 <span data-ttu-id="a48a4-110">Следующий код компилирует `T2.vb` и не отображается баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="a48a4-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a48a4-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a48a4-111">See also</span></span>
- [<span data-ttu-id="a48a4-112">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="a48a4-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="a48a4-113">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="a48a4-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
