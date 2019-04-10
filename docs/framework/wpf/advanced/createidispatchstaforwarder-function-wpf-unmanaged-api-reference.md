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
ms.openlocfilehash: a89b29cd459060c93d5ca77bb2154e1a10b02d03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213654"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d96a8-102">Функция CreateIDispatchSTAForwarder (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="d96a8-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d96a8-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="d96a8-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d96a8-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления потоком и windows.</span><span class="sxs-lookup"><span data-stu-id="d96a8-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d96a8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d96a8-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d96a8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d96a8-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d96a8-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d96a8-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="d96a8-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="d96a8-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="d96a8-109">Указатель на `IDispatch` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d96a8-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="d96a8-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="d96a8-110">ppForwarder</span></span>  
 <span data-ttu-id="d96a8-111">Указатель на адрес `IDispatch` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d96a8-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d96a8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d96a8-112">Requirements</span></span>  
 <span data-ttu-id="d96a8-113">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d96a8-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 **<span data-ttu-id="d96a8-114">БИБЛИОТЕКА DLL:</span><span class="sxs-lookup"><span data-stu-id="d96a8-114">DLL:</span></span>**  
  
 <span data-ttu-id="d96a8-115">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="d96a8-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d96a8-116">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="d96a8-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 **<span data-ttu-id="d96a8-117">Версии платформы .NET framework:</span><span class="sxs-lookup"><span data-stu-id="d96a8-117">.NET Framework Version:</span></span>** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d96a8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d96a8-118">See also</span></span>

- [<span data-ttu-id="d96a8-119">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="d96a8-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
