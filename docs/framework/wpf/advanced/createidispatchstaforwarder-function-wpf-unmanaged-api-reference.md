---
title: Функция CreateIDispatchSTAForwarder (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 1a19b7699c7a9e2b663149ea31bccb67189e68c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487828"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e46b9-102">Функция CreateIDispatchSTAForwarder (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e46b9-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="e46b9-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="e46b9-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="e46b9-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления потоком и windows.</span><span class="sxs-lookup"><span data-stu-id="e46b9-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e46b9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e46b9-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="e46b9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e46b9-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e46b9-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e46b9-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="e46b9-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="e46b9-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="e46b9-109">Указатель на `IDispatch` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e46b9-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="e46b9-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="e46b9-110">ppForwarder</span></span>  
 <span data-ttu-id="e46b9-111">Указатель на адрес `IDispatch` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e46b9-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e46b9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e46b9-112">Requirements</span></span>  
 <span data-ttu-id="e46b9-113">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e46b9-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e46b9-114">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="e46b9-114">**DLL:**</span></span>  
  
 <span data-ttu-id="e46b9-115">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="e46b9-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="e46b9-116">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="e46b9-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="e46b9-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e46b9-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e46b9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e46b9-118">See also</span></span>
- [<span data-ttu-id="e46b9-119">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="e46b9-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
