---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: 19a70e500f6b75fd003bdb798f242cddb3926935
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964349"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="0ae69-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ae69-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="0ae69-103">Приводит к тому, что компилятор не будет автоматически ссылаться на стандартные библиотеки.</span><span class="sxs-lookup"><span data-stu-id="0ae69-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae69-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ae69-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="0ae69-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ae69-105">Remarks</span></span>  
 <span data-ttu-id="0ae69-106">`-nostdlib` Параметр удаляет автоматическую ссылку на сборку System. dll и запрещает компилятору считывать файл Vbc. rsp.</span><span class="sxs-lookup"><span data-stu-id="0ae69-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="0ae69-107">Файл Vbc. rsp, расположенный в том же каталоге, что и файл Vbc. exe, ссылается на часто используемые .NET Framework сборки и импортирует `System` пространства имен и. `Microsoft.VisualBasic`</span><span class="sxs-lookup"><span data-stu-id="0ae69-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ae69-108">Ссылки на сборки mscorlib. dll и Microsoft. VisualBasic. dll всегда существуют.</span><span class="sxs-lookup"><span data-stu-id="0ae69-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ae69-109">Этот `-nostdlib` параметр недоступен в среде разработки Visual Studio; он доступен только при компиляции из командной строки.</span><span class="sxs-lookup"><span data-stu-id="0ae69-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ae69-110">Пример</span><span class="sxs-lookup"><span data-stu-id="0ae69-110">Example</span></span>  
 <span data-ttu-id="0ae69-111">Следующий код компилируется `T2.vb` без ссылок на стандартные библиотеки.</span><span class="sxs-lookup"><span data-stu-id="0ae69-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="0ae69-112">`_MYTYPE` Для`My` удаления объекта необходимо задать константу условной компиляции в виде строки "Empty".</span><span class="sxs-lookup"><span data-stu-id="0ae69-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ae69-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0ae69-113">See also</span></span>

- [<span data-ttu-id="0ae69-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="0ae69-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="0ae69-115">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="0ae69-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0ae69-116">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="0ae69-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="0ae69-117">Настройка доступа к объектам через My</span><span class="sxs-lookup"><span data-stu-id="0ae69-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
