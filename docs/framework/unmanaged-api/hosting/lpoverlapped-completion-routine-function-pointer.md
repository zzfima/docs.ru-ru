---
title: "Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LPOVERLAPPED_COMPLETION_ROUTINE
api_location: mscoree.dll
api_type: COM
f1_keywords: LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords: LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b1846cf8fff5c41fc54ddeec5b495b50c63581c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lpoverlappedcompletionroutine-function-pointer"></a><span data-ttu-id="3bd4f-102">Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="3bd4f-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="3bd4f-103">Указывает на функцию, которая уведомляет основное приложение перекрывающегося (то есть асинхронные) завершения ввода-вывода на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3bd4f-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="3bd4f-104">Указатель на функцию рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3bd4f-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bd4f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bd4f-105">Syntax</span></span>  
  
```  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3bd4f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3bd4f-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="3bd4f-107">[in] Значение, которое представляет собой код ошибки, если устройство было закрыто; в противном случае это значение равно нулю.</span><span class="sxs-lookup"><span data-stu-id="3bd4f-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="3bd4f-108">Закрытие устройства приводит к немедленному завершению всех ожидающих операций ввода-вывода на устройстве.</span><span class="sxs-lookup"><span data-stu-id="3bd4f-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="3bd4f-109">[in] Число байтов, переданных в операции ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="3bd4f-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="3bd4f-110">[in] Указатель на структуру, содержащую информацию, используемую для выполнения запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="3bd4f-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3bd4f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="3bd4f-111">Remarks</span></span>  
 <span data-ttu-id="3bd4f-112">Функция, к которому `LPOVERLAPPED_COMPLETION_ROUTINE` точек — функция обратного вызова и должны быть реализованы разработчиком ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="3bd4f-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="3bd4f-113">Функция обратного вызова позволяет основному приложению обработать выполненный запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="3bd4f-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bd4f-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3bd4f-114">Requirements</span></span>  
 <span data-ttu-id="3bd4f-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bd4f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bd4f-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3bd4f-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bd4f-117">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="3bd4f-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="3bd4f-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bd4f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd4f-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3bd4f-119">See Also</span></span>  
 [<span data-ttu-id="3bd4f-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="3bd4f-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
