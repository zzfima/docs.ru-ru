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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355744"
---
# <a name="enumimporttypes-method"></a><span data-ttu-id="1e49c-102">Метод EnumImportTypes</span><span class="sxs-lookup"><span data-stu-id="1e49c-102">EnumImportTypes Method</span></span>

<span data-ttu-id="1e49c-103">Перечисляет каждый тип в каждой области.</span><span class="sxs-lookup"><span data-stu-id="1e49c-103">Enumerates each type in each scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e49c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e49c-104">Syntax</span></span>

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a><span data-ttu-id="1e49c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e49c-105">Parameters</span></span>

`hEnum`\
<span data-ttu-id="1e49c-106">Дескриптор для перечислителя.</span><span class="sxs-lookup"><span data-stu-id="1e49c-106">Handle for enumerator.</span></span>

`dwMax`\
<span data-ttu-id="1e49c-107">Максимальное число извлекаемых типов.</span><span class="sxs-lookup"><span data-stu-id="1e49c-107">Maximum number of types to retrieve.</span></span>

`aTypeDefs`\
<span data-ttu-id="1e49c-108">Получает тип токенов, оно не должно превышать `dwMax`.</span><span class="sxs-lookup"><span data-stu-id="1e49c-108">Receives type tokens, not to exceed `dwMax`.</span></span>

`pdwCount`\
<span data-ttu-id="1e49c-109">Получает фактическое число типов в `aTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="1e49c-109">Receives actual number of type in `aTypeDefs`.</span></span>

## <a name="return-value"></a><span data-ttu-id="1e49c-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1e49c-110">Return Value</span></span>

<span data-ttu-id="1e49c-111">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="1e49c-111">Returns S_OK if the method succeeds.</span></span>

## <a name="requirements"></a><span data-ttu-id="1e49c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1e49c-112">Requirements</span></span>

<span data-ttu-id="1e49c-113">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="1e49c-113">Requires alink.h</span></span>

## <a name="see-also"></a><span data-ttu-id="1e49c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1e49c-114">See also</span></span>

- [<span data-ttu-id="1e49c-115">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="1e49c-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1e49c-116">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="1e49c-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1e49c-117">API ALink</span><span class="sxs-lookup"><span data-stu-id="1e49c-117">ALink API</span></span>](index.md)