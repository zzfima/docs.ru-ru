---
title: Метод IXCLRDataProcess::GetAppDomainByUniqueId
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8b468d40ef8eb523ba8881627fae15cf9b7c7b80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775269"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="6a0d2-102">Метод IXCLRDataProcess::GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="6a0d2-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="6a0d2-103">Получает `AppDomain` в процесс, основанный на свой уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="6a0d2-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6a0d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a0d2-104">Syntax</span></span>

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="6a0d2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a0d2-105">Parameters</span></span>

`id`\
<span data-ttu-id="6a0d2-106">[in] Уникальный идентификатор домена приложения</span><span class="sxs-lookup"><span data-stu-id="6a0d2-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="6a0d2-107">[out] Домен приложения</span><span class="sxs-lookup"><span data-stu-id="6a0d2-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="6a0d2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6a0d2-108">Remarks</span></span>

<span data-ttu-id="6a0d2-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 20 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="6a0d2-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="6a0d2-110">`IXCLRDataAppDomain*` Возвращается используется для взаимодействия с другими интерфейсами API.</span><span class="sxs-lookup"><span data-stu-id="6a0d2-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a0d2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6a0d2-111">Requirements</span></span>

<span data-ttu-id="6a0d2-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a0d2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="6a0d2-113">**Заголовок.** Нет **библиотеки:** Нет **версий платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6a0d2-113">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6a0d2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6a0d2-114">See also</span></span>

- [<span data-ttu-id="6a0d2-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="6a0d2-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="6a0d2-116">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="6a0d2-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
