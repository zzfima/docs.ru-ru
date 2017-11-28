---
title: "-noconfig (параметры компилятора C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2b15853cdd6ee9fe12b8b3ba3388a74e49c9701
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="noconfig-c-compiler-options"></a><span data-ttu-id="12207-102">/noconfig (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="12207-102">/noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="12207-103">Параметр **/noconfig** указывает компилятору не выполнять компиляцию с использованием файла csc.rsp, который располагается в том же каталоге, что и файл csc.exe, и загружается из этого каталога.</span><span class="sxs-lookup"><span data-stu-id="12207-103">The **/noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12207-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="12207-104">Syntax</span></span>  
  
```console  
/noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="12207-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="12207-105">Remarks</span></span>  
 <span data-ttu-id="12207-106">Файл csc.rsp содержит ссылки на все сборки, поставляемые вместе с платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="12207-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="12207-107">Фактические ссылки, которые включает среда разработки Visual Studio .NET, зависят от типа проекта.</span><span class="sxs-lookup"><span data-stu-id="12207-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="12207-108">Вы можете изменить файл csc.rsp и указать дополнительные параметры компилятора, которые необходимо включать каждый раз при компиляции, из командной строки с помощью файла csc.exe (кроме параметра **/noconfig**).</span><span class="sxs-lookup"><span data-stu-id="12207-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **/noconfig** option).</span></span>  
  
 <span data-ttu-id="12207-109">Компилятор обрабатывает параметры, передаваемые в команду **csc**, последними.</span><span class="sxs-lookup"><span data-stu-id="12207-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="12207-110">Таким образом, любой параметр командной строки переопределяет значение аналогичного параметра в файле csc.rsp.</span><span class="sxs-lookup"><span data-stu-id="12207-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="12207-111">Если не требуется, чтобы компилятор искал и использовал параметры в файле csc.rsp, укажите параметр **/noconfig**.</span><span class="sxs-lookup"><span data-stu-id="12207-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **/noconfig**.</span></span>  
  
 <span data-ttu-id="12207-112">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="12207-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12207-113">См. также</span><span class="sxs-lookup"><span data-stu-id="12207-113">See Also</span></span>  
 [<span data-ttu-id="12207-114">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="12207-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="12207-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="12207-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
