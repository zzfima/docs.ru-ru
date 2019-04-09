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
ms.openlocfilehash: 257fa2cf03a62ea888b76519aa5c9f9e84038045
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59126507"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a><span data-ttu-id="c22ba-102">Метод IXCLRDataProcess::GetAppDomainByUniqueId</span><span class="sxs-lookup"><span data-stu-id="c22ba-102">IXCLRDataProcess::GetAppDomainByUniqueId Method</span></span>

<span data-ttu-id="c22ba-103">Получает `AppDomain` в процесс, основанный на свой уникальный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="c22ba-103">Gets an `AppDomain` in a process based on its unique identifier.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c22ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c22ba-104">Syntax</span></span>
```
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a><span data-ttu-id="c22ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c22ba-105">Parameters</span></span>

`id`\
<span data-ttu-id="c22ba-106">[in] Уникальный идентификатор домена приложения</span><span class="sxs-lookup"><span data-stu-id="c22ba-106">[in] The unique identifier of the AppDomain</span></span>

`appDomain`\
<span data-ttu-id="c22ba-107">[out] Домен приложения</span><span class="sxs-lookup"><span data-stu-id="c22ba-107">[out] The AppDomain</span></span>

## <a name="remarks"></a><span data-ttu-id="c22ba-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c22ba-108">Remarks</span></span>

<span data-ttu-id="c22ba-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 20 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="c22ba-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="c22ba-110">`IXCLRDataAppDomain*` Возвращается используется для взаимодействия с другими интерфейсами API.</span><span class="sxs-lookup"><span data-stu-id="c22ba-110">The `IXCLRDataAppDomain*` returned is used for interaction with other APIs.</span></span>

## <a name="requirements"></a><span data-ttu-id="c22ba-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c22ba-111">Requirements</span></span>
<span data-ttu-id="c22ba-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c22ba-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c22ba-113">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="c22ba-113">**Header:** None</span></span>  
<span data-ttu-id="c22ba-114">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="c22ba-114">**Library:** None</span></span>  
**<span data-ttu-id="c22ba-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c22ba-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="c22ba-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c22ba-116">See also</span></span>

- [<span data-ttu-id="c22ba-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="c22ba-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="c22ba-118">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="c22ba-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
