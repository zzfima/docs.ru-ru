---
title: "-fullpaths (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /fullpaths
helpviewer_keywords:
- /fullpaths compiler option [C#]
- absolute paths [C#]
- fullpaths compiler option [C#]
- full paths [C#]
- -fullpaths compiler option [C#]
ms.assetid: d2a5f857-cbb2-430b-879c-d648aaf0b8c4
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5cc48337c9c85bf5adfaf8fc24a414e6db4ba26
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-fullpaths-c-compiler-options"></a><span data-ttu-id="2a98e-102">-fullpaths (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="2a98e-102">-fullpaths (C# Compiler Options)</span></span>
<span data-ttu-id="2a98e-103">Параметр **-fullpaths** указывает компилятору на необходимость задавать полный путь к файлу при выводе списка ошибок и предупреждений компиляции.</span><span class="sxs-lookup"><span data-stu-id="2a98e-103">The **-fullpaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a98e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2a98e-104">Syntax</span></span>  
  
```console  
-fullpaths  
```  
  
## <a name="remarks"></a><span data-ttu-id="2a98e-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="2a98e-105">Remarks</span></span>  
 <span data-ttu-id="2a98e-106">По умолчанию для ошибок и предупреждений, возникающих в ходе компиляции, указывается имя файла, в котором они были обнаружены.</span><span class="sxs-lookup"><span data-stu-id="2a98e-106">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="2a98e-107">Параметр **-fullpaths** указывает компилятору на необходимость задавать полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="2a98e-107">The **-fullpaths** option causes the compiler to specify the full path to the file.</span></span>  
  
 <span data-ttu-id="2a98e-108">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="2a98e-108">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a98e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="2a98e-109">See Also</span></span>  
 [<span data-ttu-id="2a98e-110">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="2a98e-110">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
