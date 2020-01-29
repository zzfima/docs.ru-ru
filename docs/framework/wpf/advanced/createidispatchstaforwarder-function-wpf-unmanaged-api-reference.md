---
title: Функция Креатеидиспатчстафорвардер — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738030"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="c6878-102">Функция Креатеидиспатчстафорвардер (Справочник по неуправляемым интерфейсам API WPF)</span><span class="sxs-lookup"><span data-stu-id="c6878-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="c6878-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.</span><span class="sxs-lookup"><span data-stu-id="c6878-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="c6878-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления потоками и окнами.</span><span class="sxs-lookup"><span data-stu-id="c6878-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6878-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6878-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6878-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6878-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c6878-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c6878-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="c6878-108">пдиспатчделегате</span><span class="sxs-lookup"><span data-stu-id="c6878-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="c6878-109">Указатель на интерфейс `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="c6878-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="c6878-110">ппфорвардер</span><span class="sxs-lookup"><span data-stu-id="c6878-110">ppForwarder</span></span>  
 <span data-ttu-id="c6878-111">Указатель на адрес интерфейса `IDispatch`.</span><span class="sxs-lookup"><span data-stu-id="c6878-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6878-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c6878-112">Requirements</span></span>  
 <span data-ttu-id="c6878-113">**Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6878-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6878-114">**КОМПОНОВКИ**</span><span class="sxs-lookup"><span data-stu-id="c6878-114">**DLL:**</span></span>  
  
 <span data-ttu-id="c6878-115">В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll</span><span class="sxs-lookup"><span data-stu-id="c6878-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="c6878-116">В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll</span><span class="sxs-lookup"><span data-stu-id="c6878-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="c6878-117">**Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6878-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6878-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="c6878-118">See also</span></span>

- [<span data-ttu-id="c6878-119">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="c6878-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
