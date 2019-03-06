---
title: Перечисление CorThreadSafetyOptions
ms.date: 03/30/2017
api_name:
- CorThreadSafetyOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorThreadSafetyOptions
helpviewer_keywords:
- CorThreadSafetyOptions enumeration [.NET Framework metadata]
ms.assetid: dae07d9b-df51-488c-b17e-52d6e48217bd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d71d2a5b3007d4e877900443af426a9643b29125
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360446"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="72cd1-102">Перечисление CorThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="72cd1-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="72cd1-103">Задает флаги для выбора параметров безопасности потока.</span><span class="sxs-lookup"><span data-stu-id="72cd1-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="72cd1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72cd1-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="72cd1-105">Участники</span><span class="sxs-lookup"><span data-stu-id="72cd1-105">Members</span></span>

|<span data-ttu-id="72cd1-106">Член</span><span class="sxs-lookup"><span data-stu-id="72cd1-106">Member</span></span>|<span data-ttu-id="72cd1-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="72cd1-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="72cd1-108">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="72cd1-108">Default value.</span></span> <span data-ttu-id="72cd1-109">Эквивалентно `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="72cd1-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="72cd1-110">Указывает, что нельзя установить блокировку потоков чтения/записи.</span><span class="sxs-lookup"><span data-stu-id="72cd1-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="72cd1-111">Указывает, что блокировки потоков чтения/записи может быть задано.</span><span class="sxs-lookup"><span data-stu-id="72cd1-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="72cd1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="72cd1-112">Requirements</span></span>

<span data-ttu-id="72cd1-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72cd1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="72cd1-114">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="72cd1-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="72cd1-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72cd1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="72cd1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="72cd1-116">See also</span></span>

- [<span data-ttu-id="72cd1-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="72cd1-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
