---
title: "-bugreport (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /bugreport
dev_langs:
- CSharp
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 20
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
ms.openlocfilehash: ccfea1aa7e51ad013418f61bc4478034c9a5d830
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="bugreport-c-compiler-options"></a><span data-ttu-id="91546-102">/bugreport (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="91546-102">/bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="91546-103">Указывает, что отладочную информацию следует поместить в файл для последующего анализа.</span><span class="sxs-lookup"><span data-stu-id="91546-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91546-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91546-104">Syntax</span></span>  
  
```console  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="91546-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="91546-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="91546-106">Имя файла, который будет содержать отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="91546-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91546-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="91546-107">Remarks</span></span>  
 <span data-ttu-id="91546-108">Параметр **/bugreport** указывает, что в `file` необходимо поместить следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="91546-108">The **/bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
-   <span data-ttu-id="91546-109">Копия всех файлов исходного кода, включенных в компиляцию.</span><span class="sxs-lookup"><span data-stu-id="91546-109">A copy of all source code files in the compilation.</span></span>  
  
-   <span data-ttu-id="91546-110">Список параметров компилятора, используемых при компиляции.</span><span class="sxs-lookup"><span data-stu-id="91546-110">A listing of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="91546-111">Сведения о версии компилятора, среды выполнения и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="91546-111">Version information about your compiler, run time, and operating system.</span></span>  
  
-   <span data-ttu-id="91546-112">Сборки и модули, на которые задаются ссылки, в формате шестнадцатеричных чисел, за исключением сборок, входящих в комплект поставки .NET Framework и SDK.</span><span class="sxs-lookup"><span data-stu-id="91546-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
-   <span data-ttu-id="91546-113">Выходные данные компилятора (если есть).</span><span class="sxs-lookup"><span data-stu-id="91546-113">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="91546-114">Описание проблемы, которое вам потребуется предоставить.</span><span class="sxs-lookup"><span data-stu-id="91546-114">A description of the problem, which you will be prompted for.</span></span>  
  
-   <span data-ttu-id="91546-115">Описание предполагаемого способа разрешения проблемы, которое вам потребуется предоставить.</span><span class="sxs-lookup"><span data-stu-id="91546-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="91546-116">Если этот параметр используется с параметром **/errorreport:prompt** или **/errorreport:send**, содержимое файла будет передано в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="91546-116">If this option is used with **/errorreport:prompt** or **/errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="91546-117">Поскольку в `file` будут помещены копии всех файлов исходного кода, рекомендуется воспроизводить предполагаемую ошибку в коде с использованием максимально короткой программы.</span><span class="sxs-lookup"><span data-stu-id="91546-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="91546-118">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="91546-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="91546-119">Обратите внимание, что содержимое созданного файла раскрывает исходный код, что может привести к непреднамеренному разглашению информации.</span><span class="sxs-lookup"><span data-stu-id="91546-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91546-120">См. также</span><span class="sxs-lookup"><span data-stu-id="91546-120">See Also</span></span>  
 <span data-ttu-id="91546-121">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="91546-121">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="91546-122">[/errorreport (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="91546-122">[/errorreport (C# Compiler Options)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md) </span></span>  
 [<span data-ttu-id="91546-123">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="91546-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

