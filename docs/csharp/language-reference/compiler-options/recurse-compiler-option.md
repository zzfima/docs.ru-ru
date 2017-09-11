---
title: "-recurse (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
dev_langs:
- CSharp
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
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
ms.openlocfilehash: 99664f8b32f5f9e5bf491c5bfde2c1649de42dd9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="recurse-c-compiler-options"></a><span data-ttu-id="cf996-102">/recurse (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="cf996-102">/recurse (C# Compiler Options)</span></span>
<span data-ttu-id="cf996-103">Параметр /recurse позволяет компилировать файлы исходного кода во всех вложенных каталогах заданного каталога (dir) или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="cf996-103">The /recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf996-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cf996-104">Syntax</span></span>  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="cf996-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="cf996-105">Arguments</span></span>  
 <span data-ttu-id="cf996-106">`dir` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="cf996-106">`dir` (optional)</span></span>  
 <span data-ttu-id="cf996-107">Каталог, с которого будет начинаться поиск.</span><span class="sxs-lookup"><span data-stu-id="cf996-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="cf996-108">Если этот параметр не задан, поиск начинается с каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="cf996-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="cf996-109">Файлы для поиска.</span><span class="sxs-lookup"><span data-stu-id="cf996-109">The file(s) to search for.</span></span> <span data-ttu-id="cf996-110">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="cf996-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf996-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cf996-111">Remarks</span></span>  
 <span data-ttu-id="cf996-112">Параметр **/recurse** позволяет компилировать файлы исходного кода во всех вложенных каталогах заданного каталога (`dir`) или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="cf996-112">The **/recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="cf996-113">Чтобы скомпилировать все соответствующие файлы в каталоге проекта, не задавая параметр **/recurse**, можно использовать подстановочные знаки в именах файлов.</span><span class="sxs-lookup"><span data-stu-id="cf996-113">You can use wildcards in a file name to compile all matching files in the project directory without using **/recurse**.</span></span>  
  
 <span data-ttu-id="cf996-114">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="cf996-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf996-115">Пример</span><span class="sxs-lookup"><span data-stu-id="cf996-115">Example</span></span>  
 <span data-ttu-id="cf996-116">Компиляция всех файлов C# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="cf996-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="cf996-117">Компиляция всех файлов C# в каталоге dir1\dir2 и всех вложенных в него каталогах, а также создание файла dir2.dll:</span><span class="sxs-lookup"><span data-stu-id="cf996-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf996-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cf996-118">See Also</span></span>  
 <span data-ttu-id="cf996-119">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf996-119">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="cf996-120">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="cf996-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

