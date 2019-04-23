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
ms.openlocfilehash: b419962982fc80591ed565cceb28afb88a39495e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199145"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="83b0e-102">Метод EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="83b0e-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="83b0e-103">Извлекает настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="83b0e-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83b0e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83b0e-104">Syntax</span></span>  
  
```  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="83b0e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="83b0e-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="83b0e-106">Дескриптор перечислителя.</span><span class="sxs-lookup"><span data-stu-id="83b0e-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="83b0e-107">Тип атрибутов, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="83b0e-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="83b0e-108">Используйте `mdTokenNill` для всех атрибутов.</span><span class="sxs-lookup"><span data-stu-id="83b0e-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="83b0e-109">Получает маркеры настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="83b0e-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="83b0e-110">Указывает размер `rCustomValues` массива.</span><span class="sxs-lookup"><span data-stu-id="83b0e-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="83b0e-111">При необходимости получает число значений маркера.</span><span class="sxs-lookup"><span data-stu-id="83b0e-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83b0e-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="83b0e-112">Return Value</span></span>  
 <span data-ttu-id="83b0e-113">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="83b0e-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83b0e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="83b0e-114">Requirements</span></span>  
 <span data-ttu-id="83b0e-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="83b0e-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b0e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="83b0e-116">See also</span></span>

- [<span data-ttu-id="83b0e-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="83b0e-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="83b0e-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="83b0e-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="83b0e-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="83b0e-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
