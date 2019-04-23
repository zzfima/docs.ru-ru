---
title: Метод IXCLRDataProcess::EnumMethodInstanceByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a51c709b0b331127b74d98c4dc42e2772fd7f2db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166443"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="c3f93-102">Метод IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="c3f93-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="c3f93-103">Перечисление экземпляров метод класса этот процесс, начиная с смещение адреса.</span><span class="sxs-lookup"><span data-stu-id="c3f93-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="c3f93-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3f93-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="c3f93-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3f93-105">Parameters</span></span>

`handle`\
<span data-ttu-id="c3f93-106">[in] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="c3f93-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="c3f93-107">[out] Экземпляр перечисления метод.</span><span class="sxs-lookup"><span data-stu-id="c3f93-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3f93-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3f93-108">Remarks</span></span>

<span data-ttu-id="c3f93-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 28 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="c3f93-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3f93-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c3f93-110">Requirements</span></span>

<span data-ttu-id="c3f93-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3f93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="c3f93-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="c3f93-112">**Header:** None</span></span>   
<span data-ttu-id="c3f93-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="c3f93-113">**Library:** None</span></span>   
<span data-ttu-id="c3f93-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3f93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="c3f93-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c3f93-115">See also</span></span>

- [<span data-ttu-id="c3f93-116">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="c3f93-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="c3f93-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="c3f93-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="c3f93-118">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="c3f93-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
