---
title: Метод ISOSDacInterface::GetModuleData
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetModuleData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetModuleData Method
helpviewer.keywords:
- ISOSDacInterface::GetModuleData Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 128af261c429228c97d952f1f8d382f46306f711
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229320"
---
# <a name="isosdacinterfacegetmoduledata-method"></a><span data-ttu-id="79ec6-102">Метод ISOSDacInterface::GetModuleData</span><span class="sxs-lookup"><span data-stu-id="79ec6-102">ISOSDacInterface::GetModuleData Method</span></span>

<span data-ttu-id="79ec6-103">Извлекает данные, соответствующие модуль загружен по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="79ec6-103">Fetches the data corresponding to the module loaded at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="79ec6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79ec6-104">Syntax</span></span>

```
HRESULT GetModuleData(
    CLRDATA_ADDRESS moduleAddr,
    DacpModuleData *data
);
```

## <a name="parameters"></a><span data-ttu-id="79ec6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79ec6-105">Parameters</span></span>

`moduleAddr`\
<span data-ttu-id="79ec6-106">[in] Адрес модуля для получения сведений для.</span><span class="sxs-lookup"><span data-stu-id="79ec6-106">[in] The address of the module to retrieve information for.</span></span>

`data`\
<span data-ttu-id="79ec6-107">[out] [DacpModuleData структуры](dacpmoduledata-structure.md) для хранения информации о загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="79ec6-107">[out] The [DacpModuleData structure](dacpmoduledata-structure.md) to hold the information of the loaded module.</span></span>

## <a name="remarks"></a><span data-ttu-id="79ec6-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="79ec6-108">Remarks</span></span>

<span data-ttu-id="79ec6-109">Указанный метод является частью `ISOSDacInterface` интерфейса и соответствует 13-й слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="79ec6-109">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 13th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="79ec6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="79ec6-110">Requirements</span></span>

<span data-ttu-id="79ec6-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79ec6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="79ec6-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="79ec6-112">**Header:** None</span></span>  
<span data-ttu-id="79ec6-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="79ec6-113">**Library:** None</span></span>  
**<span data-ttu-id="79ec6-114">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="79ec6-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="79ec6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="79ec6-115">See also</span></span>

- [<span data-ttu-id="79ec6-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="79ec6-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="79ec6-117">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="79ec6-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)