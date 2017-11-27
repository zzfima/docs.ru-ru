---
title: "Значение типа &#39; тип 1 &#39; Невозможно преобразовать в &#39; тип 2 &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31194
- bc31194
helpviewer_keywords: BC31194
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: efa6fcd4d996fb3277cc4cac2af16a86a2d65977
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="value-of-type-39type139-cannot-be-converted-to-39type239"></a><span data-ttu-id="1eb40-102">Значение типа &#39; тип 1 &#39; Невозможно преобразовать в &#39; тип 2 &#39;</span><span class="sxs-lookup"><span data-stu-id="1eb40-102">Value of type &#39;type1&#39; cannot be converted to &#39;type2&#39;</span></span>
<span data-ttu-id="1eb40-103">Не удается преобразовать значение типа «тип1» в «тип2».</span><span class="sxs-lookup"><span data-stu-id="1eb40-103">Value of type 'type1' cannot be converted to 'type2'.</span></span> <span data-ttu-id="1eb40-104">Свойство «Значение» для получения строкового значения первого элемента "\<Родительскийэлемент >".</span><span class="sxs-lookup"><span data-stu-id="1eb40-104">You can use the 'Value' property to get the string value of the first element of '\<parentElement>'.</span></span>  
  
 <span data-ttu-id="1eb40-105">Предпринята попытка неявного приведения XML-литерала к определенному типу.</span><span class="sxs-lookup"><span data-stu-id="1eb40-105">An attempt has been made to implicitly cast an XML literal to a specific type.</span></span> <span data-ttu-id="1eb40-106">XML-литерал не может быть неявно приведен к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="1eb40-106">The XML literal cannot be implicitly cast to the specified type.</span></span>  
  
 <span data-ttu-id="1eb40-107">**Идентификатор ошибки:** BC31194</span><span class="sxs-lookup"><span data-stu-id="1eb40-107">**Error ID:** BC31194</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1eb40-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1eb40-108">To correct this error</span></span>  
  
-   <span data-ttu-id="1eb40-109">Используйте свойство `Value` XML-литерала для ссылки на его значение как на `String`.</span><span class="sxs-lookup"><span data-stu-id="1eb40-109">Use the `Value` property of the XML literal to reference its value as a `String`.</span></span> <span data-ttu-id="1eb40-110">Используйте функцию `CType` , другую функцию преобразования типа или класс <xref:System.Convert> для приведения значения к указанному типу.</span><span class="sxs-lookup"><span data-stu-id="1eb40-110">Use the `CType` function, another type conversion function, or the <xref:System.Convert> class to cast the value as the specified type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eb40-111">См. также</span><span class="sxs-lookup"><span data-stu-id="1eb40-111">See Also</span></span>  
 <xref:System.Convert>  
 [<span data-ttu-id="1eb40-112">Функции преобразования типов</span><span class="sxs-lookup"><span data-stu-id="1eb40-112">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="1eb40-113">XML-литералы</span><span class="sxs-lookup"><span data-stu-id="1eb40-113">XML Literals</span></span>](../../../visual-basic/language-reference/xml-literals/index.md)  
 [<span data-ttu-id="1eb40-114">XML</span><span class="sxs-lookup"><span data-stu-id="1eb40-114">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
