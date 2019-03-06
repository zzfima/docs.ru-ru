---
title: Функция Activate (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 6410b05a1b858a7b75c9bff3220d47505beabd7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357278"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="16aac-102">Функция Activate (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="16aac-102">Activate Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="16aac-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="16aac-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="16aac-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.</span><span class="sxs-lookup"><span data-stu-id="16aac-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16aac-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="16aac-105">Syntax</span></span>  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16aac-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="16aac-106">Parameters</span></span>  
 <span data-ttu-id="16aac-107">pParameters</span><span class="sxs-lookup"><span data-stu-id="16aac-107">pParameters</span></span>  
 <span data-ttu-id="16aac-108">Указатель на параметры активации окна.</span><span class="sxs-lookup"><span data-stu-id="16aac-108">A pointer to the window's activation parameters.</span></span>  
  
 <span data-ttu-id="16aac-109">ppInner</span><span class="sxs-lookup"><span data-stu-id="16aac-109">ppInner</span></span>  
 <span data-ttu-id="16aac-110">Указатель на адрес буфера одного элемента, который содержит указатель на <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> объект.</span><span class="sxs-lookup"><span data-stu-id="16aac-110">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16aac-111">Требования</span><span class="sxs-lookup"><span data-stu-id="16aac-111">Requirements</span></span>  
 <span data-ttu-id="16aac-112">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16aac-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16aac-113">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="16aac-113">**DLL:**</span></span>  
  
 <span data-ttu-id="16aac-114">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="16aac-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="16aac-115">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="16aac-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="16aac-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16aac-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16aac-117">См. также</span><span class="sxs-lookup"><span data-stu-id="16aac-117">See also</span></span>
- [<span data-ttu-id="16aac-118">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="16aac-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
