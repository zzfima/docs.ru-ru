---
title: "Тип &lt;typename&gt; не является CLS-совместимым"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 36a49ccf7d2185c26ef8d23eebea216cc193d951
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="type-lttypenamegt-is-not-cls-compliant"></a><span data-ttu-id="a6ece-102">Тип &lt;typename&gt; не является CLS-совместимым</span><span class="sxs-lookup"><span data-stu-id="a6ece-102">Type &lt;typename&gt; is not CLS-compliant</span></span>
<span data-ttu-id="a6ece-103">Переменная, свойство или возвращаемое функцией объявлен с типом данных, который не является CLS-совместимым.</span><span class="sxs-lookup"><span data-stu-id="a6ece-103">A variable, property, or function return is declared with a data type that is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="a6ece-104">Для приложения в соответствии с [независимость от языка и независимые от языка компоненты](../../../standard/language-independence-and-language-independent-components.md) (CLS), он должен использовать только типы, совместимые с CLS.</span><span class="sxs-lookup"><span data-stu-id="a6ece-104">For an application to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span>  
  
 <span data-ttu-id="a6ece-105">Следующие типы данных [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] не соответствуют CLS:</span><span class="sxs-lookup"><span data-stu-id="a6ece-105">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="a6ece-106">Тип данных SByte</span><span class="sxs-lookup"><span data-stu-id="a6ece-106">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="a6ece-107">Тип данных UInteger</span><span class="sxs-lookup"><span data-stu-id="a6ece-107">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="a6ece-108">Тип данных ULong</span><span class="sxs-lookup"><span data-stu-id="a6ece-108">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="a6ece-109">Тип данных UShort</span><span class="sxs-lookup"><span data-stu-id="a6ece-109">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="a6ece-110">**Идентификатор ошибки:** BC40041</span><span class="sxs-lookup"><span data-stu-id="a6ece-110">**Error ID:** BC40041</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6ece-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="a6ece-111">To correct this error</span></span>  
  
-   <span data-ttu-id="a6ece-112">Если приложение должно быть CLS-совместимыми, измените тип данных этого элемента на ближайший CLS-совместимый тип.</span><span class="sxs-lookup"><span data-stu-id="a6ece-112">If your application needs to be CLS-compliant, change the data type of this element to the closest CLS-compliant type.</span></span> <span data-ttu-id="a6ece-113">Например, вместо `UInteger` вы можете использовать `Integer` , если вам не нужен диапазон значений, превышающий 2 147 483 647.</span><span class="sxs-lookup"><span data-stu-id="a6ece-113">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="a6ece-114">Если вам нужен расширенный диапазон, вы можете заменить `UInteger` на `Long`.</span><span class="sxs-lookup"><span data-stu-id="a6ece-114">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="a6ece-115">Если приложения не должны быть CLS-совместимыми, внесет необходимые изменения необязательно.</span><span class="sxs-lookup"><span data-stu-id="a6ece-115">If your application does not need to be CLS-compliant, you do not need to change anything.</span></span> <span data-ttu-id="a6ece-116">Следует помнить о его несоответствия, однако.</span><span class="sxs-lookup"><span data-stu-id="a6ece-116">You should be aware of its noncompliance, however.</span></span>