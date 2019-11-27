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
ms.openlocfilehash: 6a5b3f1e9bf1444feb73949ef7133fbd9ae35134
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446475"
---
# <a name="enumcustomattributes-method"></a><span data-ttu-id="51df0-102">Метод EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="51df0-102">EnumCustomAttributes Method</span></span>
<span data-ttu-id="51df0-103">Извлекает настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="51df0-103">Retrieves assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51df0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51df0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes(  
    HALINKENUM hEnum,  
    mdToken tkType,  
    mdCustomAttribute rCustomValues[],  
    ULONG cMax,  
    ULONG* pcCustomValues  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="51df0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="51df0-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="51df0-106">Маркер перечислителя.</span><span class="sxs-lookup"><span data-stu-id="51df0-106">Handle of enumerator.</span></span>  
  
 `tkType`  
 <span data-ttu-id="51df0-107">Тип атрибутов для перечисления.</span><span class="sxs-lookup"><span data-stu-id="51df0-107">Type of attributes to be enumerated.</span></span> <span data-ttu-id="51df0-108">Используйте `mdTokenNill` для всех атрибутов.</span><span class="sxs-lookup"><span data-stu-id="51df0-108">Use `mdTokenNill` for all attributes.</span></span>  
  
 `rCustomValues`  
 <span data-ttu-id="51df0-109">Получает маркеры настраиваемых атрибутов.</span><span class="sxs-lookup"><span data-stu-id="51df0-109">Receives custom attributes tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="51df0-110">Задает размер массива `rCustomValues`.</span><span class="sxs-lookup"><span data-stu-id="51df0-110">Specifies size of `rCustomValues` array.</span></span>  
  
 `pcCustomValues`  
 <span data-ttu-id="51df0-111">При необходимости получает число значений токена.</span><span class="sxs-lookup"><span data-stu-id="51df0-111">Optionally receives count of token values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51df0-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="51df0-112">Return Value</span></span>  
 <span data-ttu-id="51df0-113">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="51df0-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51df0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="51df0-114">Requirements</span></span>  
 <span data-ttu-id="51df0-115">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="51df0-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51df0-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="51df0-116">See also</span></span>

- [<span data-ttu-id="51df0-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="51df0-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="51df0-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="51df0-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="51df0-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="51df0-119">ALink API</span></span>](index.md)
