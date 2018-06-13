---
title: -bugreport (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 5505971ad9a6920124dd4d8c12642a5e4e346322
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214096"
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="2d455-102">-bugreport (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="2d455-102">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="2d455-103">Указывает, что отладочную информацию следует поместить в файл для последующего анализа.</span><span class="sxs-lookup"><span data-stu-id="2d455-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d455-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2d455-104">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d455-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="2d455-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="2d455-106">Имя файла, который будет содержать отчет об ошибках.</span><span class="sxs-lookup"><span data-stu-id="2d455-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d455-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="2d455-107">Remarks</span></span>  
 <span data-ttu-id="2d455-108">Параметр **-bugreport** указывает, что в `file` нужно поместить следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="2d455-108">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
-   <span data-ttu-id="2d455-109">Копия всех файлов исходного кода, включенных в компиляцию.</span><span class="sxs-lookup"><span data-stu-id="2d455-109">A copy of all source code files in the compilation.</span></span>  
  
-   <span data-ttu-id="2d455-110">Список параметров компилятора, используемых при компиляции.</span><span class="sxs-lookup"><span data-stu-id="2d455-110">A listing of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="2d455-111">Сведения о версии компилятора, среды выполнения и операционной системы.</span><span class="sxs-lookup"><span data-stu-id="2d455-111">Version information about your compiler, run time, and operating system.</span></span>  
  
-   <span data-ttu-id="2d455-112">Сборки и модули, на которые задаются ссылки, в формате шестнадцатеричных чисел, за исключением сборок, входящих в комплект поставки .NET Framework и SDK.</span><span class="sxs-lookup"><span data-stu-id="2d455-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
-   <span data-ttu-id="2d455-113">Выходные данные компилятора (если есть).</span><span class="sxs-lookup"><span data-stu-id="2d455-113">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="2d455-114">Описание проблемы, которое вам потребуется предоставить.</span><span class="sxs-lookup"><span data-stu-id="2d455-114">A description of the problem, which you will be prompted for.</span></span>  
  
-   <span data-ttu-id="2d455-115">Описание предполагаемого способа разрешения проблемы, которое вам потребуется предоставить.</span><span class="sxs-lookup"><span data-stu-id="2d455-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="2d455-116">Если этот параметр используется с параметром **-errorreport:prompt** или **-errorreport:send**, содержимое файла будет передано в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2d455-116">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="2d455-117">Поскольку в `file` будут помещены копии всех файлов исходного кода, рекомендуется воспроизводить предполагаемую ошибку в коде с использованием максимально короткой программы.</span><span class="sxs-lookup"><span data-stu-id="2d455-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="2d455-118">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="2d455-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="2d455-119">Обратите внимание, что содержимое созданного файла раскрывает исходный код, что может привести к непреднамеренному разглашению информации.</span><span class="sxs-lookup"><span data-stu-id="2d455-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d455-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2d455-120">See Also</span></span>  
 [<span data-ttu-id="2d455-121">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="2d455-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="2d455-122">-errorreport (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="2d455-122">-errorreport (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)  
 [<span data-ttu-id="2d455-123">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="2d455-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
