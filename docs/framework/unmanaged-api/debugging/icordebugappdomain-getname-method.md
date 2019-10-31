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
ms.openlocfilehash: 2c9aa6792885c685195049948a540453b1f5235e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110314"
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="059fb-102">Метод ICorDebugAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="059fb-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="059fb-103">Возвращает имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="059fb-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="059fb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="059fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="059fb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="059fb-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="059fb-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="059fb-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="059fb-107">Присвойте этому параметру значение 0, чтобы перевести этот метод в режим запроса.</span><span class="sxs-lookup"><span data-stu-id="059fb-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="059fb-108">заполняет Указатель на размер имени или количества символов, фактически возвращаемых в `szName`.</span><span class="sxs-lookup"><span data-stu-id="059fb-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="059fb-109">В режиме запроса это значение позволяет вызывающему объекту понять, насколько большой размер буфера выделяется для имени.</span><span class="sxs-lookup"><span data-stu-id="059fb-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="059fb-110">заполняет Массив, в котором хранится имя домена приложения.</span><span class="sxs-lookup"><span data-stu-id="059fb-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="059fb-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="059fb-111">Remarks</span></span>  
 <span data-ttu-id="059fb-112">Отладчик вызывает метод `GetName` один раз, чтобы получить размер буфера, необходимого для имени.</span><span class="sxs-lookup"><span data-stu-id="059fb-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="059fb-113">Отладчик выделяет буфер, а затем вызывает метод еще раз для заполнения буфера.</span><span class="sxs-lookup"><span data-stu-id="059fb-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="059fb-114">Первый вызов для получения размера имени называется *режимом запроса*.</span><span class="sxs-lookup"><span data-stu-id="059fb-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="059fb-115">Требования</span><span class="sxs-lookup"><span data-stu-id="059fb-115">Requirements</span></span>  
 <span data-ttu-id="059fb-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="059fb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="059fb-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="059fb-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="059fb-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="059fb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="059fb-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="059fb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
