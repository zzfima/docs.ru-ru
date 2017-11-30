---
title: "Функция CreateCoreClrDebugTarget"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateCorClrDebugTarget
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1f52bddb5d5f11d36fcf8b833dd6fe65f9c0a4c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="createcoreclrdebugtarget-function"></a><span data-ttu-id="0a634-102">Функция CreateCoreClrDebugTarget</span><span class="sxs-lookup"><span data-stu-id="0a634-102">CreateCoreClrDebugTarget Function</span></span>
<span data-ttu-id="0a634-103">Создает подключение к прокси-серверу отладчика, выполняется на удаленном компьютере и возвращает [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) объект, который может использоваться для запроса выполняющихся процессов и загруженных сред выполнения на удаленном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0a634-103">Creates a connection to a debugger proxy that is running on a remote machine, and returns an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that can be used to query running processes and loaded runtimes on the remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a634-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a634-104">Syntax</span></span>  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a634-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a634-105">Parameters</span></span>  
 `dwAddress`  
 <span data-ttu-id="0a634-106">[in] IPv4-адрес удаленного целевого компьютера.</span><span class="sxs-lookup"><span data-stu-id="0a634-106">[in] IPv4 address of a remote target machine.</span></span>  
  
 `ppTarget`  
 <span data-ttu-id="0a634-107">[out] Указатель на указатель на [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) объекта, который будет создан.</span><span class="sxs-lookup"><span data-stu-id="0a634-107">[out] Pointer to a pointer to an [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) object that will be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a634-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a634-108">Return Value</span></span>  
 <span data-ttu-id="0a634-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a634-109">S_OK</span></span>  
 <span data-ttu-id="0a634-110">Количество сред CLR в процессе было успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="0a634-110">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="0a634-111">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0a634-111">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="0a634-112">Не удается выделить достаточно памяти для `ppTarget`.</span><span class="sxs-lookup"><span data-stu-id="0a634-112">Unable to allocate enough memory for `ppTarget`.</span></span>  
  
 <span data-ttu-id="0a634-113">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="0a634-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="0a634-114">Прочие сбои.</span><span class="sxs-lookup"><span data-stu-id="0a634-114">Other failures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a634-115">Требования</span><span class="sxs-lookup"><span data-stu-id="0a634-115">Requirements</span></span>  
 <span data-ttu-id="0a634-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a634-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a634-117">**Заголовок:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="0a634-117">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="0a634-118">**Библиотека:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="0a634-118">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="0a634-119">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="0a634-119">**.NET Framework Versions:** 3.5 SP1</span></span>
