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
ms.openlocfilehash: f7e45d5cafa40ba147fe39888e74a67ac9f95c5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="e9598-102">Функция CreateIDispatchSTAForwarder (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="e9598-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="e9598-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="e9598-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="e9598-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для управления потоком и windows.</span><span class="sxs-lookup"><span data-stu-id="e9598-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9598-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9598-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9598-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9598-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e9598-107">Значение свойства, возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e9598-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="e9598-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="e9598-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="e9598-109">Указатель на `IDispatch` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e9598-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="e9598-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="e9598-110">ppForwarder</span></span>  
 <span data-ttu-id="e9598-111">Указатель на адрес `IDispatch` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e9598-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9598-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e9598-112">Requirements</span></span>  
 <span data-ttu-id="e9598-113">**Платформы:** разделе [требования к системе для .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9598-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9598-114">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="e9598-114">**DLL:**</span></span>  
  
 <span data-ttu-id="e9598-115">В платформе .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="e9598-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="e9598-116">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="e9598-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="e9598-117">**Версия платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9598-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9598-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e9598-118">See Also</span></span>  
 [<span data-ttu-id="e9598-119">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="e9598-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
