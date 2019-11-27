---
title: Метод EnumImportTypes
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
ms.openlocfilehash: ca7c7570aff63aa328dddc0626648fa74397addc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448737"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="ada77-102">Метод EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="ada77-102">EnumImportTypes Method</span></span>

<span data-ttu-id="ada77-103">Перечисляет каждый тип в каждой области.</span><span class="sxs-lookup"><span data-stu-id="ada77-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="ada77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ada77-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="ada77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ada77-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="ada77-106">Обработчик для перечислителя.</span><span class="sxs-lookup"><span data-stu-id="ada77-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="ada77-107">Максимальное число извлекаемых типов.</span><span class="sxs-lookup"><span data-stu-id="ada77-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="ada77-108">Получает токены типа, не превышающие `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="ada77-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="ada77-109">Получает фактическое число типов в `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="ada77-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ada77-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ada77-110">Return Value</span></span>

<span data-ttu-id="ada77-111">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="ada77-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="ada77-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ada77-112">Requirements</span></span>

<span data-ttu-id="ada77-113">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="ada77-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="ada77-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ada77-114">See also</span></span>

- [<span data-ttu-id="ada77-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="ada77-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="ada77-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="ada77-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="ada77-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="ada77-117">ALink API</span></span>](index.md)
