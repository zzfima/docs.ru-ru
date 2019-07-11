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
ms.openlocfilehash: 09ccf731f0494b6eda49f6a15d04970a723c473b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742057"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="b8433-102">Метод EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="b8433-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="b8433-103">Извлекает настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="b8433-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8433-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8433-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8433-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8433-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="b8433-106">Дескриптор перечислителя.</span><span class="sxs-lookup"><span data-stu-id="b8433-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="b8433-107">Тип атрибутов, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="b8433-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="b8433-108">Используйте `mdTokenNill` для всех атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b8433-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="b8433-109">Получает маркеры настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="b8433-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b8433-110">Указывает размер `rCustomValues` массива.</span><span class="sxs-lookup"><span data-stu-id="b8433-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="b8433-111">При необходимости получает число значений маркера.</span><span class="sxs-lookup"><span data-stu-id="b8433-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8433-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b8433-112">Return Value</span></span>  
 <span data-ttu-id="b8433-113">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="b8433-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8433-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b8433-114">Requirements</span></span>  
 <span data-ttu-id="b8433-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="b8433-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8433-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b8433-116">See also</span></span>

- [<span data-ttu-id="b8433-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="b8433-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b8433-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="b8433-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b8433-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="b8433-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
