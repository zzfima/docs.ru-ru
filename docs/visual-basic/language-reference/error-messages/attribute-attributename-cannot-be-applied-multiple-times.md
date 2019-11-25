---
title: Атрибут <attributename> не может применяться многократно
ms.date: 07/20/2015
f1_keywords:
- bc30663
- vbc30663
helpviewer_keywords:
- BC30663
ms.assetid: 3760e7ff-7238-40a1-8676-77d858a64fc0
ms.openlocfilehash: f2f4dc428a247275f9919c4a8b6e6944a558eef0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968229"
---
# <a name="attribute-attributename-cannot-be-applied-multiple-times"></a><span data-ttu-id="36189-102">Атрибут "\<AttributeName >" не может применяться несколько раз</span><span class="sxs-lookup"><span data-stu-id="36189-102">Attribute '\<attributename>' cannot be applied multiple times</span></span>

<span data-ttu-id="36189-103">Атрибут можно применить только один раз.</span><span class="sxs-lookup"><span data-stu-id="36189-103">The attribute can only be applied once.</span></span> <span data-ttu-id="36189-104">Атрибут `AttributeUsage` определяет, может ли атрибут быть применен более одного раза.</span><span class="sxs-lookup"><span data-stu-id="36189-104">The `AttributeUsage` attribute determines whether an attribute can be applied more than once.</span></span>  
  
 <span data-ttu-id="36189-105">**Идентификатор ошибки:** BC30663</span><span class="sxs-lookup"><span data-stu-id="36189-105">**Error ID:** BC30663</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="36189-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="36189-106">To correct this error</span></span>  
  
1. <span data-ttu-id="36189-107">Убедитесь, что атрибут применяется только один раз.</span><span class="sxs-lookup"><span data-stu-id="36189-107">Make sure the attribute is only applied once.</span></span>  
  
2. <span data-ttu-id="36189-108">При использовании настраиваемых атрибутов, которые вы разработали, рассмотрите возможность изменения атрибута `AttributeUsage`, чтобы разрешить использование нескольких атрибутов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="36189-108">If you are using custom attributes you developed, consider changing their `AttributeUsage` attribute to allow multiple attribute usage, as with the following example.</span></span>  
  
```vb  
<AttributeUsage(AllowMultiple := True)>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36189-109">См. также</span><span class="sxs-lookup"><span data-stu-id="36189-109">See also</span></span>

- <xref:System.AttributeUsageAttribute>
- [<span data-ttu-id="36189-110">Создание настраиваемых атрибутов</span><span class="sxs-lookup"><span data-stu-id="36189-110">Creating Custom Attributes</span></span>](../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="36189-111">AttributeUsage</span><span class="sxs-lookup"><span data-stu-id="36189-111">AttributeUsage</span></span>](../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
