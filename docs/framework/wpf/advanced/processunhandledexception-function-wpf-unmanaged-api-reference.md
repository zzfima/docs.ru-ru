---
title: Функция ProcessUnhandledException (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 3a95e8e68361f060d843247f400043a79dc28889
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466873"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="7e7fc-102">Функция ProcessUnhandledException (WPF Справочник по неуправляемым API)</span><span class="sxs-lookup"><span data-stu-id="7e7fc-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="7e7fc-103">Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="7e7fc-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="7e7fc-104">Используется инфраструктурой Windows Presentation Foundation (WPF) для обработки исключений.</span><span class="sxs-lookup"><span data-stu-id="7e7fc-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e7fc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e7fc-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e7fc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e7fc-106">Parameters</span></span>  
 <span data-ttu-id="7e7fc-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="7e7fc-107">errorMsg</span></span>  
 <span data-ttu-id="7e7fc-108">Сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="7e7fc-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e7fc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7e7fc-109">Requirements</span></span>  
 <span data-ttu-id="7e7fc-110">**Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e7fc-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e7fc-111">**БИБЛИОТЕКА DLL:**</span><span class="sxs-lookup"><span data-stu-id="7e7fc-111">**DLL:**</span></span>  
  
 <span data-ttu-id="7e7fc-112">В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="7e7fc-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="7e7fc-113">В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="7e7fc-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="7e7fc-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e7fc-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e7fc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7e7fc-115">See also</span></span>
- [<span data-ttu-id="7e7fc-116">Справочник по неуправляемым API WPF</span><span class="sxs-lookup"><span data-stu-id="7e7fc-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
