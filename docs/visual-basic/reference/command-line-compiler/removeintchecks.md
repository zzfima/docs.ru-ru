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
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005226"
---
# <a name="-removeintchecks"></a><span data-ttu-id="748d6-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="748d6-102">-removeintchecks</span></span>
<span data-ttu-id="748d6-103">Включает или выключает проверку переполнения для целочисленных операций.</span><span class="sxs-lookup"><span data-stu-id="748d6-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="748d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="748d6-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="748d6-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="748d6-105">Arguments</span></span>  
  
|<span data-ttu-id="748d6-106">Термин</span><span class="sxs-lookup"><span data-stu-id="748d6-106">Term</span></span>|<span data-ttu-id="748d6-107">Определение</span><span class="sxs-lookup"><span data-stu-id="748d6-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="748d6-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="748d6-108">`+` &#124; `-`</span></span>|<span data-ttu-id="748d6-109">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="748d6-109">Optional.</span></span> <span data-ttu-id="748d6-110">Параметр `-removeintchecks-` приводит к тому, что компилятор проверяет все вычисления целых чисел на наличие ошибок переполнения.</span><span class="sxs-lookup"><span data-stu-id="748d6-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="748d6-111">Значение по умолчанию — `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="748d6-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="748d6-112">Указание `-removeintchecks` или `-removeintchecks+` предотвращает проверку ошибок и ускоряет вычисление целых чисел.</span><span class="sxs-lookup"><span data-stu-id="748d6-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="748d6-113">Однако без проверки ошибок и при переполняется ли емкость типа данных, могут быть сохранены неправильные результаты без возникновения ошибки.</span><span class="sxs-lookup"><span data-stu-id="748d6-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="748d6-114">Установка параметра-ремовеинтчеккс в интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="748d6-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="748d6-115">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="748d6-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="748d6-116">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="748d6-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="748d6-117">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="748d6-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="748d6-118">3.  Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="748d6-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="748d6-119">4.  Измените значение в поле **Удалить проверки переполнения целых чисел** .</span><span class="sxs-lookup"><span data-stu-id="748d6-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="748d6-120">Пример</span><span class="sxs-lookup"><span data-stu-id="748d6-120">Example</span></span>  
 <span data-ttu-id="748d6-121">Следующий код компилирует `Test.vb` и отключает проверку переполнения целых чисел.</span><span class="sxs-lookup"><span data-stu-id="748d6-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="748d6-122">См. также</span><span class="sxs-lookup"><span data-stu-id="748d6-122">See also</span></span>

- [<span data-ttu-id="748d6-123">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="748d6-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="748d6-124">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="748d6-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
