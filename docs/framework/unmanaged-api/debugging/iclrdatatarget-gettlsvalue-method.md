---
title: Метод ICLRDataTarget::GetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21fa9a17067f754fe9b13c4d32193856a57750ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698139"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="90ec0-102">Метод ICLRDataTarget::GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="90ec0-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="90ec0-103">Возвращает значение из локального хранилища потока (TLS) из указанного потока в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="90ec0-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="90ec0-104">Этот метод вызывается службами доступа к данным среды CLR.</span><span class="sxs-lookup"><span data-stu-id="90ec0-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90ec0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90ec0-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90ec0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="90ec0-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="90ec0-107">[in] Идентификатор потока в целевом процессе операционной системы.</span><span class="sxs-lookup"><span data-stu-id="90ec0-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="90ec0-108">[in] Индекс расположения.</span><span class="sxs-lookup"><span data-stu-id="90ec0-108">[in] The index of the location.</span></span> <span data-ttu-id="90ec0-109">Это значение должно быть допустимым индексом в локальном хранилище из указанного потока.</span><span class="sxs-lookup"><span data-stu-id="90ec0-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="90ec0-110">[out] Указатель на `CLRDATA_ADDRESS` возвращается значение, которое указывает значение из заданного расположения TLS.</span><span class="sxs-lookup"><span data-stu-id="90ec0-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90ec0-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="90ec0-111">Remarks</span></span>  
 <span data-ttu-id="90ec0-112">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="90ec0-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90ec0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="90ec0-113">Requirements</span></span>  
 <span data-ttu-id="90ec0-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90ec0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90ec0-115">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="90ec0-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="90ec0-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90ec0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90ec0-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90ec0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90ec0-118">См. также</span><span class="sxs-lookup"><span data-stu-id="90ec0-118">See also</span></span>

- [<span data-ttu-id="90ec0-119">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="90ec0-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
