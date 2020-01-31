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
ms.openlocfilehash: 99fc89d1aee6c9f0fbffc193e12ce563e820f268
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789287"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="2bb66-102">Перечисление CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="2bb66-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="2bb66-103">Описывает формат данных в массиве байтов, который содержит информацию о событии отладки собственного исключения.</span><span class="sxs-lookup"><span data-stu-id="2bb66-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb66-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bb66-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="2bb66-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2bb66-105">Members</span></span>  
  
|<span data-ttu-id="2bb66-106">Член</span><span class="sxs-lookup"><span data-stu-id="2bb66-106">Member</span></span>|<span data-ttu-id="2bb66-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2bb66-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="2bb66-108">Данные представляют собой 32-разрядную запись Windows-исключения.</span><span class="sxs-lookup"><span data-stu-id="2bb66-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="2bb66-109">Данные представляют собой 64-разрядную запись Windows-исключения.</span><span class="sxs-lookup"><span data-stu-id="2bb66-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bb66-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="2bb66-110">Remarks</span></span>  
 <span data-ttu-id="2bb66-111">Член перечисления `CorDebugRecordFormat` передается методу [DecodeEvent](icordebugprocess6-decodeevent-method.md) для указания формата массива байтов в его `pRecord` аргументе.</span><span class="sxs-lookup"><span data-stu-id="2bb66-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2bb66-112">Это перечисление предназначено для использования только в сценариях отладки .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2bb66-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb66-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2bb66-113">Requirements</span></span>  
 <span data-ttu-id="2bb66-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bb66-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb66-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bb66-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bb66-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bb66-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bb66-117">**Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bb66-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb66-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="2bb66-118">See also</span></span>

- [<span data-ttu-id="2bb66-119">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="2bb66-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
