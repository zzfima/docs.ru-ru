---
title: Тип <typename> несовместим с CLS
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 243f51b3e6c798c82fdbe7b28557c4f96c728bf2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55281727"
---
# <a name="type-typename-is-not-cls-compliant"></a><span data-ttu-id="fee0d-102">Тип \<typename > не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="fee0d-102">Type \<typename> is not CLS-compliant</span></span>
<span data-ttu-id="fee0d-103">Переменная, свойство или возвращаемое значение функции объявлен с типом данных, не является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="fee0d-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="fee0d-104">Для приложения на соответствие стандарту [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), он должен использовать только типы, совместимые с CLS.</span><span class="sxs-lookup"><span data-stu-id="fee0d-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="fee0d-105">Следующие типы данных Visual Basic не являются CLS-совместимыми:</span><span class="sxs-lookup"><span data-stu-id="fee0d-105">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="fee0d-106">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="fee0d-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="fee0d-107">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="fee0d-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="fee0d-108">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="fee0d-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="fee0d-109">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="fee0d-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="fee0d-110">**Идентификатор ошибки:** BC40041</span><span class="sxs-lookup"><span data-stu-id="fee0d-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fee0d-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fee0d-111">To correct this error</span></span>  
  
-   <span data-ttu-id="fee0d-112">Если приложение должно быть CLS-совместимыми, измените тип данных этого элемента на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="fee0d-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="fee0d-113">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="fee0d-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="fee0d-114">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="fee0d-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="fee0d-115">Если приложения не должны быть CLS-совместимым, ничего менять не нужно.</span><span class="sxs-lookup"><span data-stu-id="fee0d-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="fee0d-116">Вы должны помнить его несоответствия, однако.</span><span class="sxs-lookup"><span data-stu-id="fee0d-116">You should be aware of its noncompliance, however.</span></span>