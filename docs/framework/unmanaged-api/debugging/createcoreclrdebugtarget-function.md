---
title: Функция CreateCoreClrDebugTarget
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: 0b210f105495fa3f5595adbcb0805e1d1fb62310
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179219"
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="10ab6-102">Функция CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="10ab6-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="10ab6-103">Создает подключение к прокси-серверу отладчика, который работает на удаленной машине, и возвращает объект [ICoreClrDebugTarget,](icoreclrdebugtarget-interface.md) который может быть использован для запроса запущенных процессов и загруженных времен выполнения на удаленной машине.</span><span class="sxs-lookup"><span data-stu-id="10ab6-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ab6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10ab6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10ab6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="10ab6-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="10ab6-106">[in] IPv4-адрес удаленного целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="10ab6-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="10ab6-107">(ваут) Указатель на указатель на объект [ICoreClrDebugTarget,](icoreclrdebugtarget-interface.md) который будет создан.</span><span class="sxs-lookup"><span data-stu-id="10ab6-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10ab6-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10ab6-108">Return Value</span></span>  
 <span data-ttu-id="10ab6-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="10ab6-109">S_OK</span></span>  
 <span data-ttu-id="10ab6-110">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="10ab6-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="10ab6-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="10ab6-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="10ab6-112">Не удается выделить достаточно памяти для `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="10ab6-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="10ab6-113">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="10ab6-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="10ab6-114">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="10ab6-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10ab6-115">Требования</span><span class="sxs-lookup"><span data-stu-id="10ab6-115">Requirements</span></span>  
 <span data-ttu-id="10ab6-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10ab6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ab6-117">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="10ab6-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="10ab6-118">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="10ab6-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="10ab6-119">**Рамочные версии .NET:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="10ab6-119">**.NET Framework Versions:** 3.5 SP1</span></span>
