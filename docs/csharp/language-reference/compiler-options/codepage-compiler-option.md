---
title: "-codepage (параметры компилятора C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /codepage
dev_langs:
- CSharp
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
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
ms.openlocfilehash: b80f6fcf8891d2f0b921af01cc094f624d807aa1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="codepage-c-compiler-options"></a><span data-ttu-id="b474d-102">/codepage (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="b474d-102">/codepage (C# Compiler Options)</span></span>
<span data-ttu-id="b474d-103">Этот параметр задает кодовую страницу, используемую во время компиляции, если требуемая страница не является текущей кодовой страницей системы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b474d-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b474d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b474d-104">Syntax</span></span>  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="b474d-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="b474d-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="b474d-106">Идентификатор кодовой страницы, используемой для всех файлов исходного кода при компиляции.</span><span class="sxs-lookup"><span data-stu-id="b474d-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b474d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="b474d-107">Remarks</span></span>  
 <span data-ttu-id="b474d-108">При компиляции одного или нескольких файлов исходного кода, не использующих кодовую страницу по умолчанию, с помощью параметра **/codepage** можно указать нужную кодовую страницу.</span><span class="sxs-lookup"><span data-stu-id="b474d-108">If you compile one or more source code files that were not created to use the default code page on your computer, you can use the **/codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="b474d-109">Параметр **/codepage** применяется ко всем файлам исходного кода, включенным в компиляцию.</span><span class="sxs-lookup"><span data-stu-id="b474d-109">**/codepage** applies to all source code files in your compilation.</span></span>  
  
 <span data-ttu-id="b474d-110">Если файлы исходного кода были созданы с помощью кодовой страницы, включенной на компьютере, либо с помощью кодовой страницы UNICODE или UTF-8, использовать параметр **/codepage** не требуется.</span><span class="sxs-lookup"><span data-stu-id="b474d-110">If the source code files were created with the same codepage that is in effect on your computer or if the source code files were created with UNICODE or UTF-8, you need not use **/codepage**.</span></span>  
  
 <span data-ttu-id="b474d-111">Сведения о том, как найти кодовые страницы, которые поддерживаются в системе, см. на странице, посвященной функции [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371).</span><span class="sxs-lookup"><span data-stu-id="b474d-111">See [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="b474d-112">Этот параметр компилятора недоступен в Visual Studio и не может быть изменен программным способом.</span><span class="sxs-lookup"><span data-stu-id="b474d-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b474d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b474d-113">See Also</span></span>  
 <span data-ttu-id="b474d-114">[Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="b474d-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="b474d-115">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="b474d-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

