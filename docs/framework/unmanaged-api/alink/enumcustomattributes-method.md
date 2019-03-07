---
title: Метод EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- EnumCustomAttributes
- IALink.EnumCustomAttributes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method
ms.assetid: 08dff60c-f01b-4050-8865-ea3f95361c9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e351c61f7e8bfc254a6fc8ea12c8a94fc393e3fc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478158"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="ebf2e-102">Метод EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="ebf2e-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="ebf2e-103">Извлекает настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="ebf2e-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf2e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebf2e-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebf2e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebf2e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ebf2e-106">Дескриптор перечислителя.</span><span class="sxs-lookup"><span data-stu-id="ebf2e-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ebf2e-107">Тип атрибутов, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="ebf2e-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="ebf2e-108">Используйте `mdTokenNill` для всех атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ebf2e-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="ebf2e-109">Получает маркеры настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ebf2e-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ebf2e-110">Указывает размер `rCustomValues` массива.</span><span class="sxs-lookup"><span data-stu-id="ebf2e-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="ebf2e-111">При необходимости получает число значений маркера.</span><span class="sxs-lookup"><span data-stu-id="ebf2e-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebf2e-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ebf2e-112">Return Value</span></span>  
 <span data-ttu-id="ebf2e-113">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="ebf2e-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf2e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ebf2e-114">Requirements</span></span>  
 <span data-ttu-id="ebf2e-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="ebf2e-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf2e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ebf2e-116">See also</span></span>
- [<span data-ttu-id="ebf2e-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="ebf2e-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ebf2e-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="ebf2e-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ebf2e-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="ebf2e-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
