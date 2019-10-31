---
title: Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE
ms.date: 03/30/2017
api_name:
- LPOVERLAPPED_COMPLETION_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE
helpviewer_keywords:
- LPOVERLAPPED_COMPLETION_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 5fb645d9-b818-401c-8c2c-c30d86de58ba
topic_type:
- apiref
ms.openlocfilehash: 103ac75e7c3eaf9739c3a448ff1c052c158621db
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090908"
---
# <a name="lpoverlapped_completion_routine-function-pointer"></a><span data-ttu-id="ba005-102">Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="ba005-102">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>
<span data-ttu-id="ba005-103">Указывает на функцию, которая уведомляет узел при завершении перекрытия (асинхронного) ввода-вывода на устройство.</span><span class="sxs-lookup"><span data-stu-id="ba005-103">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 <span data-ttu-id="ba005-104">Этот указатель функции является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ba005-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba005-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba005-105">Syntax</span></span>  
  
```cpp  
typedef VOID (*LPOVERLAPPED_COMPLETION_ROUTINE) (  
    [in] DWORD  dwErrorCode,  
    [in] DWORD  dwNumberOfBytesTransfered,  
    [in] LPVOID lpOverlapped  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba005-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ba005-106">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="ba005-107">окне Значение, которое является кодом ошибки, если устройство было закрыто; в противном случае это значение равно нулю.</span><span class="sxs-lookup"><span data-stu-id="ba005-107">[in] A value that is an error code if the device has been closed; otherwise, this value is zero.</span></span>  
  
 <span data-ttu-id="ba005-108">Закрытие устройства приводит к немедленному завершению операций ввода-вывода на устройстве.</span><span class="sxs-lookup"><span data-stu-id="ba005-108">Closing a device causes all pending I/O to the device to be completed immediately.</span></span>  
  
 `dwNumberOfBytesTransfered`  
 <span data-ttu-id="ba005-109">окне Число байтов, передаваемых операцией ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ba005-109">[in] The number of bytes transferred by the I/O operation.</span></span>  
  
 `lpOverlapped`  
 <span data-ttu-id="ba005-110">окне Указатель на структуру, содержащую сведения, используемые для завершения запроса ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ba005-110">[in] A pointer to a structure that contains information to be used to complete the I/O request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba005-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="ba005-111">Remarks</span></span>  
 <span data-ttu-id="ba005-112">Функция, к которой `LPOVERLAPPED_COMPLETION_ROUTINE` Points, является функцией обратного вызова и должна быть реализована модулем записи размещающего приложения.</span><span class="sxs-lookup"><span data-stu-id="ba005-112">The function to which `LPOVERLAPPED_COMPLETION_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="ba005-113">Функция обратного вызова позволяет узлу обработать завершенный запрос ввода-вывода.</span><span class="sxs-lookup"><span data-stu-id="ba005-113">The callback function allows the host to process the completed I/O request.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba005-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ba005-114">Requirements</span></span>  
 <span data-ttu-id="ba005-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba005-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba005-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ba005-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba005-117">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="ba005-117">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="ba005-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba005-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba005-119">См. также</span><span class="sxs-lookup"><span data-stu-id="ba005-119">See also</span></span>

- [<span data-ttu-id="ba005-120">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="ba005-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
