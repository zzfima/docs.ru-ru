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
ms.openlocfilehash: 4c1be34cf76cfb12ea1e3b3246e9e0bc26199c24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687964"
---
# <a name="-removeintchecks"></a><span data-ttu-id="7c5d3-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="7c5d3-102">-removeintchecks</span></span>
<span data-ttu-id="7c5d3-103">Включает проверка ошибки переполнения для целочисленных операций или отключить.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c5d3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c5d3-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7c5d3-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="7c5d3-105">Arguments</span></span>  
  
|<span data-ttu-id="7c5d3-106">Термин</span><span class="sxs-lookup"><span data-stu-id="7c5d3-106">Term</span></span>|<span data-ttu-id="7c5d3-107">Определение</span><span class="sxs-lookup"><span data-stu-id="7c5d3-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="7c5d3-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="7c5d3-108">`+` &#124; `-`</span></span>|<span data-ttu-id="7c5d3-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-109">Optional.</span></span> <span data-ttu-id="7c5d3-110">`-removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="7c5d3-111">Значение по умолчанию — `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="7c5d3-112">Указание `-removeintchecks` или `-removeintchecks+` предотвращает проверки на наличие ошибок и выполнения вычислений целое число быстрее.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="7c5d3-113">Тем не менее, без проверки ошибок, и если что случается емкости типа данных, неверные результаты могут храниться без возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="7c5d3-114">Чтобы задать - removeintchecks в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7c5d3-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="7c5d3-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="7c5d3-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="7c5d3-117">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="7c5d3-118">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="7c5d3-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="7c5d3-119">4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7c5d3-120">Пример</span><span class="sxs-lookup"><span data-stu-id="7c5d3-120">Example</span></span>  
 <span data-ttu-id="7c5d3-121">Следующий код компилирует `Test.vb` и отключает проверку переполнения для целочисленных.</span><span class="sxs-lookup"><span data-stu-id="7c5d3-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c5d3-122">См. также</span><span class="sxs-lookup"><span data-stu-id="7c5d3-122">See also</span></span>
- [<span data-ttu-id="7c5d3-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="7c5d3-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="7c5d3-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="7c5d3-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
