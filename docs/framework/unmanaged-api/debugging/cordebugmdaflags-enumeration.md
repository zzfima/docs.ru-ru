---
title: "Перечисление CorDebugMDAFlags"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugMDAFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugMDAFlags
helpviewer_keywords: CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 827825e4012b421caa4e05702a6f1a1b863ac69d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="f0338-102">Перечисление CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="f0338-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="f0338-103">Указывает состояние потока, по которому был вызван помощник по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f0338-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0338-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0338-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f0338-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f0338-105">Members</span></span>  
  
|<span data-ttu-id="f0338-106">Член</span><span class="sxs-lookup"><span data-stu-id="f0338-106">Member</span></span>|<span data-ttu-id="f0338-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f0338-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="f0338-108">Поток, на котором был запущен MDA перенесена, так как был запущен MDA.</span><span class="sxs-lookup"><span data-stu-id="f0338-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0338-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0338-109">Remarks</span></span>  
 <span data-ttu-id="f0338-110">Если стек вызова больше не описывает, где изначально был вызван MDA, поток рассматривается как имеющий *спящий режим*.</span><span class="sxs-lookup"><span data-stu-id="f0338-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="f0338-111">Это необычное обстоятельство при выполнении недопустимой операции при выходе из потока.</span><span class="sxs-lookup"><span data-stu-id="f0338-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0338-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f0338-112">Requirements</span></span>  
 <span data-ttu-id="f0338-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0338-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0338-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0338-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0338-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0338-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0338-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0338-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0338-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f0338-117">See Also</span></span>  
 [<span data-ttu-id="f0338-118">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="f0338-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
