---
title: Функция CreateVersionStringFromModule
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b68624b962ed610dbeecd3e4cead769ab1400f4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739209"
---
# <a name="createversionstringfrommodule-function"></a><span data-ttu-id="0d1f9-102">Функция CreateVersionStringFromModule</span><span class="sxs-lookup"><span data-stu-id="0d1f9-102">CreateVersionStringFromModule Function</span></span>
<span data-ttu-id="0d1f9-103">Создает строку версии из пути среды CLR в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-103">Creates a version string from a common language runtime (CLR) path in a target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d1f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d1f9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d1f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d1f9-105">Parameters</span></span>  
 `pidDebuggee`  
 <span data-ttu-id="0d1f9-106">[in] Идентификатор процесса, в котором загружается целевая среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-106">[in] Identifier of the process in which the target CLR is loaded.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="0d1f9-107">[in] Полный или относительный путь к целевой среде CLR, которая загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-107">[in] Full or relative path to the target CLR that is loaded in the process.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="0d1f9-108">[out] Буфер возврата для хранения строки версии целевой среды CLR.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-108">[out] Return buffer for storing the version string for the target CLR.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="0d1f9-109">[in] Размер `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-109">[in] Size of `pBuffer`.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="0d1f9-110">[out] Длина строки версии, возвращенной `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-110">[out] Length of the version string returned by `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d1f9-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0d1f9-111">Return Value</span></span>  
 <span data-ttu-id="0d1f9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d1f9-112">S_OK</span></span>  
 <span data-ttu-id="0d1f9-113">Строка версии для целевой среды CLR успешно возвращена в `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-113">The version string for the target CLR was successfully returned in `pBuffer`.</span></span>  
  
 <span data-ttu-id="0d1f9-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0d1f9-114">E_INVALIDARG</span></span>  
 <span data-ttu-id="0d1f9-115">Параметр `szModuleName` имеет значение null, либо один из параметров `pBuffer` и `cchBuffer` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-115">`szModuleName` is null, or either `pBuffer` or `cchBuffer` is null.</span></span> <span data-ttu-id="0d1f9-116">Оба параметра `pBuffer` и `cchBuffer` должны иметь значение null или не иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-116">`pBuffer` and `cchBuffer` must both be null or non-null.</span></span>  
  
 <span data-ttu-id="0d1f9-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="0d1f9-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>  
 <span data-ttu-id="0d1f9-118">Значение `pdwLength` больше значения `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-118">`pdwLength` is greater than `cchBuffer`.</span></span> <span data-ttu-id="0d1f9-119">Это может быть ожидаемым результатом, если вы передали значение null в оба параметра  `pBuffer` и `cchBuffer`, а также запросили необходимый размер буфера с помощью `pdwLength`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-119">This may be an expected result if you have passed null for both `pBuffer` and `cchBuffer`, and queried the necessary buffer size by using `pdwLength`.</span></span>  
  
 <span data-ttu-id="0d1f9-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="0d1f9-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span></span>  
 <span data-ttu-id="0d1f9-121">Параметр `szModuleName` не содержит путь к допустимой среде CLR в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-121">`szModuleName` does not contain a path to a valid CLR in the target process.</span></span>  
  
 <span data-ttu-id="0d1f9-122">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="0d1f9-122">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="0d1f9-123">Параметр `pidDebuggee` не ссылается на допустимый процесс, или произошел другой сбой.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-123">`pidDebuggee` does not refer to a valid process, or other failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d1f9-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d1f9-124">Remarks</span></span>  
 <span data-ttu-id="0d1f9-125">Эта функция принимает процесс CLR, который определяется параметром `pidDebuggee` и строкой пути, заданной параметром `szModuleName`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-125">This function accepts a CLR process that is identified by `pidDebuggee` and a string path that is specified by `szModuleName`.</span></span> <span data-ttu-id="0d1f9-126">Строка версии возвращается в буфер, на который указывает `pBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-126">The version string is returned in the buffer that `pBuffer` points to.</span></span> <span data-ttu-id="0d1f9-127">Эта строка непрозрачна для пользователя функции, то есть сама строка версии не имеет внутреннего смысла.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-127">This string is opaque to the function user; that is, there is no intrinsic meaning in the version string itself.</span></span> <span data-ttu-id="0d1f9-128">Он используется исключительно в контексте этой функции и [функция CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md).</span><span class="sxs-lookup"><span data-stu-id="0d1f9-128">It is used solely in the context of this function and the [CreateDebuggingInterfaceFromVersion function](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md).</span></span>  
  
 <span data-ttu-id="0d1f9-129">Эта функция должна вызываться дважды.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-129">This function should be called twice.</span></span> <span data-ttu-id="0d1f9-130">При первом вызове передайте значение null для обоих параметров `pBuffer` и `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-130">When you call it the first time, pass null for both `pBuffer` and `cchBuffer`.</span></span> <span data-ttu-id="0d1f9-131">После этого размер буфера, необходимый для `pBuffer`, будет возвращен в `pdwLength`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-131">When you do this, the size of the buffer necessary for `pBuffer` will be returned in `pdwLength`.</span></span> <span data-ttu-id="0d1f9-132">Затем можно вызвать эту функцию во второй раз и передать буфер в `pBuffer` и его размер в `cchBuffer`.</span><span class="sxs-lookup"><span data-stu-id="0d1f9-132">You can then call the function a second time, and pass the buffer in `pBuffer` and its size in `cchBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d1f9-133">Требования</span><span class="sxs-lookup"><span data-stu-id="0d1f9-133">Requirements</span></span>  
 <span data-ttu-id="0d1f9-134">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d1f9-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d1f9-135">**Заголовок:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="0d1f9-135">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="0d1f9-136">**Библиотека:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="0d1f9-136">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="0d1f9-137">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="0d1f9-137">**.NET Framework Versions:** 3.5 SP1</span></span>
