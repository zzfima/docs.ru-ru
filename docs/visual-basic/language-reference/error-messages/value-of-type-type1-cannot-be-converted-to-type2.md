---
title: Значение типа &#39;тип1&#39; невозможно преобразовать в &#39;тип2&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords:
- BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
ms.openlocfilehash: 657e0feb675e15b9ece00d40c3d1ebe932a29099
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568297"
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="a37ee-102">Значение типа &#39;тип1&#39; невозможно преобразовать в &#39;тип2&#39;</span><span class="sxs-lookup"><span data-stu-id="a37ee-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="a37ee-103">Значение типа «тип1» не может быть преобразован в «тип2».</span><span class="sxs-lookup"><span data-stu-id="a37ee-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="a37ee-104">Можно использовать свойство «Value», чтобы получить строковое значение первого элемента "\<Родительскийэлемент >".</span><span class="sxs-lookup"><span data-stu-id="a37ee-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="a37ee-105">Предпринята попытка неявного приведения XML-литерала к определенному типу.</span><span class="sxs-lookup"><span data-stu-id="a37ee-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="a37ee-106">XML-литерал не может быть неявно приведен к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="a37ee-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="a37ee-107">**Идентификатор ошибки:** BC31194</span><span class="sxs-lookup"><span data-stu-id="a37ee-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a37ee-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a37ee-108">To correct this error</span></span>  
  
-   <span data-ttu-id="a37ee-109">Используйте свойство `Value` XML-литерала для ссылки на его значение как на `String`.</span><span class="sxs-lookup"><span data-stu-id="a37ee-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="a37ee-110">Используйте функцию `CType` , другую функцию преобразования типа или класс <xref:System.Convert> для приведения значения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="a37ee-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a37ee-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a37ee-111">See also</span></span>
- <xref:System.Convert>
- [<span data-ttu-id="a37ee-112">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="a37ee-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="a37ee-113">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="a37ee-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)
- [<span data-ttu-id="a37ee-114">XML</span><span class="sxs-lookup"><span data-stu-id="a37ee-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
