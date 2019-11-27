---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 03dc98c45a894304a67765c3e49cd19bbb089c8c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74335436"
---
# <a name="-nologo-visual-basic"></a><span data-ttu-id="9cf52-102">-неэмблема (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cf52-102">-nologo (Visual Basic)</span></span>
<span data-ttu-id="9cf52-103">Отключает отображение баннера и информационных сообщений об авторских правах во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="9cf52-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cf52-104">Syntax</span></span>  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="9cf52-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cf52-105">Remarks</span></span>  
 <span data-ttu-id="9cf52-106">При указании `-nologo`компилятор не отображает баннер авторского права.</span><span class="sxs-lookup"><span data-stu-id="9cf52-106">If you specify `-nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="9cf52-107">По умолчанию `-nologo` не действует.</span><span class="sxs-lookup"><span data-stu-id="9cf52-107">By default, `-nologo` is not in effect.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9cf52-108">Параметр `-nologo` недоступен в среде разработки Visual Studio; Он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="9cf52-108">The `-nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cf52-109">Пример</span><span class="sxs-lookup"><span data-stu-id="9cf52-109">Example</span></span>  
 <span data-ttu-id="9cf52-110">Следующий код компилирует `T2.vb` и не отображает баннер авторского права.</span><span class="sxs-lookup"><span data-stu-id="9cf52-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9cf52-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9cf52-111">See also</span></span>

- [<span data-ttu-id="9cf52-112">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="9cf52-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="9cf52-113">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="9cf52-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
