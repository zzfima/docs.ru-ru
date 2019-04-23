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
ms.openlocfilehash: add1458bb3a50a5e5433e8cc7baaf47d750c927d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083677"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="de524-102">Перечисление CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="de524-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="de524-103">Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.</span><span class="sxs-lookup"><span data-stu-id="de524-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de524-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de524-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="de524-105">Участники</span><span class="sxs-lookup"><span data-stu-id="de524-105">Members</span></span>  
  
|<span data-ttu-id="de524-106">Член</span><span class="sxs-lookup"><span data-stu-id="de524-106">Member</span></span>|<span data-ttu-id="de524-107">Описание</span><span class="sxs-lookup"><span data-stu-id="de524-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="de524-108">Данные представляют собой 32-разрядную запись Windows-исключения.</span><span class="sxs-lookup"><span data-stu-id="de524-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="de524-109">Данные представляют собой 64-разрядную запись Windows-исключения.</span><span class="sxs-lookup"><span data-stu-id="de524-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de524-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="de524-110">Remarks</span></span>  
 <span data-ttu-id="de524-111">Является членом `CorDebugRecordFormat` передается перечисление [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) метод для указания формата массива байтов в его `pRecord` аргумент.</span><span class="sxs-lookup"><span data-stu-id="de524-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de524-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="de524-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de524-113">Требования</span><span class="sxs-lookup"><span data-stu-id="de524-113">Requirements</span></span>  
 <span data-ttu-id="de524-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de524-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de524-115">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de524-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de524-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de524-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de524-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de524-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de524-118">См. также</span><span class="sxs-lookup"><span data-stu-id="de524-118">See also</span></span>

- [<span data-ttu-id="de524-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="de524-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
