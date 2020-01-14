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
ms.openlocfilehash: f0f6fe321f4d38129b6d70ce94a7ea8de8fff6c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935671"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="e23d4-102">Метод ResolveTypeLib</span><span class="sxs-lookup"><span data-stu-id="e23d4-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="e23d4-103">Разрешает простое имя библиотеки типов, возвращая полный путь.</span><span class="sxs-lookup"><span data-stu-id="e23d4-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e23d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e23d4-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e23d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e23d4-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="e23d4-106">окне Значение типа [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащее простое имя библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="e23d4-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="e23d4-107">окне Идентификатор GUID, назначенный библиотеке типов в реестре.</span><span class="sxs-lookup"><span data-stu-id="e23d4-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="e23d4-108">окне ИДЕНТИФИКАТОР локализации библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="e23d4-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="e23d4-109">окне Основной номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="e23d4-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="e23d4-110">Например, для версии *x. y*основной номер версии — *x*.</span><span class="sxs-lookup"><span data-stu-id="e23d4-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="e23d4-111">окне Дополнительный номер версии библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="e23d4-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="e23d4-112">Например, для версии *x. y*дополнительный номер версии — *y*.</span><span class="sxs-lookup"><span data-stu-id="e23d4-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="e23d4-113">окне Флаг [Сискинд](/windows/win32/api/oaidl/ne-oaidl-syskind) , определяющий операционную среду.</span><span class="sxs-lookup"><span data-stu-id="e23d4-113">[in] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="e23d4-114">Распространенные значения: SYS_WIN32 и SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="e23d4-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="e23d4-115">заполняет Указатель на [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащий полный путь к библиотеке типов с именем в параметре `bstrSimpleName`.</span><span class="sxs-lookup"><span data-stu-id="e23d4-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e23d4-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="e23d4-116">Remarks</span></span>  
 <span data-ttu-id="e23d4-117">Метод `ResolveTypeLib` вызывается [функцией LoadTypeLibWithResolver](loadtypelibwithresolver-function.md) во время обработки программы [Tlbexp. exe (программа экспорта библиотек типов)](../../tools/tlbexp-exe-type-library-exporter.md) .</span><span class="sxs-lookup"><span data-stu-id="e23d4-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="e23d4-118">Пользовательские реализации этого интерфейса должны возвращать [строку BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) , содержащую полный путь к библиотеке типов с именем в параметре `bstrSimpleName`.</span><span class="sxs-lookup"><span data-stu-id="e23d4-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e23d4-119">Требования</span><span class="sxs-lookup"><span data-stu-id="e23d4-119">Requirements</span></span>  
 <span data-ttu-id="e23d4-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e23d4-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e23d4-121">**Заголовок:** Тлбреф. idl, Тлбреф. h</span><span class="sxs-lookup"><span data-stu-id="e23d4-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="e23d4-122">**Библиотека:** Тлбреф. lib</span><span class="sxs-lookup"><span data-stu-id="e23d4-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="e23d4-123">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e23d4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e23d4-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="e23d4-124">See also</span></span>

- [<span data-ttu-id="e23d4-125">Вспомогательные функции Tlbexp</span><span class="sxs-lookup"><span data-stu-id="e23d4-125">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="e23d4-126">лоадтипелибекс</span><span class="sxs-lookup"><span data-stu-id="e23d4-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
