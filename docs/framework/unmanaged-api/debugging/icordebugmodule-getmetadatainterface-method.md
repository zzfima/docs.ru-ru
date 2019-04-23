---
title: Метод ICorDebugModule::GetMetaDataInterface
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37710fbb7acc50b80d7acebe4194b019c0b64660
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102600"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="7ee3b-102">Метод ICorDebugModule::GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="7ee3b-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="7ee3b-103">Получает объект интерфейс метаданных, который может использоваться для просмотра метаданных для модуля.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ee3b-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ee3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7ee3b-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="7ee3b-106">[in] Идентификатор ссылки, указывающий интерфейс метаданных.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="7ee3b-107">[out] Указатель на адрес `T:IUnknown` объект, который является одним из [интерфейсы метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="7ee3b-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ee3b-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ee3b-108">Remarks</span></span>  
 <span data-ttu-id="7ee3b-109">Можно использовать отладчик `GetMetaDataInterface` метод для создания копии исходных метаданных для модуля, которая необходима для редактирования этого модуля.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="7ee3b-110">Отладчик вызывает `GetMetaDataInterface` для получения [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) объект интерфейса для модуля, затем вызывает [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) для сохранения копии метаданных модуля памяти.</span><span class="sxs-lookup"><span data-stu-id="7ee3b-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ee3b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="7ee3b-111">Requirements</span></span>  
 <span data-ttu-id="7ee3b-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ee3b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ee3b-113">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ee3b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ee3b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ee3b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ee3b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ee3b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee3b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7ee3b-116">See also</span></span>

- [<span data-ttu-id="7ee3b-117">Метаданные</span><span class="sxs-lookup"><span data-stu-id="7ee3b-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
