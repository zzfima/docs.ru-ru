---
title: Метод ICorDebugModule2::ApplyChanges
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a406e945a67352bc7f126b40bd56f4a11dd693b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419547"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="f0429-102">Метод ICorDebugModule2::ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="f0429-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="f0429-103">Применяет изменения в метаданных и изменений в код на промежуточном языке (MSIL) к работающему процессу.</span><span class="sxs-lookup"><span data-stu-id="f0429-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0429-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0429-104">Syntax</span></span>  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0429-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0429-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="f0429-106">[in] Размер в байтах, дельта метаданных.</span><span class="sxs-lookup"><span data-stu-id="f0429-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="f0429-107">[in] Буфер, содержащий метаданные изменений.</span><span class="sxs-lookup"><span data-stu-id="f0429-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="f0429-108">Адрес буфера возвращается из [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f0429-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="f0429-109">Относительные виртуальные адреса (RVA) в метаданных должен указываться относительно начала кода на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="f0429-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="f0429-110">[in] Размер в байтах разности код MSIL.</span><span class="sxs-lookup"><span data-stu-id="f0429-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="f0429-111">[in] Буфер, содержащий обновленный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="f0429-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0429-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0429-112">Remarks</span></span>  
 <span data-ttu-id="f0429-113">`pbMetadata` Параметр имеет формат метаданных специальные дельта (как выходные, [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="f0429-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="f0429-114">`pbMetadata` берет предыдущие метаданные в качестве базового и описывает отдельные изменения, применяемые к этой базе.</span><span class="sxs-lookup"><span data-stu-id="f0429-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="f0429-115">Напротив, `pbIL[`] параметр содержит новый код MSIL для обновленного метода и предназначен для полной замены предыдущих MSIL для этого метода</span><span class="sxs-lookup"><span data-stu-id="f0429-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="f0429-116">При создании разностного кода MSIL и метаданных в памяти отладчика, он вызывает `ApplyChanges` для отправки изменений в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="f0429-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="f0429-117">Среда выполнения обновляет свою таблицу метаданных, помещает новый код MSIL в процесс и настраивает в момент компиляции нового кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="f0429-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="f0429-118">Если изменения были применены, отладчик должен вызвать [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) для подготовки для следующего сеанса редактирования.</span><span class="sxs-lookup"><span data-stu-id="f0429-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="f0429-119">Затем он может продолжить процесс.</span><span class="sxs-lookup"><span data-stu-id="f0429-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="f0429-120">Каждый раз, когда он вызывает `ApplyChanges` модуля, который содержит метаданные изменений, он также должен вызвать [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) с одинаковыми метаданными изменений на все его копии метаданных этого модуля, за исключением копирования используется для выдачи изменений.</span><span class="sxs-lookup"><span data-stu-id="f0429-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="f0429-121">Если копии метаданных рассинхронизации ожидания для синхронизации с фактическими метаданными, отладчик всегда может отбросить эту копию и получить новую.</span><span class="sxs-lookup"><span data-stu-id="f0429-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="f0429-122">Если `ApplyChanges` сбой метода отладки сеанс находится в недопустимом состоянии и должен быть перезапущен.</span><span class="sxs-lookup"><span data-stu-id="f0429-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0429-123">Требования</span><span class="sxs-lookup"><span data-stu-id="f0429-123">Requirements</span></span>  
 <span data-ttu-id="f0429-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0429-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0429-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0429-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0429-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0429-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0429-127">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0429-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
