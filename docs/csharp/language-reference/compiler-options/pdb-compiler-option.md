---
title: "-pdb (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /pdb
dev_langs:
- CSharp
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 8
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7c72c12347a9096aeed063b84310356cb07b49c3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="pdb-c-compiler-options"></a><span data-ttu-id="656b4-102">/pdb (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="656b4-102">/pdb (C# Compiler Options)</span></span>
<span data-ttu-id="656b4-103">Параметр компилятора **/pdb** задает имя и расположение файла отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="656b4-103">The **/pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="656b4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="656b4-104">Syntax</span></span>  
  
```console  
/pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="656b4-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="656b4-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="656b4-106">Имя и расположение файла отладочных символов.</span><span class="sxs-lookup"><span data-stu-id="656b4-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="656b4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="656b4-107">Remarks</span></span>  
 <span data-ttu-id="656b4-108">Если указан параметр [/debug (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), компилятор создаст в каталоге с выходным файлом (EXE или DLL) PDB-файл с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="656b4-108">When you specify [/debug (C# Compiler Options)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="656b4-109">С помощью параметра **/pdb** можно задать имя PDB-файла, отличающееся от используемого по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="656b4-109">**/pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="656b4-110">Этот параметр компилятора нельзя задать в среде разработки Visual Studio или изменить программными средствами.</span><span class="sxs-lookup"><span data-stu-id="656b4-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="656b4-111">Пример</span><span class="sxs-lookup"><span data-stu-id="656b4-111">Example</span></span>  
 <span data-ttu-id="656b4-112">Компиляция файла `t.cs` и создание файла tt.pdb:</span><span class="sxs-lookup"><span data-stu-id="656b4-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc /debug /pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="656b4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="656b4-113">See Also</span></span>  
 <span data-ttu-id="656b4-114">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="656b4-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="656b4-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="656b4-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

