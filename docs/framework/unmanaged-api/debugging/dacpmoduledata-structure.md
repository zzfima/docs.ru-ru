---
title: Структура DacpModuleData
ms.date: 02/01/2019
api.name:
- DacpModuleData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpModuleData Structure
helpviewer.keywords:
- DacpModuleData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: c24bdce64eb7e208bf3830940d7beab1ebf92e78
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179188"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="cc382-102">Структура DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="cc382-102">DacpModuleData Structure</span></span>

<span data-ttu-id="cc382-103">Определяет транспортный буфер для информации о времени выполнения модуля.</span><span class="sxs-lookup"><span data-stu-id="cc382-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="cc382-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc382-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File;
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="cc382-105">Члены</span><span class="sxs-lookup"><span data-stu-id="cc382-105">Members</span></span>

| <span data-ttu-id="cc382-106">Участник</span><span class="sxs-lookup"><span data-stu-id="cc382-106">Member</span></span>    | <span data-ttu-id="cc382-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cc382-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="cc382-108">Адрес объекта модуля.</span><span class="sxs-lookup"><span data-stu-id="cc382-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="cc382-109">Указатель на портативный исполняемый (PE) файл.</span><span class="sxs-lookup"><span data-stu-id="cc382-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="cc382-110">Адрес базы загруженного изображения.</span><span class="sxs-lookup"><span data-stu-id="cc382-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="cc382-111">Буфер полезной нагрузки для дополнительной информации о модуле, используемой временем выполнения.</span><span class="sxs-lookup"><span data-stu-id="cc382-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="cc382-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="cc382-112">Remarks</span></span>

<span data-ttu-id="cc382-113">Эта структура живет в времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек.</span><span class="sxs-lookup"><span data-stu-id="cc382-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="cc382-114">Чтобы использовать его, определите структуру, указанную выше.</span><span class="sxs-lookup"><span data-stu-id="cc382-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc382-115">Требования</span><span class="sxs-lookup"><span data-stu-id="cc382-115">Requirements</span></span>
<span data-ttu-id="cc382-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc382-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="cc382-117">**Заголовок:** Ни один</span><span class="sxs-lookup"><span data-stu-id="cc382-117">**Header:** None</span></span>  
<span data-ttu-id="cc382-118">**Библиотека:** Ни один</span><span class="sxs-lookup"><span data-stu-id="cc382-118">**Library:** None</span></span>  
<span data-ttu-id="cc382-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="cc382-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="cc382-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc382-120">See also</span></span>

- [<span data-ttu-id="cc382-121">Отладки</span><span class="sxs-lookup"><span data-stu-id="cc382-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="cc382-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="cc382-122">Debugging Structures</span></span>](debugging-structures.md)
