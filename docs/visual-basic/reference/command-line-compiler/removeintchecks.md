---
title: "/ removeintchecks | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
dev_langs:
- VB
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
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
ms.openlocfilehash: 25f67774238c6e9a6b3a2c50b3702e43d5a6374c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="removeintchecks"></a><span data-ttu-id="f53c8-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="f53c8-102">/removeintchecks</span></span>
<span data-ttu-id="f53c8-103">Включает проверка ошибки переполнения для целочисленных операций или отключить.</span><span class="sxs-lookup"><span data-stu-id="f53c8-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f53c8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f53c8-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f53c8-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f53c8-105">Arguments</span></span>  
  
|<span data-ttu-id="f53c8-106">Термин</span><span class="sxs-lookup"><span data-stu-id="f53c8-106">Term</span></span>|<span data-ttu-id="f53c8-107">Определение</span><span class="sxs-lookup"><span data-stu-id="f53c8-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="f53c8-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f53c8-108">`+` &#124; `-`</span></span>|<span data-ttu-id="f53c8-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="f53c8-109">Optional.</span></span> <span data-ttu-id="f53c8-110">`/removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения.</span><span class="sxs-lookup"><span data-stu-id="f53c8-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="f53c8-111">Значение по умолчанию — `/removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="f53c8-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="f53c8-112">Указание `/removeintchecks` или `/removeintchecks+` предотвращает проверку ошибок и позволяют быстрее целочисленные вычисления.</span><span class="sxs-lookup"><span data-stu-id="f53c8-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="f53c8-113">Тем не менее, без проверки ошибок, и если производственные мощности тип данных переполнен, неверные результаты могут храниться без возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="f53c8-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="f53c8-114">Чтобы задать дополнительные сведения в Visual Studio интегрированная среда разработки</span><span class="sxs-lookup"><span data-stu-id="f53c8-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f53c8-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="f53c8-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f53c8-116">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="f53c8-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="f53c8-117">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="f53c8-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="f53c8-118">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="f53c8-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="f53c8-119">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="f53c8-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="f53c8-120">4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.</span><span class="sxs-lookup"><span data-stu-id="f53c8-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f53c8-121">Пример</span><span class="sxs-lookup"><span data-stu-id="f53c8-121">Example</span></span>  
 <span data-ttu-id="f53c8-122">Следующий код компилирует `Test.vb` и отключает проверку ошибок переполнения целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="f53c8-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f53c8-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f53c8-123">See Also</span></span>  
 <span data-ttu-id="f53c8-124">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f53c8-124">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f53c8-125"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="f53c8-125"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
