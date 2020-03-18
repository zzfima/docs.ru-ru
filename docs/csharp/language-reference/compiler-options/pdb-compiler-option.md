---
title: -pdb (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: 3081f4716e8cd858d789db6050e635af941aa05c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602575"
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="cdc4d-102">-pdb (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="cdc4d-102">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="cdc4d-103">Параметр компилятора **-pdb** задает имя и расположение файла отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="cdc4d-103">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc4d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdc4d-104">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="cdc4d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cdc4d-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="cdc4d-106">Имя и расположение файла отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="cdc4d-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdc4d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cdc4d-107">Remarks</span></span>  
 <span data-ttu-id="cdc4d-108">Если указан параметр [-debug (параметры компилятора C#)](./debug-compiler-option.md), компилятор создаст в каталоге с выходным файлом (EXE или DLL) PDB-файл с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="cdc4d-108">When you specify [-debug (C# Compiler Options)](./debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="cdc4d-109">С помощью параметра **-pdb** можно задать имя PDB-файла, отличающееся от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cdc4d-109">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="cdc4d-110">Этот параметр компилятора нельзя задать в среде разработки Visual Studio или изменить программными средствами.</span><span class="sxs-lookup"><span data-stu-id="cdc4d-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdc4d-111">Пример</span><span class="sxs-lookup"><span data-stu-id="cdc4d-111">Example</span></span>  
 <span data-ttu-id="cdc4d-112">Компиляция файла `t.cs` и создание файла tt.pdb:</span><span class="sxs-lookup"><span data-stu-id="cdc4d-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdc4d-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cdc4d-113">See also</span></span>

- [<span data-ttu-id="cdc4d-114">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="cdc4d-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="cdc4d-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="cdc4d-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
