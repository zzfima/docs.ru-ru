---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3764409f13a00f6d8a050bfbdd0f59e537a5ded3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652722"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="d294c-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d294c-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="d294c-103">Указывает компилятору не ссылаться на стандартные библиотеки автоматически.</span><span class="sxs-lookup"><span data-stu-id="d294c-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d294c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d294c-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="d294c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="d294c-105">Remarks</span></span>  
 <span data-ttu-id="d294c-106">`-nostdlib` Удаляет автоматическую ссылку на сборку System.dll и запрещает компилятору считывание файла Vbc.rsp.</span><span class="sxs-lookup"><span data-stu-id="d294c-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="d294c-107">Файл Vbc.rsp, который находится в том же каталоге, что и файл Vbc.exe, ссылается на часто используемые [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] сборки и Импортируемые пространства имен `System` и `Microsoft.VisualBasic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d294c-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d294c-108">Всегда создаются ссылки на сборки Mscorlib.dll и Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="d294c-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d294c-109">`-nostdlib` Параметр недоступен в среде разработки Visual Studio; она доступна только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="d294c-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d294c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="d294c-110">Example</span></span>  
 <span data-ttu-id="d294c-111">Следующий код компилирует `T2.vb` без ссылок на стандартные библиотеки.</span><span class="sxs-lookup"><span data-stu-id="d294c-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="d294c-112">Необходимо задать `_MYTYPE` константы условной компиляции на пустой строке, чтобы удалить `My` объекта.</span><span class="sxs-lookup"><span data-stu-id="d294c-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d294c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d294c-113">See Also</span></span>  
 [<span data-ttu-id="d294c-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="d294c-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="d294c-115">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d294c-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d294c-116">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d294c-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="d294c-117">Настройка доступа к объектам через My</span><span class="sxs-lookup"><span data-stu-id="d294c-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
