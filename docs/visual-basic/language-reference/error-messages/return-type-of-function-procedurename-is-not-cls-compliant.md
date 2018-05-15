---
title: Тип возвращаемого значения функции &#39; &lt;имя_процедуры&gt; &#39; не является CLS-совместимым
ms.date: 07/20/2015
f1_keywords:
- bc40027
- vbc40027
helpviewer_keywords:
- BC40027
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
ms.openlocfilehash: b7704ee63031c38f708a2243e84b880c25fcf819
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="return-type-of-function-39ltprocedurenamegt39-is-not-cls-compliant"></a><span data-ttu-id="907a3-102">Тип возвращаемого значения функции &#39; &lt;имя_процедуры&gt; &#39; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="907a3-102">Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="907a3-103">Объект `Function` процедура помечена как `<CLSCompliant(True)>` , но возвращает тип, который помечен как `<CLSCompliant(False)>`, не помечен или не квалифицирован, так как он имеет несоответствующий тип.</span><span class="sxs-lookup"><span data-stu-id="907a3-103">A `Function` procedure is marked as `<CLSCompliant(True)>` but returns a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="907a3-104">Для соответствия требованиям, описанным в статье [Независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), процедура должна использовать только типы, соответствующие CLS.</span><span class="sxs-lookup"><span data-stu-id="907a3-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="907a3-105">Это касается типов параметров, типа возвращаемого значения и типов всех локальных переменных.</span><span class="sxs-lookup"><span data-stu-id="907a3-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="907a3-106">Следующие типы данных Visual Basic не являются CLS-совместимыми:</span><span class="sxs-lookup"><span data-stu-id="907a3-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="907a3-107">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="907a3-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="907a3-108">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="907a3-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="907a3-109">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="907a3-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="907a3-110">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="907a3-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="907a3-111">При применении атрибута <xref:System.CLSCompliantAttribute> к программному элементу вы задаете для параметра `isCompliant` атрибута значение `True` или `False` , чтобы указать совместимость или несовместимость.</span><span class="sxs-lookup"><span data-stu-id="907a3-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="907a3-112">Для этого параметра нет значения по умолчанию, и вы должны предоставить его.</span><span class="sxs-lookup"><span data-stu-id="907a3-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="907a3-113">Если вы не применяете <xref:System.CLSCompliantAttribute> к элементу, он считается несовместимым.</span><span class="sxs-lookup"><span data-stu-id="907a3-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="907a3-114">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="907a3-114">By default, this message is a warning.</span></span> <span data-ttu-id="907a3-115">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="907a3-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="907a3-116">**Идентификатор ошибки:** BC40027</span><span class="sxs-lookup"><span data-stu-id="907a3-116">**Error ID:** BC40027</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="907a3-117">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="907a3-117">To correct this error</span></span>  
  
-   <span data-ttu-id="907a3-118">Если `Function` процедура должна возвращать этот конкретный тип, удалите <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="907a3-118">If the `Function` procedure must return this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="907a3-119">Процедура не может соответствовать CLS.</span><span class="sxs-lookup"><span data-stu-id="907a3-119">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="907a3-120">Если `Function` процедура должна быть CLS-совместимыми, измените тип возвращаемого значения на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="907a3-120">If the `Function` procedure must be CLS-compliant, change the return type to the closest CLS-compliant type.</span></span> <span data-ttu-id="907a3-121">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="907a3-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="907a3-122">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="907a3-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="907a3-123">При взаимодействии с объектами службы автоматизации или COM-объектами помните, что длина данных некоторых типов отличается от длины данных в [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="907a3-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="907a3-124">Например, данные типа `int` часто являются 16-битными в других средах.</span><span class="sxs-lookup"><span data-stu-id="907a3-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="907a3-125">Если возвращается 16-разрядное целое число такому компоненту, объявите его как `Short` вместо `Integer` в управляемом коде Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="907a3-125">If you are returning a 16-bit integer to such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>