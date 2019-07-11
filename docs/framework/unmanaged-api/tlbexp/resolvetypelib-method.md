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
ms.openlocfilehash: 0b6db8925fb966f4a8b2a213b0d6e340d0edf107
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756429"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="2e677-102">Метод ResolveTypeLib</span><span class="sxs-lookup"><span data-stu-id="2e677-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="2e677-103">Разрешает простое имя библиотеки типов путем возвращения ее полного пути.</span><span class="sxs-lookup"><span data-stu-id="2e677-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e677-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e677-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2e677-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2e677-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="2e677-106">[in] Объект [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащий простое имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2e677-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="2e677-107">[in] Идентификатор GUID, назначенный в библиотеку типов в реестре.</span><span class="sxs-lookup"><span data-stu-id="2e677-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="2e677-108">[in] Идентификатор локализации библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2e677-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="2e677-109">[in] Основной номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2e677-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="2e677-110">Например, для версии *x.y*, основной номер версии — *x*.</span><span class="sxs-lookup"><span data-stu-id="2e677-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="2e677-111">[in] Дополнительный номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2e677-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="2e677-112">Например, для версии *x.y*, дополнительный номер версии — *y*.</span><span class="sxs-lookup"><span data-stu-id="2e677-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="2e677-113">[in] Объект [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) флаг, определяющий операционной среде.</span><span class="sxs-lookup"><span data-stu-id="2e677-113">[in] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="2e677-114">Обычные значения: SYS_WIN32 и SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="2e677-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="2e677-115">[out] Указатель на [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащее полный путь к библиотеке типов, с именем в `bstrSimpleName` параметра.</span><span class="sxs-lookup"><span data-stu-id="2e677-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e677-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="2e677-116">Remarks</span></span>  
 <span data-ttu-id="2e677-117">`ResolveTypeLib` Вызывается метод [функция LoadTypeLibWithResolver](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) во время [Tlbexp.exe (программа экспорта библиотек типов)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) обработки.</span><span class="sxs-lookup"><span data-stu-id="2e677-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="2e677-118">Пользовательские реализации этого интерфейса должны возвращать [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащее полный путь к библиотеке типов, с именем в `bstrSimpleName` параметра.</span><span class="sxs-lookup"><span data-stu-id="2e677-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e677-119">Требования</span><span class="sxs-lookup"><span data-stu-id="2e677-119">Requirements</span></span>  
 <span data-ttu-id="2e677-120">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e677-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e677-121">**Заголовок.** TlbRef.idl TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="2e677-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="2e677-122">**Библиотека:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="2e677-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="2e677-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e677-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e677-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2e677-124">See also</span></span>

- [<span data-ttu-id="2e677-125">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="2e677-125">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="2e677-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="2e677-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
