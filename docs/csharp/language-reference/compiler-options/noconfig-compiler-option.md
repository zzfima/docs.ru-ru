---
title: -noconfig (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 2d6d0c52be2306292224d7831f8818c6f865f2f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602736"
---
# <a name="-noconfig-c-compiler-options"></a><span data-ttu-id="4c6dc-102">-noconfig (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="4c6dc-102">-noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="4c6dc-103">Параметр **-noconfig** указывает компилятору не выполнять компиляцию с использованием файла csc.rsp, который располагается в том же каталоге, что и файл csc.exe, и загружается оттуда.</span><span class="sxs-lookup"><span data-stu-id="4c6dc-103">The **-noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c6dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c6dc-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="4c6dc-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="4c6dc-105">Remarks</span></span>  
 <span data-ttu-id="4c6dc-106">Файл csc.rsp содержит ссылки на все сборки, поставляемые вместе с платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4c6dc-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="4c6dc-107">Фактические ссылки, которые включает среда разработки Visual Studio .NET, зависят от типа проекта.</span><span class="sxs-lookup"><span data-stu-id="4c6dc-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="4c6dc-108">Вы можете изменить файл csc.rsp и указать дополнительные параметры компилятора, которые нужно включать при каждой компиляции, из командной строки с помощью программы csc.exe (кроме параметра **-noconfig**).</span><span class="sxs-lookup"><span data-stu-id="4c6dc-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **-noconfig** option).</span></span>  
  
 <span data-ttu-id="4c6dc-109">Компилятор обрабатывает параметры, передаваемые в команду **csc**, последними.</span><span class="sxs-lookup"><span data-stu-id="4c6dc-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="4c6dc-110">Таким образом, любой параметр командной строки переопределяет значение аналогичного параметра в файле csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="4c6dc-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="4c6dc-111">Если не требуется, чтобы компилятор искал и использовал параметры в файле csc.rsp, укажите параметр **-noconfig**.</span><span class="sxs-lookup"><span data-stu-id="4c6dc-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **-noconfig**.</span></span>  
  
 <span data-ttu-id="4c6dc-112">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="4c6dc-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c6dc-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4c6dc-113">See also</span></span>

- [<span data-ttu-id="4c6dc-114">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="4c6dc-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="4c6dc-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="4c6dc-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
