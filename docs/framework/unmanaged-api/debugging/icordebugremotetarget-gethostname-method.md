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
ms.openlocfilehash: f177d441da3bd967750781e487d9fed42bc132f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791950"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="f06d8-102">Метод ICorDebugRemoteTarget::GetHostName</span><span class="sxs-lookup"><span data-stu-id="f06d8-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="f06d8-103">Возвращает полное доменное имя или IPv4-адрес целевого компьютера удаленной отладки.</span><span class="sxs-lookup"><span data-stu-id="f06d8-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="f06d8-104">В настоящее время IPV6 не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f06d8-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06d8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f06d8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="f06d8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f06d8-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="f06d8-107">окне Размер `szHostName`ного буфера в символах.</span><span class="sxs-lookup"><span data-stu-id="f06d8-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="f06d8-108">Если этот параметр имеет значение 0 (ноль), `szHostName` должен иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="f06d8-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="f06d8-109">заполняет Количество символов, включая знак завершения null, в имени узла или IP-адресе.</span><span class="sxs-lookup"><span data-stu-id="f06d8-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="f06d8-110">Этот параметр может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="f06d8-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="f06d8-111">заполняет Буфер, содержащий имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="f06d8-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f06d8-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f06d8-112">Return Value</span></span>  
 <span data-ttu-id="f06d8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f06d8-113">S_OK</span></span>  
 <span data-ttu-id="f06d8-114">Имя узла или IP-адрес успешно возвращены.</span><span class="sxs-lookup"><span data-stu-id="f06d8-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="f06d8-115">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="f06d8-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="f06d8-116">Не удалось вернуть имя узла или IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="f06d8-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f06d8-117">Заметки</span><span class="sxs-lookup"><span data-stu-id="f06d8-117">Remarks</span></span>  
 <span data-ttu-id="f06d8-118">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="f06d8-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="f06d8-119">Он должен следовать парадигме нескольких вызовов: при первом вызове вызывающий объект передает значение NULL в `cchHostName` и `szHostName`, а `pcchHostName` возвращает размер требуемого буфера.</span><span class="sxs-lookup"><span data-stu-id="f06d8-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="f06d8-120">При втором вызове размер, который был ранее возвращен, передается `cchHostName`, и буфер соответствующего размера передается в `szHostName`.</span><span class="sxs-lookup"><span data-stu-id="f06d8-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f06d8-121">Требования</span><span class="sxs-lookup"><span data-stu-id="f06d8-121">Requirements</span></span>  
 <span data-ttu-id="f06d8-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f06d8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f06d8-123">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="f06d8-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="f06d8-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f06d8-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f06d8-125">**.NET Framework версии:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="f06d8-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f06d8-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="f06d8-126">See also</span></span>

- [<span data-ttu-id="f06d8-127">Интерфейс ICorDebugRemoteTarget</span><span class="sxs-lookup"><span data-stu-id="f06d8-127">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="f06d8-128">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="f06d8-128">ICorDebug Interface</span></span>](icordebug-interface.md)
