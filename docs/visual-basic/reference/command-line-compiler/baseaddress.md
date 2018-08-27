---
title: -baseaddress
ms.date: 08/09/2018
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
ms.openlocfilehash: 6331a55bb1d20b5804605db103dcfd2997e348d9
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2018
ms.locfileid: "42930446"
---
# <a name="-baseaddress"></a><span data-ttu-id="c164b-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="c164b-102">-baseaddress</span></span>
<span data-ttu-id="c164b-103">Задает базовый адрес по умолчанию при создании библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="c164b-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c164b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c164b-104">Syntax</span></span>  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="c164b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="c164b-105">Arguments</span></span>  
  
|<span data-ttu-id="c164b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="c164b-106">Term</span></span>|<span data-ttu-id="c164b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="c164b-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="c164b-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="c164b-108">Required.</span></span> <span data-ttu-id="c164b-109">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="c164b-109">The base address for the DLL.</span></span> <span data-ttu-id="c164b-110">Необходимо указать этот адрес в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="c164b-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c164b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c164b-111">Remarks</span></span>  
 <span data-ttu-id="c164b-112">Базовый адрес по умолчанию для библиотеки DLL задается [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c164b-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="c164b-113">Имейте в виду, что младшее слово этого адреса округляется.</span><span class="sxs-lookup"><span data-stu-id="c164b-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="c164b-114">Например задать значение 0x11110001 округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="c164b-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="c164b-115">Чтобы завершить процесс подписи для библиотеки DLL, используйте `–R` средства строгих имен (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="c164b-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="c164b-116">Этот параметр учитывается, если целевой объект не представляет собой библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="c164b-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="c164b-117">Чтобы задать - baseaddress в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c164b-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="c164b-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="c164b-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c164b-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="c164b-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="c164b-120">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="c164b-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c164b-121">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="c164b-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="c164b-122">4.  Измените значение в **базовый адрес DLL:** поле.</span><span class="sxs-lookup"><span data-stu-id="c164b-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="c164b-123">**Примечание:** **базовый адрес DLL:** поле только для чтения, если целевой объект представляет собой библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="c164b-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c164b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="c164b-124">See Also</span></span>  
 [<span data-ttu-id="c164b-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="c164b-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c164b-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c164b-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="c164b-127">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="c164b-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="c164b-128">[Sn.exe (средство строгих имен)] [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="c164b-128">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
