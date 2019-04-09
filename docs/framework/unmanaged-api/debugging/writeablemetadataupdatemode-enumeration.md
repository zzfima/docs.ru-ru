---
title: Перечисление WriteableMetadataUpdateMode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62e4328b75a7f6fecc28cd620ec3ac18460316c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111141"
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="edcd7-102">Перечисление WriteableMetadataUpdateMode</span><span class="sxs-lookup"><span data-stu-id="edcd7-102">WriteableMetadataUpdateMode Enumeration</span></span>
<span data-ttu-id="edcd7-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="edcd7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="edcd7-104">Предоставляет значения, указывающие, будут ли видны в отладчике обновления копии метаданных в памяти.</span><span class="sxs-lookup"><span data-stu-id="edcd7-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edcd7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="edcd7-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="edcd7-106">Участники</span><span class="sxs-lookup"><span data-stu-id="edcd7-106">Members</span></span>  
  
|<span data-ttu-id="edcd7-107">Имя члена</span><span class="sxs-lookup"><span data-stu-id="edcd7-107">Member name</span></span>|<span data-ttu-id="edcd7-108">Описание</span><span class="sxs-lookup"><span data-stu-id="edcd7-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="edcd7-109">Поддерживает совместимость с предыдущими версиями платформы .NET Framework, делая видимыми обновления находящихся в памяти метаданных.</span><span class="sxs-lookup"><span data-stu-id="edcd7-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="edcd7-110">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="edcd7-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="edcd7-111">Делает обновления находящихся в памяти метаданных видимыми в отладчике.</span><span class="sxs-lookup"><span data-stu-id="edcd7-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edcd7-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="edcd7-112">Remarks</span></span>  
 <span data-ttu-id="edcd7-113">Является членом `WriteableMetadataUpdateMode` перечисления может быть передан [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) метод для управления, обновляются ли в памяти метаданных в целевом процессе являются видимыми для отладчика.</span><span class="sxs-lookup"><span data-stu-id="edcd7-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="edcd7-114">Параметр `LegacyCompatPolicy` обеспечивает такое же поведение, как и до версии 4.5.2 платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="edcd7-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="edcd7-115">Чаще всего это означает, что метаданные из обновлений не видны.</span><span class="sxs-lookup"><span data-stu-id="edcd7-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="edcd7-116">В то же время вызовы ряда методов отладчика неявно вынуждают его делать обновления видимыми.</span><span class="sxs-lookup"><span data-stu-id="edcd7-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="edcd7-117">Например, если отладчик передает [ICorDebugILFrame::GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) индекс переменной, не найден в исходных метаданных метода, все метаданные для модуля обновляется до моментального снимка, текущее состояние соответствия процесс.</span><span class="sxs-lookup"><span data-stu-id="edcd7-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="edcd7-118">Другими словами, при наличии параметра `LegacyCompatPolicy` отладчик может не видеть вообще, видеть частично или видеть все доступные обновления метаданных в зависимости от того, как он использует другие части неуправляемого API отладки.</span><span class="sxs-lookup"><span data-stu-id="edcd7-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edcd7-119">Требования</span><span class="sxs-lookup"><span data-stu-id="edcd7-119">Requirements</span></span>  
 <span data-ttu-id="edcd7-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edcd7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edcd7-121">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="edcd7-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="edcd7-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edcd7-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="edcd7-123">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="edcd7-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="edcd7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="edcd7-124">See also</span></span>

- [<span data-ttu-id="edcd7-125">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="edcd7-125">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="edcd7-126">Метод SetWriteableMetadataUpdateMode</span><span class="sxs-lookup"><span data-stu-id="edcd7-126">SetWriteableMetadataUpdateMode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
