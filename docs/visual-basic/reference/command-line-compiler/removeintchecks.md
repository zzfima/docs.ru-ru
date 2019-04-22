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
ms.openlocfilehash: c086a031d5cef4563a6769e7683dcb1110b8fe49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822730"
---
# <a name="-removeintchecks"></a><span data-ttu-id="d7418-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="d7418-102">-removeintchecks</span></span>
<span data-ttu-id="d7418-103">Включает проверка ошибки переполнения для целочисленных операций или отключить.</span><span class="sxs-lookup"><span data-stu-id="d7418-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7418-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7418-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7418-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="d7418-105">Arguments</span></span>  
  
|<span data-ttu-id="d7418-106">Термин</span><span class="sxs-lookup"><span data-stu-id="d7418-106">Term</span></span>|<span data-ttu-id="d7418-107">Определение</span><span class="sxs-lookup"><span data-stu-id="d7418-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d7418-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d7418-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d7418-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="d7418-109">Optional.</span></span> <span data-ttu-id="d7418-110">`-removeintchecks-` Предписывает компилятору проверять все целочисленные вычисления на наличие ошибок переполнения.</span><span class="sxs-lookup"><span data-stu-id="d7418-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="d7418-111">Значение по умолчанию — `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="d7418-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="d7418-112">Указание `-removeintchecks` или `-removeintchecks+` предотвращает проверки на наличие ошибок и выполнения вычислений целое число быстрее.</span><span class="sxs-lookup"><span data-stu-id="d7418-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="d7418-113">Тем не менее, без проверки ошибок, и если что случается емкости типа данных, неверные результаты могут храниться без возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="d7418-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="d7418-114">Чтобы задать - removeintchecks в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d7418-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d7418-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="d7418-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d7418-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d7418-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d7418-117">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="d7418-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d7418-118">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="d7418-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="d7418-119">4.  Изменить значение **удалить проверки переполнения для целочисленных** поле.</span><span class="sxs-lookup"><span data-stu-id="d7418-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d7418-120">Пример</span><span class="sxs-lookup"><span data-stu-id="d7418-120">Example</span></span>  
 <span data-ttu-id="d7418-121">Следующий код компилирует `Test.vb` и отключает проверку переполнения для целочисленных.</span><span class="sxs-lookup"><span data-stu-id="d7418-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7418-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d7418-122">See also</span></span>

- [<span data-ttu-id="d7418-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="d7418-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="d7418-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="d7418-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
