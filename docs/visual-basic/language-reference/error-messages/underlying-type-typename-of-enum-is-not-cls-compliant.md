---
title: Базовый тип <typename> перечисления несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 636fcc36e7bac52467998dc9c59f14ba1bedead3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831492"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a><span data-ttu-id="f5750-102">Базовый тип \<typename > перечисления несовместим с CLS</span><span class="sxs-lookup"><span data-stu-id="f5750-102">Underlying type \<typename> of Enum is not CLS-compliant</span></span>
<span data-ttu-id="f5750-103">Тип данных, указанный для этого перечисления не является частью [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="f5750-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="f5750-104">Это не ошибка в компоненте, поскольку [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и Visual Basic поддерживает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="f5750-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and Visual Basic support this data type.</span></span> <span data-ttu-id="f5750-105">Тем не менее другой компонент, написанный в строго CLS-совместимого кода могут не поддерживать этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="f5750-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="f5750-106">Такой компонент не может иметь возможность успешно взаимодействовать с данным компонентом.</span><span class="sxs-lookup"><span data-stu-id="f5750-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="f5750-107">Следующие типы данных Visual Basic не являются CLS-совместимыми:</span><span class="sxs-lookup"><span data-stu-id="f5750-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="f5750-108">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="f5750-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="f5750-109">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="f5750-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="f5750-110">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="f5750-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="f5750-111">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="f5750-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="f5750-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="f5750-112">By default, this message is a warning.</span></span> <span data-ttu-id="f5750-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f5750-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f5750-114">**Идентификатор ошибки:** BC40032</span><span class="sxs-lookup"><span data-stu-id="f5750-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5750-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f5750-115">To correct this error</span></span>  
  
-   <span data-ttu-id="f5750-116">Если компонент взаимодействует только с другими [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] компонентов, или не взаимодействует с любых других компонентов, не нужно ничего менять.</span><span class="sxs-lookup"><span data-stu-id="f5750-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="f5750-117">При взаимодействии с компонентом, не написаны для [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], можно определить, либо через отражение или из документации, является ли он поддерживает этот тип данных.</span><span class="sxs-lookup"><span data-stu-id="f5750-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="f5750-118">В этом случае ничего менять не нужно.</span><span class="sxs-lookup"><span data-stu-id="f5750-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="f5750-119">При взаимодействии с компонентом, который не поддерживает этот тип данных, его необходимо заменить на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="f5750-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="f5750-120">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="f5750-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="f5750-121">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="f5750-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="f5750-122">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5750-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="f5750-123">Например, данные типа `uint` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="f5750-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="f5750-124">Если вы передаете 16-разрядного аргумента такому компоненту, объявите его как `UShort` вместо `UInteger` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f5750-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5750-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f5750-125">See also</span></span>

- <span data-ttu-id="f5750-126">[Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md) (Отражение (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="f5750-126">[Reflection (Visual Basic)](../../programming-guide/concepts/reflection.md)</span></span>
- [<span data-ttu-id="f5750-127">Отражение</span><span class="sxs-lookup"><span data-stu-id="f5750-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
