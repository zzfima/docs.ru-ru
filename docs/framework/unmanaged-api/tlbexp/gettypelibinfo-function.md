---
title: Функция GetTypeLibInfo
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ec28c581b8e6e0aff3a2765720b6e9795be931b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615518"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="3804f-102">Функция GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="3804f-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="3804f-103">Возвращает сведения об указанной библиотеки типов с помощью проверки его [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) структуры.</span><span class="sxs-lookup"><span data-stu-id="3804f-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3804f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3804f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="3804f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3804f-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="3804f-106">[in] Имя файла библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3804f-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="3804f-107">[out] Идентификатор GUID библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3804f-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="3804f-108">[out] Идентификатор локализации библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3804f-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="3804f-109">[out] Объект [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) флаг, определяющий, Целевая операционная система для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3804f-109">[out] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="3804f-110">Обычные значения: SYS_WIN32 и SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="3804f-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="3804f-111">[out] Основной номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3804f-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="3804f-112">Например, для версии *x.y*, основной номер версии — *x*.</span><span class="sxs-lookup"><span data-stu-id="3804f-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="3804f-113">[out] Дополнительный номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3804f-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="3804f-114">Например, для версии *x.y*, дополнительный номер версии — *y*.</span><span class="sxs-lookup"><span data-stu-id="3804f-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3804f-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="3804f-115">Remarks</span></span>  
 <span data-ttu-id="3804f-116">`GetTypeLibInfo` Функция вызывается из [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span><span class="sxs-lookup"><span data-stu-id="3804f-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="3804f-117">Это средство создает библиотеку типов, описывающую типы в сборке среды CLR.</span><span class="sxs-lookup"><span data-stu-id="3804f-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="3804f-118">Если какой-либо параметр имеет значение null, функция возвращает `HRESULT` из `E_POINTER`.</span><span class="sxs-lookup"><span data-stu-id="3804f-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="3804f-119">В противном случае возвращает значение `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="3804f-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3804f-120">Требования</span><span class="sxs-lookup"><span data-stu-id="3804f-120">Requirements</span></span>  
 <span data-ttu-id="3804f-121">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3804f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3804f-122">**Заголовок:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="3804f-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="3804f-123">**Библиотека:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="3804f-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="3804f-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3804f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3804f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="3804f-125">See Also</span></span>  
 [<span data-ttu-id="3804f-126">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="3804f-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [<span data-ttu-id="3804f-127">Функция LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="3804f-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
