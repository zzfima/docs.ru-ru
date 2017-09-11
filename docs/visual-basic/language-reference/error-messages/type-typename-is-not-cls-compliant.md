---
title: "Тип &lt;typename&gt; не является CLS-совместимым | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
dev_langs:
- VB
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
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
ms.openlocfilehash: a8d65568e862c941d5b927582833dff803219bf9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="bf76a-102">Тип &lt;typename&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="bf76a-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="bf76a-103">Переменная, свойство или возвращаемое функцией объявлен с типом данных, который не является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="bf76a-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="bf76a-104">Для приложения на соответствие стандарту [независимость от языка и независимые от языка компоненты](https://msdn.microsoft.com/library/12a7a7h3) (CLS), он должен использовать только CLS-совместимые типы.</span><span class="sxs-lookup"><span data-stu-id="bf76a-104">For an application to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="bf76a-105">Следующие типы данных [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] не соответствуют CLS:</span><span class="sxs-lookup"><span data-stu-id="bf76a-105">The following [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="bf76a-106">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="bf76a-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="bf76a-107">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="bf76a-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="bf76a-108">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="bf76a-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="bf76a-109">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="bf76a-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="bf76a-110">**Идентификатор ошибки:** BC40041</span><span class="sxs-lookup"><span data-stu-id="bf76a-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bf76a-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bf76a-111">To correct this error</span></span>  
  
-   <span data-ttu-id="bf76a-112">Если приложение должно быть CLS-совместимыми, измените тип данных этого элемента на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="bf76a-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="bf76a-113">Например, вместо `UInteger` вы можете использовать `Integer`, если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="bf76a-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="bf76a-114">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="bf76a-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="bf76a-115">Если приложения не должны быть CLS-совместимыми, ничего менять не нужно.</span><span class="sxs-lookup"><span data-stu-id="bf76a-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="bf76a-116">Следует помнить о его несоответствия, однако.</span><span class="sxs-lookup"><span data-stu-id="bf76a-116">You should be aware of its noncompliance, however.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf76a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bf76a-117">See Also</span></span>  
 [<span data-ttu-id="bf76a-118">\<PAVE НАД настроек написание CLS-совместимого кода</span><span class="sxs-lookup"><span data-stu-id="bf76a-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
