---
title: Активация функции — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734511"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="3b4f3-102">Функция Activate (Справочник по неуправляемым ИНТЕРФЕЙСам WPF)</span><span class="sxs-lookup"><span data-stu-id="3b4f3-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="3b4f3-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.</span><span class="sxs-lookup"><span data-stu-id="3b4f3-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="3b4f3-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления Windows.</span><span class="sxs-lookup"><span data-stu-id="3b4f3-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="3b4f3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b4f3-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="3b4f3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3b4f3-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="3b4f3-107">Указатель на параметры активации окна.</span><span class="sxs-lookup"><span data-stu-id="3b4f3-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="3b4f3-108">Указатель на адрес буфера с одним элементом, который содержит указатель на объект <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument>.</span><span class="sxs-lookup"><span data-stu-id="3b4f3-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b4f3-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3b4f3-109">Requirements</span></span>

<span data-ttu-id="3b4f3-110">**Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b4f3-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3b4f3-111">**КОМПОНОВКИ**</span><span class="sxs-lookup"><span data-stu-id="3b4f3-111">**DLL:**</span></span>

<span data-ttu-id="3b4f3-112">В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll</span><span class="sxs-lookup"><span data-stu-id="3b4f3-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="3b4f3-113">В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="3b4f3-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="3b4f3-114">**Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b4f3-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3b4f3-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3b4f3-115">See also</span></span>

- [<span data-ttu-id="3b4f3-116">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="3b4f3-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
