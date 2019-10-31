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
ms.openlocfilehash: c324019e1e62701f4f2aaba1c00948b292ba6847
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127916"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="032aa-102">Метод ICorDebugModule2::ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="032aa-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="032aa-103">Применяет изменения в метаданных и изменения в коде промежуточного языка MSIL к выполняющемуся процессу.</span><span class="sxs-lookup"><span data-stu-id="032aa-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="032aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="032aa-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="032aa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="032aa-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="032aa-106">окне Размер (в байтах) разностных метаданных.</span><span class="sxs-lookup"><span data-stu-id="032aa-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="032aa-107">окне Буфер, содержащий разностные метаданные.</span><span class="sxs-lookup"><span data-stu-id="032aa-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="032aa-108">Адрес буфера возвращается методом [IMetaDataEmit2:: саведелтатомемори](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="032aa-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="032aa-109">Относительные виртуальные адреса (RVA) в метаданных должны относиться к началу кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="032aa-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="032aa-110">окне Размер (в байтах) разностного кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="032aa-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="032aa-111">окне Буфер, содержащий обновленный код MSIL.</span><span class="sxs-lookup"><span data-stu-id="032aa-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="032aa-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="032aa-112">Remarks</span></span>  
 <span data-ttu-id="032aa-113">Параметр `pbMetadata` находится в особом формате разностных метаданных (в виде выходных данных [IMetaDataEmit2:: саведелтатомемори](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="032aa-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="032aa-114">`pbMetadata` принимает предыдущие метаданные в качестве основы и описывает отдельные изменения, которые необходимо применить к этой базе.</span><span class="sxs-lookup"><span data-stu-id="032aa-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="032aa-115">В отличие от этого, параметр `pbIL[`] содержит новый код MSIL для обновленного метода и предназначен для полной замены предыдущего MSIL для этого метода.</span><span class="sxs-lookup"><span data-stu-id="032aa-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="032aa-116">Если разностный код MSIL и метаданные были созданы в памяти отладчика, отладчик вызывает `ApplyChanges` для отправки изменений в среду CLR.</span><span class="sxs-lookup"><span data-stu-id="032aa-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="032aa-117">Среда выполнения обновляет свои таблицы метаданных, помещает новый код MSIL в процесс и настраивает JIT-компиляцию нового MSIL.</span><span class="sxs-lookup"><span data-stu-id="032aa-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="032aa-118">После применения изменений отладчик должен вызвать [IMetaDataEmit2:: ресетенклог](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) , чтобы подготовиться к следующему сеансу редактирования.</span><span class="sxs-lookup"><span data-stu-id="032aa-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="032aa-119">Затем отладчик может продолжить процесс.</span><span class="sxs-lookup"><span data-stu-id="032aa-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="032aa-120">Всякий раз, когда отладчик вызывает `ApplyChanges` для модуля, который имеет разностные метаданные, он также должен вызвать метод [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) с теми же разностными метаданными для всех своих копий метаданных этого модуля, за исключением копирования, используемой для отправки изменений.</span><span class="sxs-lookup"><span data-stu-id="032aa-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="032aa-121">Если копия метаданных по каким-либо причинам не синхронизирована с фактическими метаданными, то отладчик всегда может создать копию и получить новую копию.</span><span class="sxs-lookup"><span data-stu-id="032aa-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="032aa-122">В случае сбоя метода `ApplyChanges` сеанс отладки находится в недопустимом состоянии и должен быть перезапущен.</span><span class="sxs-lookup"><span data-stu-id="032aa-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="032aa-123">Требования</span><span class="sxs-lookup"><span data-stu-id="032aa-123">Requirements</span></span>  
 <span data-ttu-id="032aa-124">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="032aa-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="032aa-125">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="032aa-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="032aa-126">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="032aa-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="032aa-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="032aa-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
