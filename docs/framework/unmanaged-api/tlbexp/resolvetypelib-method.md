---
title: Метод ResolveTypeLib
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f274befe78e45be3e53335572fd9c1e0b401fd3
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040178"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="3364f-102">Метод ResolveTypeLib</span><span class="sxs-lookup"><span data-stu-id="3364f-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="3364f-103">Разрешает простое имя библиотеки типов, возвращая полный путь.</span><span class="sxs-lookup"><span data-stu-id="3364f-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3364f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3364f-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3364f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3364f-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="3364f-106">окне Значение типа [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащее простое имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3364f-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="3364f-107">окне Идентификатор GUID, назначенный библиотеке типов в реестре.</span><span class="sxs-lookup"><span data-stu-id="3364f-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="3364f-108">окне ИДЕНТИФИКАТОР локализации библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3364f-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="3364f-109">окне Основной номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3364f-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="3364f-110">Например, для версии *x. y*основной номер версии — *x*.</span><span class="sxs-lookup"><span data-stu-id="3364f-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="3364f-111">окне Дополнительный номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="3364f-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="3364f-112">Например, для версии *x. y*дополнительный номер версии — *y*.</span><span class="sxs-lookup"><span data-stu-id="3364f-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="3364f-113">окне Флаг [Сискинд](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий операционную среду.</span><span class="sxs-lookup"><span data-stu-id="3364f-113">[in] A [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="3364f-114">Распространенные значения — SYS_WIN32 и SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="3364f-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="3364f-115">заполняет Указатель на [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащий полный путь к библиотеке типов с именем в `bstrSimpleName` параметре.</span><span class="sxs-lookup"><span data-stu-id="3364f-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3364f-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="3364f-116">Remarks</span></span>  
 <span data-ttu-id="3364f-117">Метод вызывается [функцией LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) во время обработки программы [Tlbexp. exe (программа экспорта библиотек типов).](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) `ResolveTypeLib`</span><span class="sxs-lookup"><span data-stu-id="3364f-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="3364f-118">Пользовательские реализации этого интерфейса должны возвращать [строку BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащую полный путь к библиотеке типов с именем в `bstrSimpleName` параметре.</span><span class="sxs-lookup"><span data-stu-id="3364f-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3364f-119">Требования</span><span class="sxs-lookup"><span data-stu-id="3364f-119">Requirements</span></span>  
 <span data-ttu-id="3364f-120">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3364f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3364f-121">**Заголовок.** Тлбреф. idl, Тлбреф. h</span><span class="sxs-lookup"><span data-stu-id="3364f-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="3364f-122">**Библиотечная** Тлбреф. lib</span><span class="sxs-lookup"><span data-stu-id="3364f-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="3364f-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3364f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3364f-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3364f-124">See also</span></span>

- [<span data-ttu-id="3364f-125">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="3364f-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="3364f-126">лоадтипелибекс</span><span class="sxs-lookup"><span data-stu-id="3364f-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
