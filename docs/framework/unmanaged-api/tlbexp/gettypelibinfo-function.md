---
title: "Функция GetTypeLibInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetTypeLibInfo
api_location: TlbRef.dll
api_type: DLLExport
f1_keywords: GetTypeLibInfo
helpviewer_keywords: GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a5dc55a9538798b81dce9db02583c271b9f2ed54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="5bebd-102">Функция GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="5bebd-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="5bebd-103">Возвращает сведения об указанной библиотеки типов с помощью проверки его [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) структуры.</span><span class="sxs-lookup"><span data-stu-id="5bebd-103">Returns information about the specified type library by examining its [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bebd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bebd-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bebd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5bebd-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="5bebd-106">[in] Имя файла библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="5bebd-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="5bebd-107">[out] Идентификатор GUID для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="5bebd-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="5bebd-108">[out] Локализация идентификатор библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="5bebd-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="5bebd-109">[out] Объект [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) флаг, определяющий целевую операционную систему для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="5bebd-109">[out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="5bebd-110">Общие значения: SYS_WIN32 и SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="5bebd-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="5bebd-111">[out] Основной номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="5bebd-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="5bebd-112">Например, для версии *x.y*, основной номер версии — *x*.</span><span class="sxs-lookup"><span data-stu-id="5bebd-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="5bebd-113">[out] Дополнительный номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="5bebd-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="5bebd-114">Например, для версии *x.y*, дополнительный номер версии — *y*.</span><span class="sxs-lookup"><span data-stu-id="5bebd-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bebd-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="5bebd-115">Remarks</span></span>  
 <span data-ttu-id="5bebd-116">`GetTypeLibInfo` Функция вызывается функцией [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="5bebd-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="5bebd-117">Это средство создает библиотеку типов, описывающую типы в сборке среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5bebd-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="5bebd-118">Если какой-либо параметр имеет значение null, функция возвращает `HRESULT` из `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="5bebd-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="5bebd-119">В противном случае возвращает значение `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="5bebd-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bebd-120">Требования</span><span class="sxs-lookup"><span data-stu-id="5bebd-120">Requirements</span></span>  
 <span data-ttu-id="5bebd-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bebd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bebd-122">**Заголовок:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="5bebd-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="5bebd-123">**Библиотека:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="5bebd-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="5bebd-124">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bebd-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bebd-125">См. также</span><span class="sxs-lookup"><span data-stu-id="5bebd-125">See Also</span></span>  
 [<span data-ttu-id="5bebd-126">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="5bebd-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 <span data-ttu-id="5bebd-127">[Функция LoadTypeLibEx](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5bebd-127">[LoadTypeLibEx Function](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)</span></span>
