---
title: "Тип члена &#39; &lt;membername&gt;&#39; не является CLS-совместимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bc82714d25efbe9d379fff36f92261cf25a78862
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a><span data-ttu-id="595a1-102">Тип члена &#39; &lt;membername&gt;&#39; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="595a1-102">Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="595a1-103">Тип данных, указанный для этого элемента не является частью [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="595a1-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="595a1-104">Это не ошибка в компоненте, поскольку [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] поддерживает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="595a1-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] support this data type.</span></span> <span data-ttu-id="595a1-105">Тем не менее другой компонент, написанный в строго CLS-совместимого кода может не поддерживает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="595a1-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="595a1-106">Такой компонент может оказаться невозможным успешно взаимодействовать с данным компонентом.</span><span class="sxs-lookup"><span data-stu-id="595a1-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="595a1-107">Следующие типы данных [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не соответствуют CLS:</span><span class="sxs-lookup"><span data-stu-id="595a1-107">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="595a1-108">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="595a1-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="595a1-109">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="595a1-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="595a1-110">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="595a1-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="595a1-111">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="595a1-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="595a1-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="595a1-112">By default, this message is a warning.</span></span> <span data-ttu-id="595a1-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="595a1-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="595a1-114">**Идентификатор ошибки:** BC40025</span><span class="sxs-lookup"><span data-stu-id="595a1-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="595a1-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="595a1-115">To correct this error</span></span>  
  
-   <span data-ttu-id="595a1-116">Если компонент взаимодействует только с другими [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] компонентов, или не взаимодействует с любые другие компоненты, необходимо изменить все.</span><span class="sxs-lookup"><span data-stu-id="595a1-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="595a1-117">При взаимодействии с компонентом, не написаны для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], можно определить, либо через отражение или из документации, является ли он поддерживает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="595a1-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="595a1-118">В этом случае необходимо не вносите никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="595a1-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="595a1-119">При взаимодействии с компонентом, который не поддерживает этот тип данных, его необходимо заменить на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="595a1-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="595a1-120">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="595a1-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="595a1-121">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="595a1-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="595a1-122">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="595a1-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="595a1-123">Например, данные типа `uint` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="595a1-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="595a1-124">Если вы передаете 16-разрядного аргумента такому компоненту, объявите его как `UShort` вместо `UInteger` в управляемом [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] кода.</span><span class="sxs-lookup"><span data-stu-id="595a1-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="595a1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="595a1-125">See Also</span></span>  
 [<span data-ttu-id="595a1-126">Отражение</span><span class="sxs-lookup"><span data-stu-id="595a1-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
 
