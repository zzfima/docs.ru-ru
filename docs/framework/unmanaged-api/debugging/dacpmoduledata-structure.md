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
ms.openlocfilehash: b46a04d67f59c5031b5bd195cef4cc2275e1e5e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793808"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="e455d-102">Структура DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="e455d-102">DacpModuleData Structure</span></span>

<span data-ttu-id="e455d-103">Определяет транспортный буфер для сведений о среде выполнения модуля.</span><span class="sxs-lookup"><span data-stu-id="e455d-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e455d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e455d-104">Syntax</span></span>

```cpp
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="e455d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e455d-105">Members</span></span>

| <span data-ttu-id="e455d-106">Член</span><span class="sxs-lookup"><span data-stu-id="e455d-106">Member</span></span>    | <span data-ttu-id="e455d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e455d-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="e455d-108">Адрес объекта модуля.</span><span class="sxs-lookup"><span data-stu-id="e455d-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="e455d-109">Указатель на переносимый исполняемый файл (PE).</span><span class="sxs-lookup"><span data-stu-id="e455d-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="e455d-110">Адрес базы загруженного образа.</span><span class="sxs-lookup"><span data-stu-id="e455d-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="e455d-111">Буфер полезных данных для дополнительных сведений о модулях, используемых средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="e455d-111">A payload buffer for additional module information used by the runtime.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e455d-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="e455d-112">Remarks</span></span>

<span data-ttu-id="e455d-113">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="e455d-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="e455d-114">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="e455d-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="e455d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e455d-115">Requirements</span></span>
<span data-ttu-id="e455d-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e455d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e455d-117">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="e455d-117">**Header:** None</span></span>  
<span data-ttu-id="e455d-118">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="e455d-118">**Library:** None</span></span>  
<span data-ttu-id="e455d-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e455d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e455d-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="e455d-120">See also</span></span>

- [<span data-ttu-id="e455d-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="e455d-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="e455d-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="e455d-122">Debugging Structures</span></span>](debugging-structures.md)
