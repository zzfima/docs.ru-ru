---
title: "-recurse (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b50454112bc7aee6c3e0f8fe674e8727ca9e49be
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="d2e66-102">-recurse (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="d2e66-102">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="d2e66-103">Параметр -recurse позволяет компилировать файлы исходного кода во всех вложенных каталогах заданного каталога (dir) или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="d2e66-103">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2e66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d2e66-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d2e66-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d2e66-105">Arguments</span></span>  
 <span data-ttu-id="d2e66-106">`dir` (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d2e66-106">`dir` (optional)</span></span>  
 <span data-ttu-id="d2e66-107">Каталог, с которого будет начинаться поиск.</span><span class="sxs-lookup"><span data-stu-id="d2e66-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="d2e66-108">Если этот параметр не задан, поиск начинается с каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="d2e66-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="d2e66-109">Файлы для поиска.</span><span class="sxs-lookup"><span data-stu-id="d2e66-109">The file(s) to search for.</span></span> <span data-ttu-id="d2e66-110">Поддерживаются подстановочные знаки.</span><span class="sxs-lookup"><span data-stu-id="d2e66-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2e66-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d2e66-111">Remarks</span></span>  
 <span data-ttu-id="d2e66-112">Параметр **-recurse** позволяет компилировать файлы исходного кода во всех вложенных каталогах заданного каталога (`dir`) или каталога проекта.</span><span class="sxs-lookup"><span data-stu-id="d2e66-112">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="d2e66-113">Чтобы скомпилировать все соответствующие файлы в каталоге проекта, не задавая параметр **-recurse**, можно использовать подстановочные знаки в именах файлов.</span><span class="sxs-lookup"><span data-stu-id="d2e66-113">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="d2e66-114">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="d2e66-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2e66-115">Пример</span><span class="sxs-lookup"><span data-stu-id="d2e66-115">Example</span></span>  
 <span data-ttu-id="d2e66-116">Компиляция всех файлов C# в текущем каталоге:</span><span class="sxs-lookup"><span data-stu-id="d2e66-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="d2e66-117">Компиляция всех файлов C# в каталоге dir1\dir2 и всех вложенных в него каталогах, а также создание файла dir2.dll:</span><span class="sxs-lookup"><span data-stu-id="d2e66-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="d2e66-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d2e66-118">See Also</span></span>  
 [<span data-ttu-id="d2e66-119">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="d2e66-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="d2e66-120">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="d2e66-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
