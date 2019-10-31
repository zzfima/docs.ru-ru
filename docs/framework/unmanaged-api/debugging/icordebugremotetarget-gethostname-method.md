---
title: Метод ICorDebugRemoteTarget::GetHostName
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
ms.openlocfilehash: a9a6ca9ae3cdb1c6a7398d08c9f99e3cde125cf6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131902"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="1c385-102">Метод ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="1c385-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="1c385-103">Возвращает полное доменное имя или IPv4-адрес целевого компьютера удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="1c385-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="1c385-104">В настоящее время IPV6 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1c385-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c385-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c385-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c385-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c385-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="1c385-107">окне Размер `szHostName`ного буфера в символах.</span><span class="sxs-lookup"><span data-stu-id="1c385-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="1c385-108">Если этот параметр имеет значение 0 (ноль), `szHostName` должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="1c385-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="1c385-109">заполняет Количество символов, включая знак завершения null, в имени узла или IP-адресе.</span><span class="sxs-lookup"><span data-stu-id="1c385-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="1c385-110">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="1c385-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="1c385-111">заполняет Буфер, содержащий имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="1c385-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c385-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1c385-112">Return Value</span></span>  
 <span data-ttu-id="1c385-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c385-113">S_OK</span></span>  
 <span data-ttu-id="1c385-114">Имя узла или IP-адрес успешно возвращены.</span><span class="sxs-lookup"><span data-stu-id="1c385-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="1c385-115">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="1c385-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="1c385-116">Не удалось вернуть имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="1c385-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c385-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="1c385-117">Remarks</span></span>  
 <span data-ttu-id="1c385-118">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="1c385-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="1c385-119">Он должен следовать парадигме нескольких вызовов: при первом вызове вызывающий объект передает значение NULL в `cchHostName` и `szHostName`, а `pcchHostName` возвращает размер требуемого буфера.</span><span class="sxs-lookup"><span data-stu-id="1c385-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="1c385-120">При втором вызове размер, который был ранее возвращен, передается `cchHostName`, и буфер соответствующего размера передается в `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="1c385-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c385-121">Требования</span><span class="sxs-lookup"><span data-stu-id="1c385-121">Requirements</span></span>  
 <span data-ttu-id="1c385-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c385-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c385-123">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="1c385-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="1c385-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c385-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c385-125">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="1c385-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c385-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1c385-126">See also</span></span>

- [<span data-ttu-id="1c385-127">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="1c385-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="1c385-128">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="1c385-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
