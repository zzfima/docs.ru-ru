---
title: "-pdb (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7528283765c2b6f4a9d5e84015526a95938a6281
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="8277f-102">-pdb (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="8277f-102">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="8277f-103">Параметр компилятора **-pdb** задает имя и расположение файла отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="8277f-103">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8277f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8277f-104">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="8277f-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="8277f-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="8277f-106">Имя и расположение файла отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="8277f-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8277f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8277f-107">Remarks</span></span>  
 <span data-ttu-id="8277f-108">Если указан параметр [-debug (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), компилятор создаст в каталоге с выходным файлом (EXE или DLL) PDB-файл с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="8277f-108">When you specify [-debug (C# Compiler Options)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="8277f-109">С помощью параметра **-pdb** можно задать имя PDB-файла, отличающееся от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8277f-109">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="8277f-110">Этот параметр компилятора нельзя задать в среде разработки Visual Studio или изменить программными средствами.</span><span class="sxs-lookup"><span data-stu-id="8277f-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8277f-111">Пример</span><span class="sxs-lookup"><span data-stu-id="8277f-111">Example</span></span>  
 <span data-ttu-id="8277f-112">Компиляция файла `t.cs` и создание файла tt.pdb:</span><span class="sxs-lookup"><span data-stu-id="8277f-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8277f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8277f-113">See Also</span></span>  
 [<span data-ttu-id="8277f-114">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="8277f-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="8277f-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="8277f-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
