---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a><span data-ttu-id="0d255-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="0d255-102">/removeintchecks</span></span>
<span data-ttu-id="0d255-103">Включает проверка ошибки переполнения для целочисленных операций или отключить.</span><span class="sxs-lookup"><span data-stu-id="0d255-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d255-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d255-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0d255-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0d255-105">Arguments</span></span>  
  
|<span data-ttu-id="0d255-106">Термин</span><span class="sxs-lookup"><span data-stu-id="0d255-106">Term</span></span>|<span data-ttu-id="0d255-107">Определение</span><span class="sxs-lookup"><span data-stu-id="0d255-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="0d255-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="0d255-108">`+` &#124; `-`</span></span>|<span data-ttu-id="0d255-109">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="0d255-109">Optional.</span></span> <span data-ttu-id="0d255-110">`/removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения.</span><span class="sxs-lookup"><span data-stu-id="0d255-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="0d255-111">Значение по умолчанию — `/removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="0d255-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="0d255-112">Указание `/removeintchecks` или `/removeintchecks+` предотвращает проверку ошибок и осуществлять целочисленные вычисления быстрее.</span><span class="sxs-lookup"><span data-stu-id="0d255-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="0d255-113">Тем не менее, без проверки ошибок, и если производственные мощности тип данных переполнение, неверные результаты могут храниться без возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="0d255-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="0d255-114">Чтобы задать дополнительные сведения в Visual Studio интегрированной среде разработки</span><span class="sxs-lookup"><span data-stu-id="0d255-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="0d255-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="0d255-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0d255-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0d255-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="0d255-117">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="0d255-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="0d255-118">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="0d255-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0d255-119">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="0d255-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="0d255-120">4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.</span><span class="sxs-lookup"><span data-stu-id="0d255-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0d255-121">Пример</span><span class="sxs-lookup"><span data-stu-id="0d255-121">Example</span></span>  
 <span data-ttu-id="0d255-122">Следующий код компилирует `Test.vb` и отключает проверку переполнения целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="0d255-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d255-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0d255-123">See Also</span></span>  
 [<span data-ttu-id="0d255-124">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="0d255-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0d255-125">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="0d255-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
