---
title: "Метод EnumCustomAttributes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location: alink.dll
api_type: COM
f1_keywords: EnumCustomAttributes
helpviewer_keywords: EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d616babb47ac0282ef56d119ab448a94fd24c7c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="e39cd-102">Метод EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="e39cd-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="e39cd-103">Извлекает настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="e39cd-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e39cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e39cd-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e39cd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e39cd-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e39cd-106">Дескриптор перечислителя.</span><span class="sxs-lookup"><span data-stu-id="e39cd-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="e39cd-107">Тип атрибутов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="e39cd-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="e39cd-108">Используйте `mdTokenNill` для всех атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e39cd-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="e39cd-109">Получает маркеры настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e39cd-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e39cd-110">Указывает размер `rCustomValues` массива.</span><span class="sxs-lookup"><span data-stu-id="e39cd-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="e39cd-111">При необходимости получает количество значений маркера.</span><span class="sxs-lookup"><span data-stu-id="e39cd-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e39cd-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e39cd-112">Return Value</span></span>  
 <span data-ttu-id="e39cd-113">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e39cd-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e39cd-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e39cd-114">Requirements</span></span>  
 <span data-ttu-id="e39cd-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="e39cd-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e39cd-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e39cd-116">See Also</span></span>  
 [<span data-ttu-id="e39cd-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e39cd-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e39cd-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e39cd-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e39cd-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="e39cd-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
