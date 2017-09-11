---
title: "/ nowarn | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 308bf24c2a397a75f36b97062dde7380b90c8994
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="nowarn"></a><span data-ttu-id="4bc85-102">/nowarn</span><span class="sxs-lookup"><span data-stu-id="4bc85-102">/nowarn</span></span>
<span data-ttu-id="4bc85-103">Отключает возможность компилятора создавать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4bc85-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bc85-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bc85-104">Syntax</span></span>  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="4bc85-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="4bc85-105">Arguments</span></span>  
  
|<span data-ttu-id="4bc85-106">Термин</span><span class="sxs-lookup"><span data-stu-id="4bc85-106">Term</span></span>|<span data-ttu-id="4bc85-107">Определение</span><span class="sxs-lookup"><span data-stu-id="4bc85-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="4bc85-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="4bc85-108">Optional.</span></span> <span data-ttu-id="4bc85-109">Список с разделителями запятыми Идентификационных номеров предупреждений, которые компилятор не должен отображать.</span><span class="sxs-lookup"><span data-stu-id="4bc85-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="4bc85-110">Если идентификаторы предупреждений не указаны, то подавляются все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4bc85-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bc85-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="4bc85-111">Remarks</span></span>  
 <span data-ttu-id="4bc85-112">`/nowarn` Параметр указывает компилятору не генерировать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4bc85-112">The `/nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="4bc85-113">Для подавления отдельных предупреждений, укажите идентификатор предупреждения для `/nowarn` после двоеточия.</span><span class="sxs-lookup"><span data-stu-id="4bc85-113">To suppress an individual warning, supply the warning ID to the `/nowarn` option following the colon.</span></span> <span data-ttu-id="4bc85-114">Отделите предупреждения друг от друга запятыми.</span><span class="sxs-lookup"><span data-stu-id="4bc85-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="4bc85-115">Необходимо указать только числовую часть идентификатора предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4bc85-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="4bc85-116">Например, если требуется подавить BC42024, предупреждение для неиспользуемых локальных переменных, укажите `/nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="4bc85-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `/nowarn:42024`.</span></span>  
  
 <span data-ttu-id="4bc85-117">Дополнительные сведения об Идентификационных номеров предупреждений см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="4bc85-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="4bc85-118">Установка/nowarn в Visual Studio интегрированная среда разработки</span><span class="sxs-lookup"><span data-stu-id="4bc85-118">To set /nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="4bc85-119">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="4bc85-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4bc85-120">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="4bc85-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="4bc85-121">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="4bc85-121">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="4bc85-122">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="4bc85-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="4bc85-123">3.  Выберите **отключить все предупреждения** флажок, чтобы отключить все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4bc85-123">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="4bc85-124">-или-</span><span class="sxs-lookup"><span data-stu-id="4bc85-124">- or -</span></span><br />     <span data-ttu-id="4bc85-125">Чтобы отключить определенное предупреждение, щелкните **нет** из раскрывающегося списка рядом с предупреждением.</span><span class="sxs-lookup"><span data-stu-id="4bc85-125">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4bc85-126">Пример</span><span class="sxs-lookup"><span data-stu-id="4bc85-126">Example</span></span>  
 <span data-ttu-id="4bc85-127">Следующий код компилирует `T2.vb` и не отображает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="4bc85-127">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="4bc85-128">Пример</span><span class="sxs-lookup"><span data-stu-id="4bc85-128">Example</span></span>  
 <span data-ttu-id="4bc85-129">Следующий код компилирует `T2.vb` и не отображает предупреждения для неиспользуемых локальных переменных (42024).</span><span class="sxs-lookup"><span data-stu-id="4bc85-129">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bc85-130">См. также</span><span class="sxs-lookup"><span data-stu-id="4bc85-130">See Also</span></span>  
 <span data-ttu-id="4bc85-131">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="4bc85-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="4bc85-132"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="4bc85-132"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="4bc85-133"> [Настройка предупреждений в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="4bc85-133"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
