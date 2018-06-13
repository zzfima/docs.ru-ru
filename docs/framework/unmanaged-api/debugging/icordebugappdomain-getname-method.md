---
title: Метод ICorDebugAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84f895e749fc8f2520dbce3caf9e6c11fda78a7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405773"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="cae2b-102">Метод ICorDebugAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="cae2b-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="cae2b-103">Возвращает имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="cae2b-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae2b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cae2b-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cae2b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cae2b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="cae2b-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="cae2b-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="cae2b-107">Это значение равным нулю, чтобы поместить этот метод в режиме запроса.</span><span class="sxs-lookup"><span data-stu-id="cae2b-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cae2b-108">[out] Указатель на размер имя или число символов, фактически извлеченных в `szName`.</span><span class="sxs-lookup"><span data-stu-id="cae2b-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="cae2b-109">В режиме запроса, это значение позволяет вызывающему объекту определить размер буфера для выделения для имени.</span><span class="sxs-lookup"><span data-stu-id="cae2b-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="cae2b-110">[out] Массив, который содержит имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="cae2b-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cae2b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="cae2b-111">Remarks</span></span>  
 <span data-ttu-id="cae2b-112">Отладчик вызывает `GetName` метод один раз, чтобы получить размер буфера, который необходим для имени.</span><span class="sxs-lookup"><span data-stu-id="cae2b-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="cae2b-113">Отладчик выделяет буфер и затем вызывает метод во второй раз для заполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="cae2b-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="cae2b-114">Первый вызов для получения размера имени, называется *режим запроса*.</span><span class="sxs-lookup"><span data-stu-id="cae2b-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cae2b-115">Требования</span><span class="sxs-lookup"><span data-stu-id="cae2b-115">Requirements</span></span>  
 <span data-ttu-id="cae2b-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cae2b-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cae2b-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cae2b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cae2b-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cae2b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cae2b-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cae2b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
