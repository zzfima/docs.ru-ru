---
title: Функция CreateIDispatchSTAForwarder - ссылка на Неуправляемый API WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174723"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="bc3e8-102">Функция CreateIDispatchSTAForwarder (Ссылка на Неуправляемый API WPF)</span><span class="sxs-lookup"><span data-stu-id="bc3e8-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="bc3e8-103">Этот API поддерживает инфраструктуру Фонда презентаций Windows (WPF) и не предназначен для использования непосредственно из вашего кода.</span><span class="sxs-lookup"><span data-stu-id="bc3e8-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="bc3e8-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления потоками и окнами.</span><span class="sxs-lookup"><span data-stu-id="bc3e8-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc3e8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc3e8-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc3e8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bc3e8-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bc3e8-107">Значение свойства/возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bc3e8-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="bc3e8-108">pDispatchДелегат</span><span class="sxs-lookup"><span data-stu-id="bc3e8-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="bc3e8-109">Указатель на `IDispatch` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="bc3e8-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="bc3e8-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="bc3e8-110">ppForwarder</span></span>  
 <span data-ttu-id="bc3e8-111">Указатель на адрес интерфейса. `IDispatch`</span><span class="sxs-lookup"><span data-stu-id="bc3e8-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc3e8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bc3e8-112">Requirements</span></span>  
 <span data-ttu-id="bc3e8-113">**Платформы:** Смотрите [требования рамочной системы .NET](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc3e8-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc3e8-114">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="bc3e8-114">**DLL:**</span></span>  
  
 <span data-ttu-id="bc3e8-115">В рамках .NET 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="bc3e8-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="bc3e8-116">В рамках .NET 4 и позже: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="bc3e8-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="bc3e8-117">**Рамочная версия .NET:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc3e8-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc3e8-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bc3e8-118">See also</span></span>

- [<span data-ttu-id="bc3e8-119">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="bc3e8-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
