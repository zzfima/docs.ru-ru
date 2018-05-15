---
title: -removeintchecks
ms.date: 03/13/2018
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26485fe2ba3f5647266147744cbe53f978694a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-removeintchecks"></a><span data-ttu-id="c8807-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="c8807-102">-removeintchecks</span></span>
<span data-ttu-id="c8807-103">Включает проверка ошибки переполнения для целочисленных операций или отключить.</span><span class="sxs-lookup"><span data-stu-id="c8807-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8807-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8807-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c8807-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c8807-105">Arguments</span></span>  
  
|<span data-ttu-id="c8807-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c8807-106">Term</span></span>|<span data-ttu-id="c8807-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c8807-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="c8807-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="c8807-108">`+` &#124; `-`</span></span>|<span data-ttu-id="c8807-109">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c8807-109">Optional.</span></span> <span data-ttu-id="c8807-110">`-removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения.</span><span class="sxs-lookup"><span data-stu-id="c8807-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="c8807-111">Значение по умолчанию — `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="c8807-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="c8807-112">Указание `-removeintchecks` или `-removeintchecks+` предотвращает проверку ошибок и осуществлять целочисленные вычисления быстрее.</span><span class="sxs-lookup"><span data-stu-id="c8807-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="c8807-113">Тем не менее, без проверки ошибок, и если производственные мощности тип данных переполнение, неверные результаты могут храниться без возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="c8807-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="c8807-114">Чтобы задать - removeintchecks в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c8807-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c8807-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c8807-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c8807-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c8807-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c8807-117">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="c8807-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c8807-118">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="c8807-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="c8807-119">4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.</span><span class="sxs-lookup"><span data-stu-id="c8807-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c8807-120">Пример</span><span class="sxs-lookup"><span data-stu-id="c8807-120">Example</span></span>  
 <span data-ttu-id="c8807-121">Следующий код компилирует `Test.vb` и отключает проверку переполнения целое число со знаком.</span><span class="sxs-lookup"><span data-stu-id="c8807-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8807-122">См. также</span><span class="sxs-lookup"><span data-stu-id="c8807-122">See Also</span></span>  
 [<span data-ttu-id="c8807-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c8807-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c8807-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c8807-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
