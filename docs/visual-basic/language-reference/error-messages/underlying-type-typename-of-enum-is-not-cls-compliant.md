---
title: "Базовый тип &lt;typename&gt; перечисления не является CLS-совместимым | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40032
- bc40032
dev_langs:
- VB
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
caps.latest.revision: 8
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
ms.openlocfilehash: 51628d2232b9e1c89e7fbf931ef0d6602f7cddc9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a><span data-ttu-id="ae43f-102">Базовый тип &lt;typename&gt; перечисления не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="ae43f-102">Underlying type &lt;typename&gt; of Enum is not CLS-compliant</span></span>
<span data-ttu-id="ae43f-103">Тип данных, указанный для этого перечисления не является частью [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span><span class="sxs-lookup"><span data-stu-id="ae43f-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS).</span></span> <span data-ttu-id="ae43f-104">Это не ошибка в компоненте, поскольку [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] поддерживает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="ae43f-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] and [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] support this data type.</span></span> <span data-ttu-id="ae43f-105">Однако другой компонент, написанный в строго CLS-совместимом коде могут не поддерживать этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="ae43f-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="ae43f-106">Такой компонент может оказаться невозможным успешно взаимодействовать с данным компонентом.</span><span class="sxs-lookup"><span data-stu-id="ae43f-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="ae43f-107">Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не соответствуют CLS:</span><span class="sxs-lookup"><span data-stu-id="ae43f-107">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="ae43f-108">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="ae43f-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="ae43f-109">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="ae43f-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="ae43f-110">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="ae43f-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="ae43f-111">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="ae43f-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="ae43f-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="ae43f-112">By default, this message is a warning.</span></span> <span data-ttu-id="ae43f-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ae43f-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ae43f-114">**Идентификатор ошибки:** BC40032</span><span class="sxs-lookup"><span data-stu-id="ae43f-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ae43f-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ae43f-115">To correct this error</span></span>  
  
-   <span data-ttu-id="ae43f-116">Если компонент взаимодействует только с другими [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] компонентов, или не взаимодействует с другие компоненты, не нужно ничего менять.</span><span class="sxs-lookup"><span data-stu-id="ae43f-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="ae43f-117">При взаимодействии с компонентом, не записанном для [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], можно определить, либо через отражение, или из документации, является ли он поддерживает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="ae43f-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="ae43f-118">В этом случае не требуется ничего менять.</span><span class="sxs-lookup"><span data-stu-id="ae43f-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="ae43f-119">При взаимодействии с компонентом, который не поддерживает этот тип данных, его необходимо заменить на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="ae43f-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="ae43f-120">Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="ae43f-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="ae43f-121">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="ae43f-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="ae43f-122">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae43f-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span> <span data-ttu-id="ae43f-123">Например, данные типа `uint` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="ae43f-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="ae43f-124">При передаче 16-разрядного аргумента такому компоненту, следует объявить ее как `UShort` вместо `UInteger` в управляемом [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] кода.</span><span class="sxs-lookup"><span data-stu-id="ae43f-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae43f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ae43f-125">See Also</span></span>  
 <span data-ttu-id="ae43f-126">[Отражение](http://msdn.microsoft.com/library/5d1d1bcf-08de-4d0b-97a8-912d17c00f26) </span><span class="sxs-lookup"><span data-stu-id="ae43f-126">[Reflection](http://msdn.microsoft.com/library/5d1d1bcf-08de-4d0b-97a8-912d17c00f26) </span></span>  
<span data-ttu-id="ae43f-127"> [Отражение](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775) </span><span class="sxs-lookup"><span data-stu-id="ae43f-127"> [Reflection](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775) </span></span>  
<span data-ttu-id="ae43f-128"> [\<PAVE НАД настроек написание CLS-совместимого кода](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span><span class="sxs-lookup"><span data-stu-id="ae43f-128"> [\<PAVE OVER> Writing CLS-Compliant Code](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)</span></span>
