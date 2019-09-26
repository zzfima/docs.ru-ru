---
title: Перечисление Клрдатасаурцетипе
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274097"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="9d156-102">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="9d156-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="9d156-103">Предоставляет значения, используемые структурой CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="9d156-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9d156-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d156-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="9d156-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9d156-105">Members</span></span>

| <span data-ttu-id="9d156-106">Член</span><span class="sxs-lookup"><span data-stu-id="9d156-106">Member</span></span>                        | <span data-ttu-id="9d156-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9d156-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="9d156-108">Указание того, что ничего еще не применимо</span><span class="sxs-lookup"><span data-stu-id="9d156-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="9d156-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9d156-109">Remarks</span></span>

<span data-ttu-id="9d156-110">Это перечисление находится внутри среды выполнения и не предоставляется через заголовки или файлы библиотек.</span><span class="sxs-lookup"><span data-stu-id="9d156-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9d156-111">Чтобы использовать его, определите перечисление, как определено выше в коде.</span><span class="sxs-lookup"><span data-stu-id="9d156-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="9d156-112">Это также называется псевдонимом `CLRDATA_ENUM` , как упоминалось в [общих типах данных](../common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="9d156-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="9d156-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9d156-113">Requirements</span></span>

<span data-ttu-id="9d156-114">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d156-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9d156-115">**Заголовок.** Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="9d156-115">**Header:** None</span></span>  
<span data-ttu-id="9d156-116">**Библиотечная** Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="9d156-116">**Library:** None</span></span>  
<span data-ttu-id="9d156-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9d156-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9d156-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9d156-118">See also</span></span>

- [<span data-ttu-id="9d156-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="9d156-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="9d156-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="9d156-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
