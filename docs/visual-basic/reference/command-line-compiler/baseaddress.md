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
ms.openlocfilehash: 8be88bf4834ca58b1fe708eb1ef7188c583fef0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="baseaddress"></a><span data-ttu-id="efc0c-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="efc0c-102">/baseaddress</span></span>
<span data-ttu-id="efc0c-103">Задает базовый адрес при создании библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="efc0c-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efc0c-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="efc0c-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="efc0c-105">Arguments</span></span>  
  
|<span data-ttu-id="efc0c-106">Термин</span><span class="sxs-lookup"><span data-stu-id="efc0c-106">Term</span></span>|<span data-ttu-id="efc0c-107">Определение</span><span class="sxs-lookup"><span data-stu-id="efc0c-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="efc0c-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="efc0c-108">Required.</span></span> <span data-ttu-id="efc0c-109">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="efc0c-109">The base address for the DLL.</span></span> <span data-ttu-id="efc0c-110">Этот адрес должен указан как шестнадцатеричное число.</span><span class="sxs-lookup"><span data-stu-id="efc0c-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efc0c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="efc0c-111">Remarks</span></span>  
 <span data-ttu-id="efc0c-112">Базовый адрес библиотеки DLL по умолчанию задается [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="efc0c-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="efc0c-113">Имейте в виду, что младшее слово адреса округляется.</span><span class="sxs-lookup"><span data-stu-id="efc0c-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="efc0c-114">Например если будет указано 0x11110001, оно округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="efc0c-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="efc0c-115">Чтобы завершить процесс подписи для библиотеки DLL, используйте `–R` средства строгих имен (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="efc0c-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="efc0c-116">Этот параметр учитывается, если целевой объект не является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="efc0c-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="efc0c-117">Задание/baseaddress в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="efc0c-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="efc0c-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="efc0c-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="efc0c-119">В меню **Проект** выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="efc0c-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="efc0c-120">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="efc0c-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="efc0c-121">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="efc0c-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="efc0c-122">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="efc0c-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="efc0c-123">4.  Измените значение в **базовый адрес DLL:** поле.</span><span class="sxs-lookup"><span data-stu-id="efc0c-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="efc0c-124">**Примечание:** **базовый адрес DLL:** поле доступно только для чтения, если целевой объект является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="efc0c-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efc0c-125">См. также</span><span class="sxs-lookup"><span data-stu-id="efc0c-125">See Also</span></span>  
 [<span data-ttu-id="efc0c-126">Компилятор Visual Basic с интерфейсом командной строки</span><span class="sxs-lookup"><span data-stu-id="efc0c-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="efc0c-127">/ Target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efc0c-127">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="efc0c-128">Примеры командных строк компиляции</span><span class="sxs-lookup"><span data-stu-id="efc0c-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="efc0c-129">Sn.exe (средство строгих имен)</span><span class="sxs-lookup"><span data-stu-id="efc0c-129">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)
