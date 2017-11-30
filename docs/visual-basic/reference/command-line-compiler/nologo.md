---
title: /nologo (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c2c7e7a111a3763d7463f67c2d984955da33bbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nologo-visual-basic"></a><span data-ttu-id="b8cd5-102">/nologo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8cd5-102">/nologo (Visual Basic)</span></span>
<span data-ttu-id="b8cd5-103">Отключает отображение авторских прав и информационные сообщения во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="b8cd5-103">Suppresses display of the copyright banner and informational messages during compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8cd5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8cd5-104">Syntax</span></span>  
  
```  
/nologo  
```  
  
## <a name="remarks"></a><span data-ttu-id="b8cd5-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="b8cd5-105">Remarks</span></span>  
 <span data-ttu-id="b8cd5-106">При указании `/nologo`, компилятор не отображает баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="b8cd5-106">If you specify `/nologo`, the compiler does not display a copyright banner.</span></span> <span data-ttu-id="b8cd5-107">По умолчанию `/nologo` не действует.</span><span class="sxs-lookup"><span data-stu-id="b8cd5-107">By default, `/nologo` is not in effect.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8cd5-108">`/nologo` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="b8cd5-108">The `/nologo` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8cd5-109">Пример</span><span class="sxs-lookup"><span data-stu-id="b8cd5-109">Example</span></span>  
 <span data-ttu-id="b8cd5-110">Следующий код компилирует `T2.vb` и не будут отображаться баннер авторских прав.</span><span class="sxs-lookup"><span data-stu-id="b8cd5-110">The following code compiles `T2.vb` and does not display a copyright banner.</span></span>  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8cd5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b8cd5-111">See Also</span></span>  
 [<span data-ttu-id="b8cd5-112">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="b8cd5-112">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b8cd5-113">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="b8cd5-113">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
