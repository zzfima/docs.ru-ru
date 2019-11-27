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
ms.openlocfilehash: 93dd8c56176890d04d792f3c336492e4f232825b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442464"
---
# <a name="corthreadsafetyoptions-enumeration"></a><span data-ttu-id="d8258-102">Перечисление CorThreadSafetyOptions</span><span class="sxs-lookup"><span data-stu-id="d8258-102">CorThreadSafetyOptions Enumeration</span></span>

<span data-ttu-id="d8258-103">Задает флаги для выбора параметров безопасности потока.</span><span class="sxs-lookup"><span data-stu-id="d8258-103">Specifies flags to select options for thread safety.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8258-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8258-104">Syntax</span></span>

```cpp
typedef enum CorThreadSafetyOptions {
    MDThreadSafetyDefault       = 0x00000000,
    MDThreadSafetyOff           = 0x00000000,
    MDThreadSafetyOn            = 0x00000001,
} CorThreadSafetyOptions;
```

## <a name="members"></a><span data-ttu-id="d8258-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d8258-105">Members</span></span>

|<span data-ttu-id="d8258-106">Член</span><span class="sxs-lookup"><span data-stu-id="d8258-106">Member</span></span>|<span data-ttu-id="d8258-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d8258-107">Description</span></span>|
|------------|-----------------|
|`MDThreadSafetyDefault`|<span data-ttu-id="d8258-108">Значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d8258-108">Default value.</span></span> <span data-ttu-id="d8258-109">Эквивалентно `MDThreadSafetyOff`.</span><span class="sxs-lookup"><span data-stu-id="d8258-109">Same as `MDThreadSafetyOff`.</span></span>|
|`MDThreadSafetyOff`|<span data-ttu-id="d8258-110">Указывает, что невозможно установить блокировку потоков чтения/записи.</span><span class="sxs-lookup"><span data-stu-id="d8258-110">Indicates that a reader/writer lock cannot be set.</span></span>|
|`MDThreadSafetyOn`|<span data-ttu-id="d8258-111">Указывает, что можно задать блокировку потоков чтения/записи.</span><span class="sxs-lookup"><span data-stu-id="d8258-111">Indicates that a reader/writer lock can be set.</span></span>|

## <a name="requirements"></a><span data-ttu-id="d8258-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d8258-112">Requirements</span></span>

<span data-ttu-id="d8258-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8258-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d8258-114">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="d8258-114">**Header:** CorHdr.h</span></span>

<span data-ttu-id="d8258-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8258-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d8258-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d8258-116">See also</span></span>

- [<span data-ttu-id="d8258-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="d8258-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
