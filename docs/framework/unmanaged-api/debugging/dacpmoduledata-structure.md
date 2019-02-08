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
ms.openlocfilehash: db3fdaa768e3d1b445f08c3964521570631f0965
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828669"
---
# <a name="dacpmoduledata-structure"></a><span data-ttu-id="4bd79-102">Структура DacpModuleData</span><span class="sxs-lookup"><span data-stu-id="4bd79-102">DacpModuleData Structure</span></span>

<span data-ttu-id="4bd79-103">Определяет транспорт буфера для модуля сведения среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4bd79-103">Defines a transport buffer for a module's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4bd79-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bd79-104">Syntax</span></span>

```
struct DacpModuleData
{
    CLRDATA_ADDRESS Address;
    CLRDATA_ADDRESS File; 
    CLRDATA_ADDRESS  ilBase;
    char payLoad[132];
};
```

## <a name="members"></a><span data-ttu-id="4bd79-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4bd79-105">Members</span></span>

| <span data-ttu-id="4bd79-106">Член</span><span class="sxs-lookup"><span data-stu-id="4bd79-106">Member</span></span>    | <span data-ttu-id="4bd79-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4bd79-107">Description</span></span>                                                             |
| --------- | ----------------------------------------------------------------------- |
| `Address` | <span data-ttu-id="4bd79-108">Адрес объекта модуля.</span><span class="sxs-lookup"><span data-stu-id="4bd79-108">Address of the module object.</span></span>                                           |
| `File`    | <span data-ttu-id="4bd79-109">Указатель на переносимого исполняемого (PE) файла.</span><span class="sxs-lookup"><span data-stu-id="4bd79-109">A pointer to the portable executable (PE) file.</span></span>                       |
| `ilBase`  | <span data-ttu-id="4bd79-110">Адрес загруженного образа базовый.</span><span class="sxs-lookup"><span data-stu-id="4bd79-110">The address of the loaded image's base.</span></span>                                 |
| `payLoad` | <span data-ttu-id="4bd79-111">Буфер полезных данных для дополнительного модуля сведения, используемые средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="4bd79-111">A payload buffer for additional module information used by the runtime.</span></span> |


## <a name="remarks"></a><span data-ttu-id="4bd79-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="4bd79-112">Remarks</span></span>

<span data-ttu-id="4bd79-113">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="4bd79-113">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="4bd79-114">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="4bd79-114">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="4bd79-115">Требования</span><span class="sxs-lookup"><span data-stu-id="4bd79-115">Requirements</span></span>
<span data-ttu-id="4bd79-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bd79-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4bd79-117">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="4bd79-117">**Header:** None</span></span>  
<span data-ttu-id="4bd79-118">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="4bd79-118">**Library:** None</span></span>  
<span data-ttu-id="4bd79-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd79-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4bd79-120">См. также</span><span class="sxs-lookup"><span data-stu-id="4bd79-120">See also</span></span>
- [<span data-ttu-id="4bd79-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="4bd79-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="4bd79-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="4bd79-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
