---
title: "Тип &lt;typename&gt; не является CLS-совместимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords: BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 16c12ee6c4f6efa20b9bab5ccf10077496b931ac
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/09/2017
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="0b1c9-102">Тип &lt;typename&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="0b1c9-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="0b1c9-103">Переменная, свойство или возвращаемое функцией объявлен с типом данных, который не является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="0b1c9-104">Для приложения в соответствии с [независимость от языка и независимые от языка компоненты](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), он должен использовать только типы, совместимые с CLS.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../../docs/standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="0b1c9-105">Следующие типы данных [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не соответствуют CLS:</span><span class="sxs-lookup"><span data-stu-id="0b1c9-105">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="0b1c9-106">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="0b1c9-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="0b1c9-107">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="0b1c9-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="0b1c9-108">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="0b1c9-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="0b1c9-109">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="0b1c9-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="0b1c9-110">**Идентификатор ошибки:** BC40041</span><span class="sxs-lookup"><span data-stu-id="0b1c9-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0b1c9-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0b1c9-111">To correct this error</span></span>  
  
-   <span data-ttu-id="0b1c9-112">Если приложение должно быть CLS-совместимыми, измените тип данных этого элемента на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="0b1c9-113">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="0b1c9-114">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="0b1c9-115">Если приложения не должны быть CLS-совместимыми, внесет необходимые изменения необязательно.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="0b1c9-116">Следует помнить о его несоответствия, однако.</span><span class="sxs-lookup"><span data-stu-id="0b1c9-116">You should be aware of its noncompliance, however.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b1c9-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0b1c9-117">See Also</span></span>  
 [<span data-ttu-id="0b1c9-118">\<PAVE НАД > написание CLS-совместимого кода</span><span class="sxs-lookup"><span data-stu-id="0b1c9-118">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
