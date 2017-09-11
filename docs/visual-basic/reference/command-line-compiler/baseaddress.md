---
title: "/ baseaddress | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
dev_langs:
- VB
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
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
ms.openlocfilehash: 5687f119a57e0e54eca4df8f91fdf5e8b2775f82
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="baseaddress"></a><span data-ttu-id="eb17b-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="eb17b-102">/baseaddress</span></span>
<span data-ttu-id="eb17b-103">Задает базовый адрес при создании библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="eb17b-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb17b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb17b-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="eb17b-105">Аргументы</span><span class="sxs-lookup"><span data-stu-id="eb17b-105">Arguments</span></span>  
  
|<span data-ttu-id="eb17b-106">Термин</span><span class="sxs-lookup"><span data-stu-id="eb17b-106">Term</span></span>|<span data-ttu-id="eb17b-107">Определение</span><span class="sxs-lookup"><span data-stu-id="eb17b-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="eb17b-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="eb17b-108">Required.</span></span> <span data-ttu-id="eb17b-109">Базовый адрес библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="eb17b-109">The base address for the DLL.</span></span> <span data-ttu-id="eb17b-110">Этот адрес должен указан как шестнадцатеричное число.</span><span class="sxs-lookup"><span data-stu-id="eb17b-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb17b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb17b-111">Remarks</span></span>  
 <span data-ttu-id="eb17b-112">Базовый адрес библиотеки DLL по умолчанию задается [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb17b-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
 <span data-ttu-id="eb17b-113">Имейте в виду, что младшее слово адреса округляется.</span><span class="sxs-lookup"><span data-stu-id="eb17b-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="eb17b-114">Например если будет указано 0x11110001, оно округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="eb17b-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="eb17b-115">Для подписывания библиотеки DLL используйте `–R` параметр инструмента строгого именования (Sn.exe).</span><span class="sxs-lookup"><span data-stu-id="eb17b-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="eb17b-116">Этот параметр учитывается, если целевой объект не является библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="eb17b-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="eb17b-117">Установка/baseaddress в Интегрированной среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="eb17b-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="eb17b-118">1.  Выберите проект в **Обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="eb17b-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="eb17b-119">На **проекта** меню, щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="eb17b-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="eb17b-120">Дополнительные сведения см. в разделе [Знакомство с конструктором проектов](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="eb17b-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="eb17b-121">2.  Откройте вкладку **Компиляция**.</span><span class="sxs-lookup"><span data-stu-id="eb17b-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="eb17b-122">3.  Нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="eb17b-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="eb17b-123">4.  Измените значение в **базовый адрес DLL:** поле.</span><span class="sxs-lookup"><span data-stu-id="eb17b-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="eb17b-124">**Примечание:** **базовый адрес DLL:** поле доступно только для чтения, если целевым является не DLL.</span><span class="sxs-lookup"><span data-stu-id="eb17b-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb17b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="eb17b-125">See Also</span></span>  
 <span data-ttu-id="eb17b-126">[Компилятор командной строки Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="eb17b-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="eb17b-127"> [/ Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="eb17b-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="eb17b-128"> [Примеры командных строк компиляции](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="eb17b-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="eb17b-129"> [Sn.exe (средство строгих имен)](https://msdn.microsoft.com/library/k5b5tt23)</span><span class="sxs-lookup"><span data-stu-id="eb17b-129"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23)</span></span>
