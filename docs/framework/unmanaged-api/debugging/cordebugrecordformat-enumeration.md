---
title: Перечисление CorDebugRecordFormat
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: adb13688791cd7d8f467780da1895d4f9fe6e990
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739643"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="10e51-102">Перечисление CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="10e51-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="10e51-103">Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.</span><span class="sxs-lookup"><span data-stu-id="10e51-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10e51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10e51-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="10e51-105">Участники</span><span class="sxs-lookup"><span data-stu-id="10e51-105">Members</span></span>  
  
|<span data-ttu-id="10e51-106">Член</span><span class="sxs-lookup"><span data-stu-id="10e51-106">Member</span></span>|<span data-ttu-id="10e51-107">Описание</span><span class="sxs-lookup"><span data-stu-id="10e51-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="10e51-108">Данные представляют собой 32-разрядную запись Windows-исключения.</span><span class="sxs-lookup"><span data-stu-id="10e51-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="10e51-109">Данные представляют собой 64-разрядную запись Windows-исключения.</span><span class="sxs-lookup"><span data-stu-id="10e51-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10e51-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="10e51-110">Remarks</span></span>  
 <span data-ttu-id="10e51-111">Является членом `CorDebugRecordFormat` передается перечисление [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод для указания формата массива байтов в его `pRecord` аргумент.</span><span class="sxs-lookup"><span data-stu-id="10e51-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10e51-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="10e51-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10e51-113">Требования</span><span class="sxs-lookup"><span data-stu-id="10e51-113">Requirements</span></span>  
 <span data-ttu-id="10e51-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10e51-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10e51-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10e51-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10e51-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10e51-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10e51-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10e51-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10e51-118">См. также</span><span class="sxs-lookup"><span data-stu-id="10e51-118">See also</span></span>

- [<span data-ttu-id="10e51-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="10e51-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
