---
title: Функция Activate (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: ee231653815bd5ef75d58979034e3b3be9f5ba54
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777173"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="1fc5f-102">Функция Activate (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="1fc5f-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="1fc5f-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="1fc5f-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="1fc5f-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="1fc5f-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="1fc5f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1fc5f-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="1fc5f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1fc5f-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="1fc5f-107">Указатель на параметры активации окна.</span><span class="sxs-lookup"><span data-stu-id="1fc5f-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="1fc5f-108">Указатель на адрес буфера одного элемента, который содержит указатель на <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> объект.</span><span class="sxs-lookup"><span data-stu-id="1fc5f-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="1fc5f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1fc5f-109">Requirements</span></span>

<span data-ttu-id="1fc5f-110">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fc5f-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="1fc5f-111">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="1fc5f-111">**DLL:**</span></span>

<span data-ttu-id="1fc5f-112">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="1fc5f-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="1fc5f-113">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="1fc5f-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="1fc5f-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fc5f-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1fc5f-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1fc5f-115">See also</span></span>

- [<span data-ttu-id="1fc5f-116">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="1fc5f-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
