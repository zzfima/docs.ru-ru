---
title: -fullpaths (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /fullpaths
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
ms.openlocfilehash: 8f23bb683067c55f5b5213065c3082b843dd7dce
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43522947"
---
# <a name="-fullpaths-c-compiler-options"></a><span data-ttu-id="90425-102">-fullpaths (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="90425-102">-fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="90425-103">Параметр **-fullpaths** указывает компилятору на необходимость задавать полный путь к файлу при выводе списка ошибок и предупреждений компиляции.</span><span class="sxs-lookup"><span data-stu-id="90425-103">The **-fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90425-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90425-104">Syntax</span></span>  
  
```console  
-fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="90425-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="90425-105">Remarks</span></span>  
 <span data-ttu-id="90425-106">По умолчанию для ошибок и предупреждений, возникающих в ходе компиляции, указывается имя файла, в котором они были обнаружены.</span><span class="sxs-lookup"><span data-stu-id="90425-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="90425-107">Параметр **-fullpaths** указывает компилятору на необходимость задавать полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="90425-107">The **-fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="90425-108">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="90425-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90425-109">См. также</span><span class="sxs-lookup"><span data-stu-id="90425-109">See Also</span></span>  

- [<span data-ttu-id="90425-110">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="90425-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
