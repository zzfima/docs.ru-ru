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
ms.openlocfilehash: 35767529d9433764b7eed0b3b4acdd806f399962
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792183"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="b312a-102">Метод ICorDebugProcess7::SetWriteableMetadataUpdateMode</span><span class="sxs-lookup"><span data-stu-id="b312a-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="b312a-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="b312a-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b312a-104">Настраивает порядок, согласно которому отладчик обрабатывает обновления находящихся в памяти метаданных в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="b312a-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b312a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b312a-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b312a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b312a-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="b312a-107">Значение перечисления [вритеаблеметадатаупдатемоде](writeablemetadataupdatemode-enumeration.md) , указывающее, являются ли обновления в памяти в целевом процессе видимыми (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) или невидимыми (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) отладчиком.</span><span class="sxs-lookup"><span data-stu-id="b312a-107">A [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b312a-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="b312a-108">Remarks</span></span>  
 <span data-ttu-id="b312a-109">Обновления для метаданных в целевом процессе могут поступать из режима "Изменить и продолжить", профилировщика или <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b312a-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b312a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b312a-110">Requirements</span></span>  
 <span data-ttu-id="b312a-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b312a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b312a-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b312a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b312a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b312a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b312a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b312a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b312a-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b312a-115">See also</span></span>

- [<span data-ttu-id="b312a-116">Интерфейс ICorDebugProcess7</span><span class="sxs-lookup"><span data-stu-id="b312a-116">ICorDebugProcess7 Interface</span></span>](icordebugprocess7-interface.md)
- [<span data-ttu-id="b312a-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b312a-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
