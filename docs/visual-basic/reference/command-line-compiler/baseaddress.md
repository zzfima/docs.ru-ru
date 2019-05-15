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
ms.openlocfilehash: e8dfe95ef3385635f5839ecc96047911544a256e
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591449"
---
# <a name="-baseaddress"></a><span data-ttu-id="1c79c-102">-baseaddress</span><span class="sxs-lookup"><span data-stu-id="1c79c-102">-baseaddress</span></span>
<span data-ttu-id="1c79c-103">Задает базовый адрес по умолчанию при создании библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="1c79c-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c79c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c79c-104">Syntax</span></span>  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="1c79c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="1c79c-105">Arguments</span></span>  
  
|<span data-ttu-id="1c79c-106">Термин</span><span class="sxs-lookup"><span data-stu-id="1c79c-106">Term</span></span>|<span data-ttu-id="1c79c-107">Определение</span><span class="sxs-lookup"><span data-stu-id="1c79c-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="1c79c-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="1c79c-108">Required.</span></span> <span data-ttu-id="1c79c-109">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="1c79c-109">The base address for the DLL.</span></span> <span data-ttu-id="1c79c-110">Необходимо указать этот адрес в шестнадцатеричном формате.</span><span class="sxs-lookup"><span data-stu-id="1c79c-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c79c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c79c-111">Remarks</span></span>  
 <span data-ttu-id="1c79c-112">Базовый адрес по умолчанию для библиотеки DLL задается в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1c79c-112">The default base address for a DLL is set by the .NET Framework.</span></span>  
  
 <span data-ttu-id="1c79c-113">Имейте в виду, что младшее слово этого адреса округляется.</span><span class="sxs-lookup"><span data-stu-id="1c79c-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="1c79c-114">Например задать значение 0x11110001 округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="1c79c-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="1c79c-115">Чтобы завершить процесс подписи для библиотеки DLL, используйте `–R` средства строгих имен (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="1c79c-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="1c79c-116">Этот параметр учитывается, если целевой объект не представляет собой библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="1c79c-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="1c79c-117">Чтобы задать - baseaddress в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1c79c-117">To set -baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="1c79c-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="1c79c-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="1c79c-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1c79c-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="1c79c-120">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="1c79c-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="1c79c-121">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="1c79c-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="1c79c-122">4.  Измените значение в **базовый адрес DLL:** поле.</span><span class="sxs-lookup"><span data-stu-id="1c79c-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="1c79c-123">**Примечание.**      **Базовый адрес DLL:** поле только для чтения, если целевой объект представляет собой библиотеку DLL.</span><span class="sxs-lookup"><span data-stu-id="1c79c-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c79c-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1c79c-124">See also</span></span>

- [<span data-ttu-id="1c79c-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="1c79c-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="1c79c-126">-target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c79c-126">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
- [<span data-ttu-id="1c79c-127">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="1c79c-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="1c79c-128">[Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="1c79c-128">[Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
