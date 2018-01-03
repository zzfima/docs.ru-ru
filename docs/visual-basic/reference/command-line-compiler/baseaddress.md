---
title: /baseaddress
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1ad39acdec92667fbb0848a1c64c567b504dcb67
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="baseaddress"></a><span data-ttu-id="f4479-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="f4479-102">/baseaddress</span></span>
<span data-ttu-id="f4479-103">Задает базовый адрес при создании библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="f4479-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4479-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4479-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="f4479-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="f4479-105">Arguments</span></span>  
  
|<span data-ttu-id="f4479-106">Термин</span><span class="sxs-lookup"><span data-stu-id="f4479-106">Term</span></span>|<span data-ttu-id="f4479-107">Определение</span><span class="sxs-lookup"><span data-stu-id="f4479-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="f4479-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="f4479-108">Required.</span></span> <span data-ttu-id="f4479-109">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="f4479-109">The base address for the DLL.</span></span> <span data-ttu-id="f4479-110">Этот адрес должен указан как шестнадцатеричное число.</span><span class="sxs-lookup"><span data-stu-id="f4479-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4479-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4479-111">Remarks</span></span>  
 <span data-ttu-id="f4479-112">Базовый адрес библиотеки DLL по умолчанию задается [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4479-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="f4479-113">Имейте в виду, что младшее слово адреса округляется.</span><span class="sxs-lookup"><span data-stu-id="f4479-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="f4479-114">Например если будет указано 0x11110001, оно округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="f4479-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="f4479-115">Чтобы завершить процесс подписи для библиотеки DLL, используйте `–R` средства строгих имен (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="f4479-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="f4479-116">Этот параметр учитывается, если целевой объект не является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="f4479-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="f4479-117">Задание/baseaddress в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f4479-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="f4479-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="f4479-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f4479-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f4479-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="f4479-120">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="f4479-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="f4479-121">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="f4479-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="f4479-122">4.  Измените значение в **базовый адрес DLL:** поле.</span><span class="sxs-lookup"><span data-stu-id="f4479-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="f4479-123">**Примечание:** **базовый адрес DLL:** поле доступно только для чтения, если целевой объект является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="f4479-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4479-124">См. также</span><span class="sxs-lookup"><span data-stu-id="f4479-124">See Also</span></span>  
 [<span data-ttu-id="f4479-125">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="f4479-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="f4479-126">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4479-126">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="f4479-127">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="f4479-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="f4479-128">[Sn.exe (средство строгих имен)] [Sn.exe (средство строгих имен)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="f4479-128">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
