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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1536a89d0e85480d3829939c40cd986fe65883df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422475"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="248c1-102">Метод ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="248c1-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="248c1-103">Возвращает полное доменное имя или IPv4-адрес удаленной отладки конечного компьютера.</span><span class="sxs-lookup"><span data-stu-id="248c1-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="248c1-104">IPv6 не поддерживается в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="248c1-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="248c1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="248c1-105">Syntax</span></span>  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="248c1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="248c1-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="248c1-107">[in] Размер (в символах) для `szHostName` буфера.</span><span class="sxs-lookup"><span data-stu-id="248c1-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="248c1-108">Если этот параметр равен 0 (нуль), `szHostName` должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="248c1-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="248c1-109">[out] Число символов, включая знак завершения null, имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="248c1-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="248c1-110">Этот параметр может быть нулевым.</span><span class="sxs-lookup"><span data-stu-id="248c1-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="248c1-111">[out] Буфер, содержащий имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="248c1-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="248c1-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="248c1-112">Return Value</span></span>  
 <span data-ttu-id="248c1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="248c1-113">S_OK</span></span>  
 <span data-ttu-id="248c1-114">Имя узла или IP-адрес был успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="248c1-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="248c1-115">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="248c1-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="248c1-116">Не удалось вернуть имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="248c1-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="248c1-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="248c1-117">Remarks</span></span>  
 <span data-ttu-id="248c1-118">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="248c1-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="248c1-119">Он должен соответствовать несколько вызовов парадигма: при первом вызове вызывающий объект передает значение null как `cchHostName` и `szHostName`, и `pcchHostName` возвращает размер буфера.</span><span class="sxs-lookup"><span data-stu-id="248c1-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer .</span></span> <span data-ttu-id="248c1-120">При втором вызове переданный размер, который ранее был возвращен `cchHostName`, и переданный буфер соответствующего размера `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="248c1-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="248c1-121">Требования</span><span class="sxs-lookup"><span data-stu-id="248c1-121">Requirements</span></span>  
 <span data-ttu-id="248c1-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="248c1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="248c1-123">**Заголовок:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="248c1-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="248c1-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="248c1-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="248c1-125">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="248c1-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="248c1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="248c1-126">See Also</span></span>  
 [<span data-ttu-id="248c1-127">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="248c1-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="248c1-128">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="248c1-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
