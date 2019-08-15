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
ms.openlocfilehash: 7da0986269189ba5c2dfa0f10d509bf51deb446d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040206"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="cc880-102">Функция GetTypeLibInfo</span><span class="sxs-lookup"><span data-stu-id="cc880-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="cc880-103">Возвращает сведения о указанной библиотеке типов, изучая ее структуру [тлибаттр](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) .</span><span class="sxs-lookup"><span data-stu-id="cc880-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc880-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc880-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc880-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc880-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="cc880-106">окне Имя файла библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="cc880-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="cc880-107">заполняет Идентификатор GUID библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="cc880-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="cc880-108">заполняет ИДЕНТИФИКАТОР локализации библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="cc880-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="cc880-109">заполняет Флаг [Сискинд](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий целевую операционную систему для библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="cc880-109">[out] A [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="cc880-110">Распространенные значения — SYS_WIN32 и SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="cc880-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="cc880-111">заполняет Основной номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="cc880-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="cc880-112">Например, для версии *x. y*основной номер версии — *x*.</span><span class="sxs-lookup"><span data-stu-id="cc880-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="cc880-113">заполняет Дополнительный номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="cc880-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="cc880-114">Например, для версии *x. y*дополнительный номер версии — *y*.</span><span class="sxs-lookup"><span data-stu-id="cc880-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc880-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="cc880-115">Remarks</span></span>  
 <span data-ttu-id="cc880-116">Функция вызывается программой [Tlbexp. exe (программа экспорта библиотек типов).](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) `GetTypeLibInfo`</span><span class="sxs-lookup"><span data-stu-id="cc880-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="cc880-117">Это средство создает библиотеку типов, описывающую типы в сборке среды CLR.</span><span class="sxs-lookup"><span data-stu-id="cc880-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="cc880-118">Если какой-либо из параметров имеет значение null, `HRESULT` функция `E_POINTER`возвращает объект.</span><span class="sxs-lookup"><span data-stu-id="cc880-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="cc880-119">В противном случае она возвращает `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="cc880-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc880-120">Требования</span><span class="sxs-lookup"><span data-stu-id="cc880-120">Requirements</span></span>  
 <span data-ttu-id="cc880-121">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc880-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc880-122">**Заголовок.** Тлбреф. h</span><span class="sxs-lookup"><span data-stu-id="cc880-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="cc880-123">**Библиотечная** Тлбреф. lib</span><span class="sxs-lookup"><span data-stu-id="cc880-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="cc880-124">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc880-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc880-125">См. также</span><span class="sxs-lookup"><span data-stu-id="cc880-125">See also</span></span>

- [<span data-ttu-id="cc880-126">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="cc880-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="cc880-127">Функция Лоадтипелибекс</span><span class="sxs-lookup"><span data-stu-id="cc880-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
