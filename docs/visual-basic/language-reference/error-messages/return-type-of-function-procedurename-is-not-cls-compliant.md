---
title: "Тип возвращаемого значения функции &#39; &lt;имя_процедуры&gt;&#39; не является CLS-совместимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords: BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16670521ec09ae9cab28bf6ca4705c131fd84701
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a><span data-ttu-id="c9324-102">Тип возвращаемого значения функции &#39; &lt;имя_процедуры&gt;&#39; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="c9324-102">Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="c9324-103">Объект `Function` процедура помечена как `<CLSCompliant(True)>` , но возвращает тип, который помечен как `<CLSCompliant(False)>`, не помечен или не квалифицирован, так как он имеет несоответствующий тип.</span><span class="sxs-lookup"><span data-stu-id="c9324-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="c9324-104">Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), процедура должна использовать только типы, соответствующие CLS.</span><span class="sxs-lookup"><span data-stu-id="c9324-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="c9324-105">Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="c9324-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="c9324-106">Следующие типы данных [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не соответствуют CLS:</span><span class="sxs-lookup"><span data-stu-id="c9324-106">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="c9324-107">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="c9324-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="c9324-108">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="c9324-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="c9324-109">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="c9324-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="c9324-110">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="c9324-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="c9324-111">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="c9324-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="c9324-112">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="c9324-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="c9324-113">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="c9324-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="c9324-114">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="c9324-114">By default, this message is a warning.</span></span> <span data-ttu-id="c9324-115">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c9324-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c9324-116">**Идентификатор ошибки:** BC40027</span><span class="sxs-lookup"><span data-stu-id="c9324-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c9324-117">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c9324-117">To correct this error</span></span>  
  
-   <span data-ttu-id="c9324-118">Если `Function` процедура должна возвращать этот конкретный тип, удалите <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c9324-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="c9324-119">Процедура не может соответствовать CLS.</span><span class="sxs-lookup"><span data-stu-id="c9324-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="c9324-120">Если `Function` процедура должна быть CLS-совместимыми, измените тип возвращаемого значения на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="c9324-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="c9324-121">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="c9324-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="c9324-122">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="c9324-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="c9324-123">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c9324-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="c9324-124">Например, данные типа `int` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="c9324-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="c9324-125">Если возвращается 16-разрядное целое число такому компоненту, объявите его как `Short` вместо `Integer` в управляемом [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] кода.</span><span class="sxs-lookup"><span data-stu-id="c9324-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9324-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c9324-126">See Also</span></span>  
 [<span data-ttu-id="c9324-127">\<PAVE НАД > написание CLS-совместимого кода</span><span class="sxs-lookup"><span data-stu-id="c9324-127">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
