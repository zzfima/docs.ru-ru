---
title: Метод ICorDebugProcess7::SetWriteableMetadataUpdateMode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70d8f5bf23b5cdf0714bfbb8c8571f9412ad7115
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487292"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="34eb2-102">Метод ICorDebugProcess7::SetWriteableMetadataUpdateMode</span><span class="sxs-lookup"><span data-stu-id="34eb2-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="34eb2-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="34eb2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="34eb2-104">Настраивает порядок, согласно которому отладчик обрабатывает обновления находящихся в памяти метаданных в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="34eb2-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34eb2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34eb2-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34eb2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="34eb2-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="34eb2-107">Объект [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) значение перечисления, указывающее, являются ли видимыми обновления находящихся в памяти метаданных в целевом процессе (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) или не отображается (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) для отладчика.</span><span class="sxs-lookup"><span data-stu-id="34eb2-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34eb2-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="34eb2-108">Remarks</span></span>  
 <span data-ttu-id="34eb2-109">Обновления для метаданных в целевом процессе могут поступать из режима "Изменить и продолжить", профилировщика или <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34eb2-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34eb2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="34eb2-110">Requirements</span></span>  
 <span data-ttu-id="34eb2-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34eb2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34eb2-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34eb2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34eb2-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34eb2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34eb2-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34eb2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34eb2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="34eb2-115">See also</span></span>
- [<span data-ttu-id="34eb2-116">Интерфейс ICorDebugProcess7</span><span class="sxs-lookup"><span data-stu-id="34eb2-116">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)
- [<span data-ttu-id="34eb2-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="34eb2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
