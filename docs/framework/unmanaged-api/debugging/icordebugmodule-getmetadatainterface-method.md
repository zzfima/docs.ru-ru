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
ms.openlocfilehash: fb96949e22b4edfc0e64780a54bb38da44eb8369
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129548"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="ea1b1-102">Метод ICorDebugModule::GetMetaDataInterface</span><span class="sxs-lookup"><span data-stu-id="ea1b1-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="ea1b1-103">Возвращает объект интерфейса метаданных, который может использоваться для проверки метаданных модуля.</span><span class="sxs-lookup"><span data-stu-id="ea1b1-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea1b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea1b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ea1b1-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="ea1b1-106">окне Идентификатор ссылки, указывающий интерфейс метаданных.</span><span class="sxs-lookup"><span data-stu-id="ea1b1-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="ea1b1-107">заполняет Указатель на адрес объекта `T:IUnknown`, который является одним из [интерфейсов метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="ea1b1-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea1b1-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="ea1b1-108">Remarks</span></span>  
 <span data-ttu-id="ea1b1-109">Отладчик может использовать метод `GetMetaDataInterface`, чтобы создать копию исходных метаданных для модуля, который необходимо сделать для изменения этого модуля.</span><span class="sxs-lookup"><span data-stu-id="ea1b1-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="ea1b1-110">Отладчик вызывает `GetMetaDataInterface`, чтобы получить объект интерфейса [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) для модуля, а затем вызывает метод [IMetaDataEmit:: саветомемори](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) , чтобы сохранить копию метаданных модуля в памяти.</span><span class="sxs-lookup"><span data-stu-id="ea1b1-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea1b1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ea1b1-111">Requirements</span></span>  
 <span data-ttu-id="ea1b1-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea1b1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea1b1-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea1b1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea1b1-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea1b1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea1b1-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea1b1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1b1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ea1b1-116">See also</span></span>

- [<span data-ttu-id="ea1b1-117">Метаданные</span><span class="sxs-lookup"><span data-stu-id="ea1b1-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
